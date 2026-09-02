# SOLUTION — Global AI Platform Architecture

> Read this *after* you have drafted your own target architecture. This
> is the reasoning the reference design is defending, not a scoring key.
> A different architecture that defends the same properties is a valid
> answer.

## 1. Solution overview

A senior architect answers three questions in a global-platform design
review:

1. **Where does data live, and under what authority?** — the residency
   and sovereignty question. This drives the region layout more than
   latency does.
2. **What is centralized, and what is federated?** — the control-plane
   vs. data-plane split. Model registry, policy, IAM, audit are
   centralized; storage, training, and inference are regional.
3. **What survives the failure of a single provider, a single
   jurisdiction, or a single sponsor?** — the reversibility and
   blast-radius question. Multi-cloud is expensive; the design has to
   justify the specific places it's paid for and the specific places
   it's not.

The reference target state is a **regional data plane, global control
plane, model-registry-as-source-of-truth** platform. Data classes are
bound to region sets by policy; the control plane runs on a primary
hyperscaler with a warm-standby on a second; the mainland-China footprint
is a separately governed cell that shares standards but not tenancy with
the rest of the platform.

The **key trade-off accepted** is duplication: the platform runs two
control planes (global + China cell), maintains two sets of operational
runbooks, and pays for one region set to be strictly compliant with the
strictest applicable regulation rather than optimized for cost. The
alternative — a single "global-except-China" plane with cost-optimized
regions — fails a residency audit the first time GDPR meets DPDP meets
the EU AI Act simultaneously.

## 2. Worked answer (the reference target state)

### 2.1 Region layout

| Cell | Primary purpose | Cloud A | Cloud B | Residency binding |
|---|---|---|---|---|
| **EU-central** (Frankfurt) | EU personal data, EU credit models | Hyperscaler A `eu-central-1` equivalent | Hyperscaler B `europe-west3` equivalent | GDPR; EU AI Act high-risk registry co-located |
| **EU-west** (Dublin/Paris) | EU DR + latency backfill for EU-west customers | Hyperscaler A | Hyperscaler B | Same as EU-central; cross-region only within EU |
| **US-east** (N. Virginia) | US retail + US regulated data (GLBA scope) | Hyperscaler A | Hyperscaler B | US only; UK data may replicate here under UK IDTA / EU-US Data Privacy Framework where applicable |
| **UK** (London) | UK-only regulatory footprint (PRA/FCA) | Hyperscaler A `eu-west-2` equivalent | — | UK data resident; may transit to US only under approved transfer mechanism |
| **BR** (São Paulo) | Brazil retail (LGPD) | Hyperscaler A | — | LGPD; onward transfer only under adequacy or SCCs |
| **IN** (Mumbai/Hyderabad) | India retail (DPDP Act 2023) | Hyperscaler A | Hyperscaler B | Personal data of Indian citizens resident in India; cross-border only to allow-listed countries under DPDP Section 16 |
| **SG** (Singapore) | APAC ex-CN, ex-IN hub; Singapore, HK, AU, JP customers | Hyperscaler A | Hyperscaler B | Per-country policy at ingestion; Singapore PDPA at rest |
| **CN cell** (Shanghai + Beijing) | Mainland China personal information | Local partner (Alibaba Cloud / Tencent Cloud / JV) | Local partner (secondary) | PIPL; cross-border personal information transfer only under CAC assessment / SCCs |

**Why this layout, not a smaller one.** A design that consolidates EU
and UK into "EMEA" saves cost until the first PRA thematic review. A
design that consolidates India and Singapore into "APAC ex-China" fails
DPDP because Indian personal data is expected to be locally resident by
default; the allow-list for cross-border transfer is
government-controlled and can change without notice.

**Why this layout, not a larger one.** Adding a Japan-resident cell or
a Middle East cell is defensible when there is a material book of
regulated business in those markets. The reference target does not
open cells speculatively; opening a cell is a Board decision because
each cell adds ~4–8 FTEs of run-cost regardless of workload volume.

### 2.2 Control plane vs. data plane

**Data plane (regional)**:
- Object storage, relational storage, feature-store storage.
- Training clusters (GPU / TPU where available).
- Inference endpoints (batch and online).
- Regional caching and CDN edges.
- Data pipelines that touch personal data.

**Control plane (global, with one exception)**:
- Model registry (**the single source of truth for what is deployed
  where, and under what classification**).
- Policy engine (residency policy, AI-Act classification policy,
  data-classification policy).
- Identity and access (SSO, RBAC/ABAC, service identity federation).
- Observability aggregation (metadata only; raw logs stay regional).
- Deployment orchestrator (GitOps-style; the orchestrator holds no
  personal data).
- Audit log aggregation (immutable, WORM-backed, retained per the
  longest applicable statutory period).

**The exception**: the mainland-China cell operates its own control
plane instance. It receives the standards (registry schema, policy
definitions, orchestrator behavior) as **artifacts**, not as **calls**.
The China cell registry synchronizes model *metadata* to a
metadata-only mirror outside China for global governance visibility;
model *weights* and *training data* do not cross the border unless
they have been through a CAC (Cyberspace Administration of China)
cross-border transfer assessment.

**Why this split, and why the China cell is separate.** The single-
control-plane design is what makes governance tractable — the registry
is the authoritative statement of "what model is in production
anywhere, and what obligations attach to it." Splitting the registry
regionally means you cannot answer "how many high-risk AI systems do we
operate globally" without a reconciliation job, and regulators do not
accept "we'll get back to you." The China cell is separate because a
Western-headquartered control plane cannot lawfully be the primary
authority for PIPL-scope personal information without a CAC assessment
that in practice is not granted for this shape of workload; treating
China as a peer cell that mirrors metadata is the operational
compromise that keeps global visibility without violating PIPL.

### 2.3 Data residency and sovereignty policy

Every dataset has a **residency class**, assigned at ingestion and
carried in metadata:

| Class | Examples | Storage regions | Cross-region allowed? | Cross-border training data? |
|---|---|---|---|---|
| **C0 — Public reference** | Model architectures, open datasets, public docs | Any | Yes | Yes |
| **C1 — Business confidential, non-personal** | Aggregated KPIs, model performance metrics, non-personal telemetry | Any group region | Yes, within group | Yes, if de-identification is verified |
| **C2 — Personal, non-sensitive** | Customer contact, non-sensitive KYC fields | Origin region only | No (except lawful transfer) | Only under approved cross-border transfer mechanism |
| **C3 — Personal, sensitive / regulated** | Full KYC, transaction history, credit-decisioning inputs, biometric | Origin region only, in the cell defined for that jurisdiction | No | No; training runs in-region against in-region data |
| **C4 — Restricted (sanctioned jurisdictions, adversarial-target lists)** | As defined by CISO / Compliance | Approved cell only; separate encryption authority | No | No; models trained on C4 data do not leave the cell |

Enforcement is not left to policy documents. It is enforced by:

- **Ingestion tags**. Data cannot land in the platform without a
  residency class; untagged ingestion is rejected at the pipeline edge.
- **Storage IAM**. Each region's storage account only accepts writes
  whose residency class matches the region policy.
- **Egress controls**. VPC egress rules, private-link topology, and
  KMS key locality make it not-quietly-possible for a training job to
  read C3 data in a wrong region. Attempts are logged as security
  events.
- **Model registry gates**. A model whose training-data lineage
  includes a residency class that does not match the region of
  deployment cannot be promoted to production in that region. This is
  the last-line control.

**Why enforcement, not policy.** A residency policy that lives only
in a Confluence page is a policy that will be violated within 90 days
of the first incident-response drill. The compensating controls
above are what a regulator asks for; they are the answer to "show me
how you know."

### 2.4 EU AI Act as a first-class platform concern

The registry carries an **AI-Act classification** per model:

- **Prohibited** — the platform refuses to accept these models
  (social scoring, real-time biometric ID in public spaces except for
  the narrow authorized exceptions, etc.). Registration attempt is
  logged and escalated.
- **High-risk** — credit scoring, employment decisions, essential
  services eligibility, and other Annex III use cases. The registry
  requires the additional evidentiary artifacts before allowing
  promotion to production: data-governance record, technical
  documentation, transparency information, human-oversight design,
  post-market monitoring plan, and the conformity self-assessment (or
  notified-body assessment where applicable).
- **Limited-risk** — transparency obligations attach (users are
  informed they are interacting with an AI system where required).
  Registry checks for transparency configuration.
- **Minimal-risk** — standard governance.

**Why in the registry, not in a policy checklist.** High-risk
obligations attach for the full life of the model. The registry is the
only object that lives that long — features get rebuilt, pipelines
get refactored, training clusters get retired. If the classification
lives in the registry, the obligations follow the model automatically.
If the classification lives in a document, they get lost the first
time the responsible team reorganizes.

### 2.5 Reference architecture summary

```
                          ┌─────────────────────────────────────┐
                          │       GLOBAL CONTROL PLANE           │
                          │  (Cloud A primary, Cloud B standby)  │
                          │                                      │
                          │  • Model registry (SoT)              │
                          │  • Policy engine                     │
                          │  • Federated identity                │
                          │  • Deployment orchestrator (GitOps)  │
                          │  • Audit aggregation (metadata)      │
                          └──────┬───────────────────┬───────────┘
                                 │                   │
              ┌──────────────────┼───────────────────┼─────────────────────┐
              │                  │                   │                     │
   ┌──────────▼─────────┐  ┌─────▼──────────┐  ┌─────▼──────────┐   ┌──────▼───────┐
   │   EU CELLS         │  │  AMER CELLS    │  │  APAC ex-CN,   │   │  CN CELL     │
   │  (EU-C, EU-W, UK)  │  │  (US-E, BR)    │  │  ex-IN (SG)    │   │  (Shanghai + │
   │                    │  │                │  │  + IN cell     │   │   Beijing)   │
   │  Regional data     │  │  Regional data │  │  (Mumbai)      │   │              │
   │  plane, in-region  │  │  plane         │  │                │   │  Separate    │
   │  training + serve  │  │                │  │  Regional data │   │  control     │
   │                    │  │                │  │  plane         │   │  plane;      │
   │  Cloud A + Cloud B │  │  Cloud A +     │  │                │   │  metadata    │
   │                    │  │  Cloud B       │  │  Cloud A +     │   │  mirror only │
   │                    │  │                │  │  Cloud B       │   │              │
   └────────────────────┘  └────────────────┘  └────────────────┘   └──────────────┘
```

Full artifact: `architecture/target-architecture.md`.

### 2.6 Roadmap sequenced by reversibility

Phase ordering is deliberate. Each phase is chosen to buy information
about the next.

- **Phase 0 (Months 0-3) — Alignment and inventory.** Model registry
  standing up as a *read-only* observatory over existing platforms.
  Every existing model is registered, classified for the AI Act,
  and its residency status recorded. **Highly reversible** (nothing
  is migrated; the registry is a mirror).
- **Phase 1 (Months 3-9) — Control plane build-out.** Global control
  plane deployed. Policy engine authoritative for *new* workloads;
  existing workloads remain on their current substrate. **Medium
  reversibility**: reverting means turning the new registry back into
  a read-only observatory.
- **Phase 2 (Months 9-18) — Regional data planes.** EU-central and
  US-east first; UK, BR, SG, IN follow. Migration happens per model,
  per team; the registry gates whether a model is served from the
  new data plane. **Low reversibility per migrated model**, but the
  registry lets us pause and re-plan per model.
- **Phase 3 (Months 18-24) — China cell.** Separate control plane
  stood up with local partner. Metadata mirror established. Migration
  from the three legacy APAC stacks. **Distinct workstream**; failure
  here does not block phases 0-2 from delivering value.
- **Phase 4 (Months 24-36) — Retirement and optimization.** Legacy
  platforms retired. FinOps takes over as the operating discipline.
  **The retirement decision itself is a gate** — retirement only
  proceeds when the last workload on the legacy platform has been
  either migrated or explicitly out-scoped.

**Why sequenced by reversibility.** A design review that goes wrong in
Phase 0 costs weeks. A design review that goes wrong in Phase 3 costs
quarters. Building the registry first, migrating last, and treating
China as a parallel workstream front-loads the cheap reversible
decisions.

### 2.7 Vendor concentration and exit posture

Named-vendor risk is treated explicitly. The design commits to:

- Two hyperscalers of record globally (outside China), with the
  control plane deployed to both. The primary carries production
  traffic; the secondary carries continuous warm-standby workload
  sufficient to keep the operational muscle current, not a "cold DR
  we've never tested" account.
- One local partner primary in China with a secondary partner
  identified. The China cell is expected to be able to fail over
  between local partners within a defined RTO. The reference
  target commits to **4 hours for control-plane recovery** and
  **24 hours for full workload restoration**, consistent with the
  bank-sector operational-resilience posture that Chinese domestic
  banks apply to their own cloud tenancies. Per-workload benchmark
  numbers (batch training vs. online inference vs. feature-store
  read path) are deferred to a follow-up compliance workstream —
  tracked as **FOLLOWUP-CN-RTO-01** on the platform backlog —
  which validates the specific numbers with the local partners and
  the FS-scenario risk register at the Phase 3 acceptance gate.
  This deferral is scoped and time-bound; it is not an open
  research question blocking the reference design.
- Storage formats are open (Parquet / Iceberg / Delta as appropriate);
  model artifacts are portable (ONNX / TorchScript / vendor-neutral
  container images). Feature-store schemas are portable; the
  feature-store *implementation* is not, and that trade-off is
  explicit.
- No compute-plane primitives are used that cannot be reproduced on
  the alternate hyperscaler within one quarter of engineering effort.
  Managed services that fail this test (proprietary training
  accelerators without portable equivalents, provider-only
  vector-store implementations) are opt-in per workload, not default.

## Implementation

The implementation approach is defined by the roadmap in
Section 2.6, the residency enforcement mechanisms in Section 2.3,
and the vendor-exit posture in Section 2.7. Rather than repeat
those, this section names the invariants an implementation team
must hold:

- **Registry-first.** No workload migrates before it is
  registered and classified. The registry gates every
  downstream promotion decision; if the registry is not
  authoritative in Phase 1, the residency guarantees in
  Section 2.3 cannot be enforced in Phase 2.
- **Enforcement is code.** Residency, AI-Act classification,
  and cross-border transfer mechanisms are enforced by the
  controls listed in Section 2.3 (ingestion tags, storage IAM,
  egress controls, registry gates). Every control has a build
  owner and an automated conformance test defined in
  `architecture/target-architecture.md`.
- **Reversibility over cost.** Each phase in Section 2.6
  is chosen to buy information about the next. Cost
  optimization is Phase 4 work; it does not shape the
  Phase 0-2 substrate.
- **China cell as a parallel workstream.** Phase 3 runs in
  parallel with Phases 1-2; its delivery does not block, and
  is not blocked by, the global cell. Metadata mirror
  discipline is defined at the start of Phase 3, not the end.
- **Sponsor-neutral operating cadence.** Implementation gates
  in each phase are automated (registry sign-off, policy-
  engine dry-run, migration proof) rather than sponsor-
  approved. This is what makes the platform survive a
  sponsor rotation as noted in Validation step 4.

Sizing, team topology, and per-artifact build ownership are
captured in `architecture/target-architecture.md`; that
document is the operational companion to this SOLUTION.

## 3. Validation steps

A senior architect validates a design like this against the
following. If any check fails, the design is not yet ready for review.

**Structural checks**:

1. Can you point to the specific control that prevents C3 data from
   region A from being read by a training job in region B? Is it a
   single control or defense in depth?
2. Can you name the object in the platform that answers "how many
   high-risk AI Act systems are in production right now, and in which
   regions?" without a batch job?
3. If Cloud A is sanctioned in a jurisdiction next quarter, what is
   the migration path, and how long does it take? Is the estimate
   based on portable artifacts, or on rewriting them?
4. If the executive sponsor rotates, what changes about the design?
   (Correct answer: not the architecture; possibly the roadmap
   sequencing; definitely the communication cadence.)

**Regulatory dry-runs**:

5. Pick a fictional EU customer whose personal data is in EU-central.
   Trace what happens when that data is used to train the fraud
   model. Where is the training data at rest, at compute, in
   metadata, and in the resulting model artifact? Which of those
   crossings, if any, cross a border? Under what mechanism?
6. Same trace, but for an Indian customer's data and a credit
   scoring model. Confirm the DPDP posture is defensible.
7. Same trace, but for a Chinese customer's data. Confirm that no
   personal information leaves China, that model artifacts trained
   on Chinese data stay in the China cell, and that only metadata
   crosses to the global registry mirror.

**Operational dry-runs**:

8. Draw the incident-response path for a high-severity model
   incident (a production credit-scoring model producing biased
   decisions) that spans the EU cell and the US cell. Which team is
   accountable? Which pager fires? How is model rollback
   authorized?
9. Walk through what a first-time regulator inquiry looks like.
   Which artifacts are produced from the platform automatically?
   Which require engineering work?

If steps 1-9 can be walked through without hand-waving, the design is
review-ready. If any require "we would need to build that," the
design is not yet complete.

## 4. Rubric — quick reference

The full rubric lives at `rubric/evaluation-rubric.md`. The
five weighted dimensions are:

1. **Residency and sovereignty defensibility** (weight: 25%). Is the
   policy enforceable, or is it aspirational?
2. **Control-plane vs. data-plane split** (weight: 20%). Is the split
   coherent? Is the model registry the source of truth for governance
   claims?
3. **EU AI Act operationalization** (weight: 15%). Is classification
   in the registry, or in a checklist?
4. **Vendor concentration and exit posture** (weight: 15%). Is
   multi-cloud paid for where it matters, and only where it matters?
5. **Roadmap sequenced by reversibility** (weight: 15%). Are early
   phases cheap to reverse? Are late phases the ones with real
   commitment?

Remaining 10% is distributed across documentation quality, diagram
correctness, and consistency of claims across artifacts.

A submission scoring below 60 on Dimension 1 (residency) is
non-passing regardless of other scores. A senior architect who does
not defend residency in a globally-regulated workload has not
demonstrated the level.

## 5. Common mistakes

**1. "Multi-region" mistaken for "global-compliant."** Two AWS
regions in the US and one in Frankfurt is a multi-region design;
it is not a compliant global design. Multi-region solves latency
and availability; global-compliant solves *residency*.

**2. Single global control plane hosting personal data.** The
control plane is designed for global reach; a design that lets
personal data leak into control-plane storage (via logs, via
observability, via cached metadata) breaks residency by accident.
Metadata-only aggregation is a deliberate discipline.

**3. Treating the China cell as "another region."** Mainland China
is not a region; it is a separate governance domain. Designs that
model China as `cn-north-1` on the main control plane will fail
PIPL scrutiny at the first serious review.

**4. AI-Act classification as a checklist.** Classification that
lives in a spreadsheet gets stale. Classification that lives in the
registry follows the model.

**5. Optimizing for cost in the wrong phase.** Cost optimization
belongs in Phase 4. Optimizing the region layout for cost in Phase 1
buys a design that is 30% cheaper and 100% non-compliant.

**6. Multi-cloud everywhere.** Multi-cloud has real cost. The design
pays for it where the risk warrants (control plane, primary regions
with regulatory exposure) and does not pay for it where the risk
does not (Brazil-only workload, UK-only workload). A senior
submission distinguishes; a junior submission either pays everywhere
or nowhere.

**7. Ignoring the sponsor question.** Global platform programs
outlive most executive sponsors. A design that only works when the
current CDO is in seat is not a global platform; it is a personal
project. The reference design explicitly discusses sponsor rotation
in Phase 0 alignment.

**8. Treating governance as Phase 3.** Governance is Phase 0. If it
appears later, it will not be enforced by the time it appears.

**9. Diagram without policy.** A boxes-and-arrows diagram that does
not name the residency class of the flowing data is a picture, not
an architecture. Every arrow between regions in the reference
diagrams is annotated with the residency-transfer mechanism.

**10. Perfect on paper, unbuildable in practice.** A design that
requires 200 FTE of platform engineering to operate is not a
platform, it is a research project. Reference sizing (see the
architecture doc) targets a steady-state platform team compatible
with a large-enterprise (not FAANG) staffing model.

## 6. References

Regulatory and standards references cited or relied upon by this
solution:

- **General Data Protection Regulation (GDPR)** — Regulation (EU)
  2016/679. In particular Articles 44–49 (transfers of personal
  data to third countries).
  <https://eur-lex.europa.eu/eli/reg/2016/679/oj>
- **EU Artificial Intelligence Act** — Regulation (EU) 2024/1689.
  Risk classification (Titles II–III), obligations for
  high-risk AI systems, and post-market monitoring.
  <https://eur-lex.europa.eu/eli/reg/2024/1689/oj>
- **UK Data Protection Act 2018** and the UK International Data
  Transfer Agreement (IDTA), for personal data transfers out of
  the UK.
  <https://www.legislation.gov.uk/ukpga/2018/12/contents>
- **US Gramm-Leach-Bliley Act (GLBA)** safeguards obligations for
  financial institutions.
  <https://www.ftc.gov/business-guidance/privacy-security/gramm-leach-bliley-act>
- **Brazil Lei Geral de Proteção de Dados (LGPD)** — Law No.
  13,709/2018.
  <https://www.planalto.gov.br/ccivil_03/_ato2015-2018/2018/lei/l13709.htm>
- **India Digital Personal Data Protection Act, 2023 (DPDP)** —
  including Section 16 on cross-border transfer.
  <https://www.meity.gov.in/writereaddata/files/Digital%20Personal%20Data%20Protection%20Act%202023.pdf>
- **Singapore Personal Data Protection Act (PDPA)** —
  <https://www.pdpc.gov.sg/overview-of-pdpa/the-legislation/personal-data-protection-act>
- **China Personal Information Protection Law (PIPL)** — including
  Articles 38–41 on cross-border personal information transfer;
  Cyberspace Administration of China (CAC) implementing measures.
  English translations vary; primary regulator is the CAC.
  <http://www.cac.gov.cn/> (CAC portal)
- **NIST AI Risk Management Framework (AI 100-1)**, and the
  Generative AI Profile (AI 600-1).
  <https://www.nist.gov/itl/ai-risk-management-framework>
- **ISO/IEC 42001:2023** — Artificial intelligence — Management
  system.
  <https://www.iso.org/standard/81230.html>
- **ISO/IEC 27001:2022** — Information security management systems.
  <https://www.iso.org/standard/27001>
- **AWS Well-Architected Framework**, **Google Cloud Architecture
  Framework**, **Microsoft Azure Well-Architected Framework** — as
  the "well-architected" bases from which regional and cross-cloud
  reasoning departs.
  - <https://aws.amazon.com/architecture/well-architected/>
  - <https://cloud.google.com/architecture/framework>
  - <https://learn.microsoft.com/azure/well-architected/>

Sector-specific supervisory expectations (PRA/FCA operational
resilience, EBA guidelines on outsourcing to cloud, MAS guidelines
on outsourcing risk management) are relevant to the financial-
services scenario but not required reading; the design cites them as
supervisory expectations rather than as text.

Related solutions in this repository:

- `projects/project-401-transformation-strategy/SOLUTION.md` —
  the transformation-strategy view that frames why a design like
  this is worth funding.
- `modules/mod-403-enterprise-governance/SOLUTION.md` — governance
  patterns that this design consumes.
- `modules/mod-406-global-infrastructure/SOLUTION.md` — the module
  view of the same problem space at coarser granularity.
- `modules/mod-405-responsible-ai/SOLUTION.md` — responsible-AI
  patterns that the AI-Act classification presumes.

## Time budget

- **Review-time read**: 30 minutes to read this SOLUTION plus
  `architecture/target-architecture.md`. This is the minimum to
  participate in a design review.
- **Full deliverable read**: 3–4 hours to read all artifacts
  (SOLUTION, architecture, rubric) with the referenced regulations
  open in a second tab.
- **Learner-side build**: a strong learner produces a defensible
  first draft in 20–30 hours of focused work, plus a further
  10–15 hours iterating after peer review.

## Status

**Version**: 1.0
**Status**: Reference solution
**Owner**: Senior Architect curriculum track
