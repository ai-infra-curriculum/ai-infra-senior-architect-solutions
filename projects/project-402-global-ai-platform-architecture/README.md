# Project 402: Global AI Platform Architecture

> Senior-architect capstone. The learner submits a target-state architecture
> for a global AI/ML platform that must serve regulated markets on three
> continents, with residency, sovereignty, and reliability constraints that
> a single-region design cannot satisfy.

## Scenario (fictional)

**NorthWave Financial Group** is a fictional multinational retail-and-
commercial bank operating in the EU, the United States, the United Kingdom,
Brazil, India, Singapore, and mainland China. Total assets under management
and product mix are illustrative only; the scenario exists to force
concrete regional trade-offs.

The bank has three existing pockets of AI/ML capability:

1. **EU platform** — a legacy on-prem cluster in Frankfurt running risk
   models and marketing-analytics workloads. Owned by the CRO's org.
   Batch-only.
2. **US platform** — a hyperscaler-hosted SageMaker footprint in
   `us-east-1`, added when the retail-analytics team was acquired. Owned
   by the CMO's org. Batch + low-volume online scoring.
3. **APAC platforms** — three separately built stacks (Singapore, Mumbai,
   Shanghai), owned by regional CTOs. Inconsistent governance, no shared
   data plane, no shared model registry.

Group Executive has approved the design phase of a **single global AI
platform** and asked the AI Infrastructure Architect (the learner) to
produce a target architecture, a residency-and-sovereignty policy, and
an execution roadmap. Funding for build is contingent on this design
review.

## The problem statement (what a senior architect is being asked to solve)

Design a global AI platform such that:

1. **Regulated data stays in-region.** EU personal data is bound by GDPR;
   Chinese personal information is bound by PIPL; Indian personal data is
   bound by DPDP Act 2023; US and UK add sectoral rules (GLBA, PRA/FCA);
   Brazil is bound by LGPD. In several of these jurisdictions the
   controller model materially restricts cross-border transfer.
2. **A single control plane governs all regions.** Model registry, policy
   engine, IAM, and audit are unified. The data plane is regional; the
   control plane is not.
3. **The platform is defensible under the EU AI Act.** High-risk AI
   systems (credit scoring, fraud detection, employment) are identifiable
   at inventory time, and the platform enforces the obligations that
   attach to that classification.
4. **Multi-cloud is a first-class constraint**, not a slide. Mainland
   China requires a local partner (Alibaba Cloud, Tencent Cloud, or a
   joint venture) and cannot use most Western-headquartered hyperscaler
   accounts directly. The rest of the world runs on two hyperscalers for
   supplier-concentration reasons flagged by the Group Risk Committee.
5. **The platform is operationally coherent.** One deployment interface,
   one monitoring surface, one incident-management workflow, even when
   the underlying compute is heterogeneous.

## Deliverables the learner submits

1. **Target-state architecture** (`architecture/target-architecture.md`
   or equivalent). Data plane, control plane, model plane, region layout,
   cloud allocation, and interconnect topology. Must include an
   authoritative diagram or equivalent structured description.
2. **Data-residency-and-sovereignty policy** (typically a section within
   the architecture document, or a standalone artifact). Data
   classification, allowed regions per class, allowed egress patterns,
   and the enforcement mechanisms that make the policy operational
   (not aspirational).
3. **Regional strategy** (which markets run on which providers, why, and
   what escape hatches exist if a provider fails or is sanctioned).
4. **Roadmap** (24-36 month execution plan, sequenced by reversibility;
   see `SOLUTION.md` for the reasoning behind this ordering).
5. **Governance and controls** (how the platform surfaces the EU AI Act
   high-risk classification, how the model registry gates deployment,
   how audit evidence is produced).
6. **Risk register** (top 10 risks with probability, impact, mitigation,
   and residual risk; must include vendor concentration, sanctions
   exposure, data-transfer regulatory change, and control-plane
   availability).

## Explicitly out of scope

- **Model selection or algorithm design.** The learner is designing a
  platform, not a portfolio.
- **Business case in dollars.** A senior architect cites the shape of
  the value, but sizing is a finance workstream, not an architecture
  deliverable. (Contrast with Project 401, which is the finance
  workstream.)
- **Vendor negotiation and pricing.** Named vendors are examples;
  procurement is a separate workstream.
- **Detailed CI/CD tool selection.** Categories are named (registry,
  feature store, orchestrator) with selection criteria; tool choice is
  the platform-build phase.

## What "senior architect quality" means for this project

A junior submission answers "what cloud, what tools, what region." A
senior submission answers the same questions, and then explains **why
those answers survive**:

- **Under the specific regulations named**, not "compliance" as a
  hand-wave.
- **Under vendor failure**, including the possibility of a hyperscaler
  being sanctioned or exiting a market.
- **Under organizational change** — the sponsor rotating, the CRO
  disagreeing with the CMO on ownership, a business unit refusing to
  migrate.
- **Under audit** — the architecture produces the artifacts a regulator
  asks for without a heroic engineering effort.

The reference solution in `SOLUTION.md` is not a scoring key with a
single right answer. It's a set of trade-offs a senior architect should
be able to defend on their feet in a design review.

## Evaluation

See `rubric/evaluation-rubric.md` for the scoring rubric. The rubric
weights *defensibility of trade-offs* above *architectural cleverness*.
A learner who picks the same target architecture as a competitor but
cannot defend their residency policy under DPDP will score below a
learner who chose a slightly clumsier architecture but can defend every
choice against regulatory change.

## Reading order

1. `README.md` (this file) — the scenario and the ask.
2. `SOLUTION.md` — the senior-architect reasoning that the reference
   design encodes.
3. `architecture/target-architecture.md` — the reference target state.
4. `rubric/evaluation-rubric.md` — the scoring rubric graders use.

## Version

**Version**: 1.0
**Status**: Reference solution
**Owner**: Senior Architect curriculum track
