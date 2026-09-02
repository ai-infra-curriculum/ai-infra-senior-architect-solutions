# Target-State Architecture — Global AI Platform

> Reference target architecture for Project 402. Companion to
> `../SOLUTION.md`. Read that document first for the reasoning; this
> document is the artifact a design review would work from.

## 1. Architectural principles

The design is anchored to seven principles. Every deviation from these
is expected to be justified explicitly in an ADR.

1. **Residency by policy, enforced by control.** Where data can live is
   defined once, in the policy engine, and enforced everywhere by
   compensating technical controls. Documents are not controls.
2. **One registry, one truth.** The model registry is the authoritative
   answer to "what is deployed where, and under what obligations."
   Governance claims that cannot be resolved from the registry are not
   yet operationalized.
3. **Global control plane, regional data plane.** Metadata flows to the
   center; regulated data does not.
4. **China is a peer cell, not a region.** Mainland China operates a
   parallel control plane, shares standards as artifacts, and
   synchronizes metadata (not payloads) with the global control plane.
5. **Two hyperscalers of record outside China.** Vendor concentration
   risk is priced explicitly; the design pays the cost of multi-cloud
   where the exposure warrants and does not where it does not.
6. **Portable artifacts, non-portable managed services.** Storage
   formats, model artifacts, and pipeline definitions are portable.
   Some managed services (identity, observability, orchestration) are
   deliberately not, and that choice is captured in ADRs.
7. **Reversibility drives sequencing.** The roadmap front-loads the
   cheap reversible decisions and back-loads the expensive committed
   ones.

## 2. Logical architecture

```
              ┌─────────────────────────────────────────────────────────┐
              │                GLOBAL CONTROL PLANE                     │
              │                                                         │
              │   ┌──────────────┐    ┌────────────────┐                 │
              │   │  Federated   │    │  Policy Engine │                 │
              │   │  Identity    │    │  (residency,   │                 │
              │   │  (SSO,       │    │  AI-Act,       │                 │
              │   │  ABAC/RBAC)  │    │  data class)   │                 │
              │   └──────┬───────┘    └────────┬───────┘                 │
              │          │                     │                         │
              │   ┌──────▼─────────────────────▼───────┐                 │
              │   │        Model Registry (SoT)        │                 │
              │   │   • Model card                      │                 │
              │   │   • Training data lineage           │                 │
              │   │   • Residency binding               │                 │
              │   │   • AI-Act classification           │                 │
              │   │   • Approvals + evidence            │                 │
              │   └──────┬─────────────────────┬───────┘                 │
              │          │                     │                         │
              │   ┌──────▼───────┐     ┌───────▼───────┐                 │
              │   │  Deployment  │     │  Audit / Obs  │                 │
              │   │  Orchestr.   │     │  Aggregation  │                 │
              │   │  (GitOps)    │     │  (metadata)   │                 │
              │   └──────┬───────┘     └───────┬───────┘                 │
              └──────────┼─────────────────────┼─────────────────────────┘
                         │                     │
     ┌───────────────────┼─────────────────────┼───────────────────┐
     │                   │                     │                    │
┌────▼────────┐   ┌──────▼────────┐    ┌───────▼─────────┐   ┌──────▼───────┐
│  EU CELLS   │   │  AMER CELLS   │    │  APAC ex-CN     │   │  CN CELL     │
│             │   │               │    │  CELLS          │   │              │
│  EU-C  EU-W │   │  US-E    BR   │    │  SG        IN   │   │  Shanghai +  │
│  UK         │   │               │    │                 │   │  Beijing     │
│             │   │               │    │                 │   │              │
│  Feature    │   │  Feature      │    │  Feature        │   │  Separate    │
│  store      │   │  store        │    │  store          │   │  registry    │
│  Training   │   │  Training     │    │  Training       │   │  Separate    │
│  Serving    │   │  Serving      │    │  Serving        │   │  policy eng. │
│             │   │               │    │                 │   │  Metadata    │
│  Cloud A+B  │   │  Cloud A+B    │    │  Cloud A+B      │   │  mirror only │
│             │   │  (BR: A only) │    │  (IN: A+B)      │   │              │
│             │   │               │    │  (SG: A+B)      │   │  Local       │
│             │   │               │    │                 │   │  partner A+B │
└─────────────┘   └───────────────┘    └─────────────────┘   └──────────────┘

Legend:
  • Cloud A / Cloud B = two hyperscalers of record (procurement decision,
    not a technical decision).
  • Local partner A / B = mainland-China cloud providers (e.g., Alibaba
    Cloud, Tencent Cloud, or a joint venture).
  • Metadata flows global; data does not.
```

## 3. Cell-by-cell allocation

### 3.1 EU-central (Frankfurt)

- **Purpose**: EU personal data (GDPR); EU AI Act high-risk workloads
  (credit scoring, employment analytics); EU-regulated marketing.
- **Cloud allocation**: Cloud A primary, Cloud B warm-standby.
- **Data classes hosted**: C0, C1, C2, C3 (EU-origin only).
- **Cross-region behavior**: C0/C1 may replicate to other EU cells.
  C2/C3 stay in-cell; cross-region replication only to EU-west for
  disaster recovery, over private interconnect, encrypted with EU-
  resident KMS keys.
- **Cross-border behavior**: C0/C1 may leave the EU under standard
  intra-group data transfer agreements. C2 leaves only under an
  approved transfer mechanism (SCCs, EU-US DPF, adequacy). C3 does
  not leave the EU.

### 3.2 EU-west (Dublin / Paris)

- **Purpose**: EU disaster recovery, latency backfill for EU-west
  customers, secondary for EU-central control-plane components.
- **Cloud allocation**: Same two hyperscalers.
- **Cross-region within EU**: allowed for all EU classes.
- **Cross-border**: none directly; egress goes through EU-central.

### 3.3 UK (London)

- **Purpose**: UK-only regulated workload footprint (PRA/FCA supervisory
  perimeter).
- **Cloud allocation**: Cloud A only. Cloud B optional Phase-2 add.
- **Rationale**: Adding a second UK hyperscaler doubles run-cost for a
  cell that is small in workload volume. The exit posture is instead
  "fail over to EU-central under approved transfer mechanism," which
  is a slower RTO but a defensible one.
- **Cross-border**: UK → US under UK IDTA (as applicable) or
  UK-adequacy mechanisms. UK → EU under UK-EU adequacy (as long as
  it is maintained). UK → other under case-by-case DPIA.

### 3.4 US-east (N. Virginia)

- **Purpose**: US retail, US regulated workloads (GLBA), UK data
  under approved mechanism.
- **Cloud allocation**: Cloud A primary, Cloud B warm-standby.
- **US-west cell**: not present in the reference. Added when latency
  requirements for US-Pacific customers become material, which the
  reference does not assume out of the gate.

### 3.5 BR (São Paulo)

- **Purpose**: Brazil retail (LGPD).
- **Cloud allocation**: Cloud A only. Cloud B optional.
- **Rationale**: Similar to UK — cell size does not justify dual-cloud
  cost. Exit posture: fail over to another Cloud A region under LGPD
  onward-transfer mechanism (SCCs).

### 3.6 IN (Mumbai / Hyderabad)

- **Purpose**: India retail (DPDP Act 2023). India KYC, credit,
  transaction data.
- **Cloud allocation**: Cloud A primary, Cloud B warm-standby.
- **Cross-border**: personal data of Indian data principals stays in
  India except to jurisdictions notified by the Central Government
  under DPDP Section 16. The allow-list can change; the design
  assumes it will and treats cross-border transfer as a runtime
  policy decision, not a design-time one.

### 3.7 SG (Singapore)

- **Purpose**: APAC hub for Singapore, Hong Kong, Australia, Japan,
  and other non-China, non-India APAC customers. Per-country policy
  applied at ingestion; PDPA-compliant at rest.
- **Cloud allocation**: Cloud A primary, Cloud B warm-standby.
- **Cross-border**: intra-group transfers under approved mechanisms
  per source country.

### 3.8 CN cell (Shanghai + Beijing)

- **Purpose**: Mainland China personal information (PIPL) and
  Chinese-market retail and commercial workloads.
- **Cloud allocation**: Local partner A primary; local partner B
  identified as secondary. No Western hyperscaler is used as
  primary or secondary for personal-information workloads.
- **Governance**: Separate registry instance, separate policy
  engine, separate audit store. Metadata (model identifiers,
  classification, deployment status) synchronizes to a metadata
  mirror outside China; payloads, weights, and training data do
  not.
- **Cross-border**: PIPL Articles 38–41 apply. Any cross-border
  personal-information transfer requires a Cyberspace
  Administration of China (CAC) assessment or the applicable SCCs
  under the CAC's cross-border SCC mechanism.
- **Operational integration**: the China-cell operations team is
  a separately staffed unit; on-call and incident response are
  local, escalation to global only for standards-and-policy
  questions.

## 4. Data plane

### 4.1 Storage layers

| Layer | Purpose | Format | Residency-tag propagation |
|---|---|---|---|
| **Raw / bronze** | Ingested-as-is, tagged at ingest | Provider-native object store | Yes; ingestion rejects untagged data |
| **Curated / silver** | Cleaned, joined, still regulated | Iceberg / Delta over object store | Yes; carried in table metadata |
| **Feature store — offline** | Feature values for training | Parquet + catalog | Yes; feature-set residency class = MAX of source residency classes |
| **Feature store — online** | Feature values for online inference | Regional key-value store | Yes; only features cleared for the serving region are materialized |
| **Model artifacts** | Weights, ONNX / TorchScript / container | Object store + registry pointer | Yes; artifact residency = registry-declared class |

### 4.2 Training plane

- Training clusters are regional. A training job's residency class is
  the MAX of the residency classes of its input datasets. Training
  jobs whose residency class does not permit the region are rejected
  by the orchestrator.
- Cross-region training on the same input class (e.g., an EU model
  trained on EU-central data using an EU-west GPU pool for capacity)
  is permitted within the same regulatory boundary.
- Cross-border training on C3 or C4 is not supported by the
  reference. Federated training for cross-border C3 is a Phase 4
  research topic and is not depended on for compliance.

### 4.3 Inference plane

- Online inference is regional. Requests from a region are served by
  the model instance in the region, using the online feature store in
  the region.
- Cross-region failover for online serving degrades gracefully — a
  request that fails in the primary region is served from the
  standby region **only if** the model's residency class permits
  that region; otherwise the request fails-closed with a defined
  error (which is preferable to a residency violation).
- Batch inference follows the same rules as training: it runs in the
  region of the data it operates on.

## 5. Control plane

### 5.1 Model registry (the source of truth)

Each registry entry carries:

- **Model identity**: name, version, hash of the artifact.
- **Owner**: team, service account, escalation contact.
- **Training data lineage**: pointer to the datasets used, with each
  dataset's residency class. Not the data itself — a lineage
  pointer.
- **Residency binding**: the residency class of the model, computed
  from the lineage. Determines which regions may host it.
- **AI-Act classification**: prohibited / high-risk / limited-risk /
  minimal-risk.
- **Evidence bundle**: for high-risk, the technical documentation,
  data-governance record, human-oversight design, transparency
  info, post-market monitoring plan, and conformity self-assessment
  (or notified-body assessment where applicable).
- **Deployment status**: which regions currently host this model
  version, under which endpoints.
- **Approvals**: sign-off history (owner, security, compliance,
  where applicable — legal / notified body).

The registry API refuses to promote a model to production in a
region unless: (a) the residency binding permits the region, (b)
the AI-Act classification's evidence bundle is complete for the
applicable use case, and (c) approvals are in date.

### 5.2 Policy engine

Policy is expressed as code and versioned. Three policy families:

- **Residency policy**: which classes can go where.
- **AI-Act classification policy**: how a use case is classified,
  and what obligations attach.
- **Data-class policy**: how a dataset is classified at ingestion,
  and what defaults its residency class inherits.

Policy is evaluated at three moments:

1. **At ingestion** — an untagged dataset cannot land.
2. **At training-job submission** — the orchestrator rejects a job
   whose residency class does not match the region.
3. **At promotion to production** — the registry gates the
   promotion.

Policy changes go through the same code review and audit trail as
platform code changes. Emergency policy changes have a documented
exception path with mandatory retrospective review.

### 5.3 Federated identity

- SSO across all cells except the China cell.
- Service identity federation between control plane and each data
  plane (workload-identity-federation-style; short-lived credentials
  rather than long-lived secrets).
- The China cell has its own identity plane; a small number of
  designated global standards-authors have accounts in both.
  Cross-plane access is audited.

### 5.4 Deployment orchestrator

- GitOps-style. Desired state lives in Git; actual state is
  reconciled.
- The orchestrator itself holds no personal data. It holds
  configuration, not payload.
- Blue/green + canary as the default rollout pattern for online
  models; shadow deployment supported for high-risk models where
  it materially aids monitoring.

### 5.5 Observability aggregation

- Regional observability stores hold raw logs (including anything
  that could contain personal data).
- The global aggregation surface holds metadata only — model IDs,
  event counts, latency histograms, error rates by category — and
  does not pull raw log content across borders.
- Alerting is regional-first; escalation to global is by summary,
  not by raw log.

### 5.6 Audit log aggregation

- Every policy decision, registry promotion, and cross-border
  transfer approval is recorded to an immutable audit store.
- Retention is set to the maximum of all applicable statutory
  minimums (see `../rubric/evaluation-rubric.md` for how graders
  test this).
- Audit is aggregated globally as metadata (event happened at time
  T for entity E), with the payload retained regionally.

## 6. Networking

### 6.1 Global topology

- **Primary interconnect**: private backbone from each cell to the
  control plane on Cloud A, with a parallel path on Cloud B for
  control-plane failover.
- **Data-plane egress from a cell** is restricted by policy at the
  cell edge. C3 egress is not routable.
- **Cross-region within a regulatory boundary** (e.g., EU-central ↔
  EU-west) uses provider-managed private interconnect where
  available; falls back to VPN over private peering elsewhere.
- **China cell** is not on the same private backbone. Metadata
  synchronization uses a signed, rate-limited channel; there is no
  general-purpose network path from the CN cell to the global
  control plane.

### 6.2 Edge / CDN

- CDN is used for public model-serving traffic where residency
  permits (largely C0/C1 content, or C2 responses when the response
  itself is not identifying).
- Edge inference is out of scope for the reference target;
  documented in the roadmap as a Phase 4 extension for latency-
  sensitive workloads.

### 6.3 Interconnect between cells

- **EU cells to each other**: private interconnect, EU-only routing.
- **US cell to EU cell**: private interconnect, transfer subject to
  policy engine at the cell edge; personal-data transfer requires
  the relevant mechanism (SCC / DPF / adequacy).
- **APAC ex-CN cells to each other and to hub**: private
  interconnect where the intra-group agreements permit; per-country
  policy at ingestion.
- **CN cell**: metadata channel only. No data-plane interconnect.

## 7. Operations

### 7.1 Staffing model (reference sizing)

The reference target is designed to be operable at the scale of a
large enterprise, not at hyperscaler-native staffing levels. Steady-
state estimates (post Phase 3):

| Function | Global HQ | Per non-CN cell | CN cell |
|---|---|---|---|
| **Platform engineering** | ~15 | ~2 | ~4 |
| **SRE / on-call** | ~6 | follow-the-sun rotation | ~3 (local) |
| **ML platform / registry** | ~6 | shared | shared |
| **Security & policy engineering** | ~4 | ~1 | ~2 |
| **Compliance & governance** | ~4 | ~1 | ~2 |
| **Program & product** | ~4 | shared | shared |

Actual sizing depends on workload volume; the numbers above are the
"below this, the platform is not honestly operable" floor. A design
that assumes less needs to specify what it is trading off (usually:
on-call burden, or governance response time).

### 7.2 Incident response

- Regional incidents handled by regional on-call.
- Cross-regional incidents (control-plane failures, cross-cell
  policy misconfiguration) handled by global on-call, with regional
  leads on the bridge.
- CN-cell incidents handled by the CN team; global visibility is
  via post-incident summary, not real-time bridge (this is an
  operational compromise driven by the cross-border rules on
  incident-related data).

### 7.3 Change management

- Platform changes flow through GitOps; approvals codified in
  CODEOWNERS.
- Registry schema changes require a versioned migration and a
  policy engine dry-run.
- Policy changes have a change-advisory-board (CAB) equivalent for
  material changes; minor operational changes flow through the
  standard code-review path.

## 8. Vendor and exit posture

### 8.1 Multi-cloud, priced

Multi-cloud is deployed at:

- **Global control plane** — Cloud A primary, Cloud B warm-standby.
  This is where the cost is worth paying: control-plane outage is
  a global platform outage.
- **EU-central, US-east, IN cells** — the largest cells by workload
  volume, and the ones with the most regulatory exposure. Multi-
  cloud here reduces vendor concentration where it matters.
- **UK, BR** — single cloud with a documented failover posture. The
  smaller-cell exposure does not justify the run-cost of a second
  hyperscaler footprint.

### 8.2 China: local partners, portable artifacts

- Two Chinese cloud partners identified (primary + secondary).
- Data plane and control plane both run on the primary; failover to
  secondary is exercised on a defined cadence.
- Model artifacts are portable across the two partners; feature
  store implementations may differ, which is captured as a
  documented risk.

### 8.3 Exit paths

For each cell, the design records:

- Which managed services are in use.
- What the portable equivalent is on the alternate cloud.
- The engineering effort to switch (person-quarters).
- The RTO for a forced exit (sanctions, provider withdrawal).

<!-- needs-research: sector-specific supervisor expectations on
"stressed exit" RTO for cloud in the financial-services scenario —
PRA supervisory statement SS2/21 and MAS notices differ in
detail — needs a compliance workstream to confirm the specific
numbers cited in the risk register -->

## 9. ADRs (index)

The reference solution includes decision records that a design
review should be able to trace. In an actual submission, each ADR
is a short document (title, context, decision, consequences).

- **ADR-001** — Global control plane, regional data plane.
- **ADR-002** — Model registry as source of truth for governance.
- **ADR-003** — China as a peer cell, not a region.
- **ADR-004** — Two hyperscalers globally; single-cloud in smaller
  cells with documented failover.
- **ADR-005** — Storage formats standardized on open table formats
  (Iceberg / Delta), model artifacts standardized on portable
  formats.
- **ADR-006** — AI-Act classification carried in the registry.
- **ADR-007** — Policy-as-code; three enforcement points (ingest,
  submit, promote).
- **ADR-008** — Roadmap sequenced by reversibility; registry
  first, migration last.
- **ADR-009** — Sponsor-independence design; the architecture does
  not depend on any named executive for correctness.
- **ADR-010** — Federated training deferred; no compliance path
  currently depends on it.

## 10. Diagram legend and conventions

- **Solid arrows** denote data flow.
- **Dashed arrows** denote metadata flow.
- **Colored region boundaries** denote regulatory boundaries; each
  cross-boundary arrow is labeled with the transfer mechanism.
- **Cell** = a governance unit; may span multiple cloud regions of
  the same jurisdiction.
- **Region** = a cloud provider region within a cell.
- **SoT** = source of truth.

## 11. Known open items

Items marked `needs-research` in the SOLUTION and here are the ones
that block sign-off on the reference and would be researched during
a real design phase:

- Sector-specific stressed-exit RTOs for the FS scenario (PRA
  SS2/21, MAS, HKMA differ; the reference does not commit to a
  single number).
- Latest CAC guidance on cross-border personal-information transfer
  mechanisms; the design assumes the current CAC SCC path and
  standard assessment thresholds, and would be re-checked at
  build-time.
- Practical DPDP Section 16 allow-list content as of the design
  date; the reference treats it as runtime-configurable, but the
  initial value at build-time needs Legal to state.

None of these change the shape of the architecture. All would
change specific numeric commitments in the risk register.
