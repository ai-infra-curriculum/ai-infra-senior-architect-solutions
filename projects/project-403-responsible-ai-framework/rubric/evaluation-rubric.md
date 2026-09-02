# Evaluation Rubric — Project 403: Responsible AI Framework

> Grading guide for Project 403 submissions. Companion to
> `../SOLUTION.md`, `../framework/responsible-ai-framework.md`, and
> `../governance/ethics-board-charter.md`. The rubric weights
> **enforceability of claims** above **breadth of principles**. A
> submission that publishes a large number of principles and enforces
> none scores below a submission that publishes fewer principles and
> can point at the control enforcing each one.

## How to use this rubric

- Score each of the six weighted dimensions on a 0–100 scale.
- Compute the weighted total.
- Apply the two floor rules (inventory and bias/explainability
  enforceability) as pass/fail overrides.
- Record justification against each dimension. Grader disagreement
  above 10 points on any single dimension is resolved by a second
  grader before returning the score.

## Weighting

| Dimension | Weight |
|---|---:|
| 1. Inventory and taxonomy defensibility | 20% |
| 2. EU AI Act operationalization | 20% |
| 3. Bias and explainability enforceability | 15% |
| 4. Ethics Board charter defensibility | 15% |
| 5. Board oversight and public transparency | 15% |
| 6. Regulatory roadmap sequenced by reversibility | 10% |
| 7. Documentation quality, cross-artifact consistency, named-role-independence | 5% |
| **Total** | **100%** |

## Floor rules (pass/fail)

- **Inventory floor.** A submission scoring below 60 on
  Dimension 1 is non-passing regardless of the total. A learner
  who cannot show a single named artifact that resolves "what do
  we operate?" has not demonstrated the level.
- **Enforcement floor.** A submission scoring below 60 on
  Dimension 3 is non-passing regardless of the total. A learner
  who does not show fairness and explainability being enforced
  at deployment-time has published aspirations, not a framework.

## Dimension 1 — Inventory and taxonomy defensibility (20%)

**What the grader is looking for**: the submission designates a
single named artifact — a model registry, an AI system inventory,
an equivalently-named object — as the source of truth for "what
we operate." The artifact carries the fields required for
downstream governance claims. Registration is a precondition to
deployment, not a paperwork step after the fact.

**Scoring anchors**:

- **90–100** — Named registry with a documented schema. Fields
  include identity, ownership (by role, not person), purpose,
  data lineage pointer, regulatory classification across
  jurisdictional overlays, NIST AI RMF function coverage,
  fairness declaration, explanation strategy, human-oversight
  design, post-market monitoring plan, approvals log. Registration
  is a gate: deployment cannot bypass it. Change management is
  in place: material change re-enters approval. Vendor and
  foundation-model-based systems are in scope with the same
  registration.
- **75–89** — Registry with a documented schema. Most fields
  present; a few (e.g., NIST profile, state-law overlay) thin.
  Registration is a gate for most classes but perhaps with
  documented exceptions.
- **60–74** — Inventory exists as a spreadsheet or ticket
  system. Schema is not enforced. Registration is a workflow
  step rather than a gate.
- **40–59** — Inventory mentioned; no schema; no clear source
  of truth; multiple candidate artifacts with no reconciliation.
- **0–39** — "We inventory our AI" without a named artifact.

**Automatic deductions**:

- **−15** if the framework acknowledges multiple sources of
  truth (registry, tickets, spreadsheet, Confluence page) with
  no stated reconciliation.
- **−15** if procured / vendor AI is silently out of scope.

## Dimension 2 — EU AI Act operationalization (20%)

**What the grader is looking for**: the submission does not merely
mention the AI Act; it operationalizes the classification in the
registry, requires the evidence bundle at promotion for high-risk
systems, refuses prohibited-category registrations, and surfaces
Article 50-equivalent transparency obligations for limited-risk
systems.

**Scoring anchors**:

- **90–100** — Classification is a registry field. Prohibited
  category is refused at registration and escalated. High-risk
  evidence bundle is enumerated (risk-management record, data-
  governance record, technical documentation, logging /
  traceability, transparency information, human-oversight design,
  accuracy/robustness/cybersecurity evidence, conformity-assessment
  record, post-market monitoring plan) and enforced at promotion.
  Limited-risk transparency configuration is checked. Post-market
  monitoring is architected, not deferred. Notified-body vs.
  self-assessment distinction is at least acknowledged.
- **75–89** — Classification in registry. Evidence bundle
  enumerated; enforcement at promotion mostly wired. Post-market
  monitoring named.
- **60–74** — Classification named. High-risk obligations
  listed. Enforcement is described as policy, not as control.
- **40–59** — AI Act cited as a general compliance concern; no
  connection to specific platform behaviors.
- **0–39** — No AI Act treatment, or the submission conflates
  the AI Act with GDPR.

**Automatic deductions**:

- **−15** if the submission treats "high-risk" as a label
  without enumerating the obligations that attach to it.
- **−10** if the submission does not address prohibited-category
  handling at all.

## Dimension 3 — Bias and explainability enforceability (15%)

**What the grader is looking for**: fairness is declared per
system before deployment and evidenced at evaluation.
Explainability is designed per audience and produced as a
side-effect of evaluation, not on regulator request.
Monitoring is wired for both. The registry gate blocks
promotion when the required declarations, evaluations, and
monitoring are not in place.

**Scoring anchors**:

- **90–100** — Fairness declaration is a registry field with a
  documented per-system rationale. The framework acknowledges
  that different fairness definitions are mathematically
  incompatible and requires an argued choice, not a house
  metric. Monitoring is wired with named thresholds and named
  responses. Explainability is designed for four audiences
  minimum (individual, reviewer, regulator, governance) with
  named methods and persistence. Explanation quality itself is
  monitored. Registry gate blocks promotion if any of the
  required artifacts are missing.
- **75–89** — Fairness declared. Some rationale requirement.
  Explainability audience-designed. Monitoring named.
- **60–74** — Fairness metric named at framework level (one
  house metric). Explainability treated as a documentation
  requirement rather than a first-class artifact.
- **40–59** — Fairness and explainability listed as principles
  without connection to platform behavior.
- **0–39** — Fairness / explainability as trust statements only.

**Automatic deductions**:

- **−15** if the framework mandates one fairness metric
  across-the-board without acknowledging incompatibility.
- **−15** if explainability is described as report-on-request
  rather than routine artifact.

## Dimension 4 — Ethics Board charter defensibility (15%)

**What the grader is looking for**: the AI Ethics Board has a
written charter that scopes composition, quorum, authority,
dissent recording, external members, cadence, and effectiveness
review. The Board's authority is split into binding and advisory
with named classes; binding is narrow and specific, advisory is
where advice-with-visibility is enough.

**Scoring anchors**:

- **90–100** — Charter names composition (with at least two
  external members and independence tested annually), quorum,
  standing agenda, binding authority on named classes (high-risk
  registration/promotion; fairness/explainability overrides;
  transparency exceptions; interim classification of emerging
  capabilities), advisory authority on named classes, dissent
  recording with automatic escalation triggers, annual external
  effectiveness review, escalation path to Board Risk Committee.
  Charter distinguishes what the Board is and is not.
- **75–89** — Charter present; most sections; some scope items
  thin (e.g., dissent recording named but escalation triggers
  vague).
- **60–74** — Charter present as an outline. Authority not
  scoped (either "advisory to leadership" without teeth, or
  "governance body running the programme" without limit).
- **40–59** — Ethics Board mentioned; no written charter.
- **0–39** — Ethics Board as an aspirational body without any
  operational definition.

**Automatic deductions**:

- **−15** if the Board has no external members.
- **−10** if the Board's authority is unbounded ("Ethics Board
  decides all AI matters") or vacuous ("Ethics Board advises
  leadership") without named classes.

## Dimension 5 — Board oversight and public transparency (15%)

**What the grader is looking for**: Board Risk Committee and
Audit Committee packs are produced on a defined cadence from
platform records, not from slides. The public transparency
report is produced from the same records. Escalation
thresholds are stated numerically or categorically. Exceptions
to public disclosure are policy, not judgement-per-case.

**Scoring anchors**:

- **90–100** — Board Risk Committee pack content defined and
  segmented into automatically-produced and manually-authored
  fields. Audit Committee pack defined. Escalation thresholds
  stated. Public transparency report content defined; cadence
  defined; production pipeline defined (scheduled job over
  registry and monitoring records); exceptions policy defined
  and enforced. Manual-assembly of packs identified as a
  control smell.
- **75–89** — Board pack and public report defined; some
  fields still manually assembled without articulated smell.
- **60–74** — Reports mentioned without a production pipeline
  ("we will report to the Board quarterly") — treated as an
  intent, not a control.
- **40–59** — Reporting listed as an obligation without
  content.
- **0–39** — No reporting model.

**Automatic deductions**:

- **−10** if the Board pack is described as slide assembly per
  cycle with no linkage back to platform records.
- **−10** if the public transparency report is described in
  marketing-brochure terms rather than as producible from
  records.

## Dimension 6 — Regulatory roadmap sequenced by reversibility (10%)

**What the grader is looking for**: Phase 0 is the read-only
observatory; new deployment gates come in Phase 1; backfill of
existing systems is Phase 2; external review is Phase 3.
Regulatory drift is absorbed as policy update, not as a rewrite
per landing.

**Scoring anchors**:

- **90–100** — Phase 0 registry-as-observatory, no migration
  commitment. Phase 1 Ethics Board chartered, new deployments
  gated. Phase 2 backfill on a defined schedule; unmet backfill
  freezes material change. Phase 3 external review and first
  public report. Phase 4 optimization and drift absorption.
  Regulatory drift explicitly treated as policy update rather
  than framework rewrite.
- **75–89** — Phased plan present. Registry-first present.
  Sequence broadly reversibility-ordered but not always
  articulated as such.
- **60–74** — Phased plan by activity (inventory → gate →
  report) rather than by reversibility. Regulatory drift
  handling implicit.
- **40–59** — A Gantt exists; no sequencing rationale.
- **0–39** — No roadmap.

## Dimension 7 — Documentation, consistency, named-role-independence (5%)

**What the grader is looking for**: the submission's artifacts
agree with each other; roles are named as roles, not as people;
the framework survives leadership rotation.

**Scoring anchors**:

- **90–100** — README, SOLUTION-equivalent, framework artifact,
  charter, and rubric-equivalent are internally consistent.
  Every accountability in the framework is a role. The
  submission explicitly discusses how leadership rotation is
  handled.
- **75–89** — Consistent artifacts. Named roles predominantly.
  Rotation handled implicitly.
- **60–74** — Documents present; small inconsistencies (e.g.,
  Ethics Board quorum stated differently in two places).
- **40–59** — Documents sparse or contradictory.
- **0–39** — Documentation aspirational only.

**Automatic deductions**:

- **−10** if any accountability is a named person rather than
  a role.

## Anti-patterns (automatic deductions apply where noted)

The following are common submission failure modes. Any appearing
in a submission requires the grader to note it in the scoring
justification; automatic deductions above apply where listed.

1. **Twelve principles, zero controls.** A framework that
   publishes twelve virtues and enforces none. Grader notes in
   Dimension 3 justification.
2. **Inventory as a spreadsheet.** See Dimension 1 automatic
   deduction.
3. **One fairness metric across the board.** See Dimension 3
   automatic deduction.
4. **Explainability as report-on-request.** See Dimension 3
   automatic deduction.
5. **Ethics Board with no charter.** See Dimension 4.
6. **Ethics Board with unbounded or vacuous authority.** See
   Dimension 4 automatic deduction.
7. **Board packs assembled manually.** See Dimension 5
   automatic deduction.
8. **Public transparency report as marketing brochure.** See
   Dimension 5 automatic deduction.
9. **Named-person dependencies.** See Dimension 7 automatic
   deduction.
10. **Regulatory drift ignored.** A framework tuned exactly to
    one regulator's guidance as of one date, with no absorption
    model for the next landing. Grader notes in Dimension 6.

## Grader worksheet

For each submission, produce:

- **Dimension scores** (seven numeric scores).
- **Floor-rule results** (inventory floor: pass/fail;
  enforcement floor: pass/fail).
- **Weighted total**.
- **Justification per dimension** (2–4 sentences each).
- **Notable strengths** (2–3 items).
- **Highest-value improvement** (one item, phrased actionably).

Return the worksheet with the score. As with Project 402, the
single highest-value improvement is often more valuable than
the score itself and is the item to prioritize in written
feedback.

## Reference calibration

Two calibration points for graders:

- The reference solution in `../SOLUTION.md` +
  `../framework/responsible-ai-framework.md` +
  `../governance/ethics-board-charter.md` is designed to score
  **90+** on Dimensions 1–5 and **~85** on Dimensions 6–7
  (deliberate `needs-research` items prevent a 95+ on
  documentation).
- A submission that copies the reference framework structure
  but cannot answer the operational dry-runs from SOLUTION §3
  should score **~65** on Dimensions 1 and 3 — the shape is
  right, but the enforceability is missing.

Grader disagreement between "the shape is right" and "the
enforceability is missing" is common. When in doubt, run one
of the operational dry-runs with the learner present and score
based on the answers they can produce from the artifacts they
submitted.
