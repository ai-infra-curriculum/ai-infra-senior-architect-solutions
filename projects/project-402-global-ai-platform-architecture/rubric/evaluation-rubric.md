# Evaluation Rubric — Project 402: Global AI Platform Architecture

> Grading guide for Project 402 submissions. Companion to
> `../SOLUTION.md` and `../architecture/target-architecture.md`.
> The rubric weights **defensibility of trade-offs** above
> **architectural cleverness**. A design that quietly satisfies the
> checks scores higher than one that clearly cites patterns but does
> not connect them to the scenario constraints.

## How to use this rubric

- Score each of the five weighted dimensions on a 0–100 scale.
- Compute the weighted total.
- Apply the two floor rules (residency and registry-as-SoT) as
  pass/fail overrides.
- Record justification against each dimension. Grader disagreement
  above 10 points on any single dimension is resolved by a second
  grader before returning the score.

## Weighting

| Dimension | Weight |
|---|---:|
| 1. Residency and sovereignty defensibility | 25% |
| 2. Control-plane vs. data-plane split | 20% |
| 3. EU AI Act operationalization | 15% |
| 4. Vendor concentration and exit posture | 15% |
| 5. Roadmap sequenced by reversibility | 15% |
| 6. Documentation quality, diagram correctness, cross-artifact consistency | 10% |
| **Total** | **100%** |

## Floor rules (pass/fail)

- **Residency floor.** A submission scoring below 60 on Dimension 1
  is non-passing regardless of the total. A learner who cannot
  defend residency in a globally-regulated workload has not
  demonstrated the senior-architect level.
- **Registry floor.** A submission whose governance claims cannot be
  resolved from a single named artifact (the model registry, or an
  equivalent named object) is non-passing. Governance-by-spreadsheet
  does not clear the level.

## Dimension 1 — Residency and sovereignty defensibility (25%)

**What the grader is looking for**: the submission's residency policy
is not a paragraph. It is a policy expressed against a named data
classification, tied to specific regulations, and enforced by
specific technical controls named in the design.

**Scoring anchors**:

- **90–100** — Data classes explicitly named. Every class is bound to
  a region set that is defensible under the specific regulation
  cited (GDPR, PIPL, DPDP, LGPD, GLBA, PDPA, UK DPA). Enforcement is
  named at three or more levels of the stack (ingestion, storage
  IAM, egress, registry gates). China is treated as a peer cell
  (separate policy authority), not as a region on the main plane.
  The submission traces at least two of the regulatory dry-runs from
  the SOLUTION §3 (or equivalents).
- **75–89** — Data classes present. Cross-border and cross-region
  rules present. Enforcement named at one to two levels of the
  stack. China treated correctly at the architectural level but
  perhaps with hand-waving on operational separation.
- **60–74** — Data classes present but generic; the specific
  regulations are named but not connected to specific controls.
  Enforcement is described as policy, not as control. China is
  treated as "another region."
- **40–59** — Residency mentioned; specific regulations cited
  without the specific obligations they impose. No named
  enforcement mechanism.
- **0–39** — "Compliance" as a hand-wave. No data classification,
  no residency controls, no jurisdictional distinctions.

**Automatic deductions**:

- **−20** if the submission's control plane holds personal data at
  rest anywhere (including in logs, observability, or caches). This
  is a design defect, not a policy defect.
- **−20** if the submission proposes cross-border replication of
  C3-equivalent data by default (rather than as a specific,
  policy-gated case).

## Dimension 2 — Control-plane vs. data-plane split (20%)

**What the grader is looking for**: the submission distinguishes
control plane from data plane; the split is coherent; the model
registry is the source of truth for governance claims.

**Scoring anchors**:

- **90–100** — Control plane and data plane are named as distinct
  concerns with distinct residency properties. The model registry is
  the authoritative object for "what is deployed where, and under
  what obligations." The registry gates deployment; deployment
  cannot silently drift from the registry state. Metadata-vs.-data
  distinction is preserved end-to-end (observability aggregation,
  audit aggregation, cross-cell mirrors).
- **75–89** — Control-plane / data-plane split present. Registry
  role is called out but perhaps not every governance claim ties
  back to it. Metadata-only aggregation named but not universally
  applied.
- **60–74** — Split is present as a diagram element but not as a
  policy. Registry is one system among several; some governance
  claims live in other systems that are not clearly reconciled.
- **40–59** — Split is not present or is nominal only.
- **0–39** — "Central platform" as a monolith with no articulated
  control-plane discipline.

**Automatic deductions**:

- **−15** if the submission has multiple sources of truth for
  "what is deployed" (e.g., registry says one thing, GitOps repo
  says another, orchestrator says a third, with no stated
  reconciliation).

## Dimension 3 — EU AI Act operationalization (15%)

**What the grader is looking for**: the submission does not just
mention the AI Act; it operationalizes the classification in the
platform.

**Scoring anchors**:

- **90–100** — AI-Act classification carried in the registry.
  Registry refuses to promote a high-risk model without the
  evidence bundle (technical documentation, data-governance
  record, human-oversight design, transparency information,
  post-market monitoring plan, conformity assessment). Prohibited
  classifications are refused at registration. Limited-risk
  transparency obligations are surfaced. Post-market monitoring
  is architected, not deferred.
- **75–89** — Classification carried in the registry. Evidence
  requirements enumerated but perhaps not all enforced. Post-
  market monitoring named.
- **60–74** — Classification mentioned. High-risk obligations
  listed. No enforcement in the registry or orchestrator.
- **40–59** — AI Act cited as a general compliance concern; no
  connection to specific platform behaviors.
- **0–39** — No AI Act treatment, or the submission conflates the
  AI Act with GDPR.

## Dimension 4 — Vendor concentration and exit posture (15%)

**What the grader is looking for**: multi-cloud is priced
explicitly. The design pays for multi-cloud where the exposure
warrants and does not pay for it where it does not. Exit paths
are specific.

**Scoring anchors**:

- **90–100** — Two hyperscalers named as "of record" outside China.
  China treated with two local partners. Multi-cloud deployed at
  the control plane and at large-exposure cells; single-cloud in
  smaller cells with a documented exit RTO. Portable artifacts
  named (open table formats, portable model formats). Non-
  portable managed services named as such and justified.
- **75–89** — Multi-cloud stance is defined. China posture is
  correct. Portable artifacts named. Some cells' multi-cloud vs.
  single-cloud rationale is thin.
- **60–74** — Multi-cloud mentioned at the whole-platform level
  (either "everywhere" or "nowhere"). Portability discussed
  generically.
- **40–59** — Single-cloud submission that does not acknowledge
  vendor-concentration risk. Or an everywhere-multi-cloud
  submission that does not price it.
- **0–39** — Vendor exposure not addressed.

**Automatic deductions**:

- **−15** if the submission proposes running the mainland-China
  workload on a Western hyperscaler.
- **−10** if the submission proposes multi-cloud but does not name
  what the failover exercise looks like (a warm-standby that is
  never exercised is not a mitigation).

## Dimension 5 — Roadmap sequenced by reversibility (15%)

**What the grader is looking for**: early phases are cheap to
reverse; late phases are the ones with real commitment; the
sequencing buys information for the harder decisions.

**Scoring anchors**:

- **90–100** — Phase 0 stands up the registry as a *read-only*
  observatory over existing platforms; no migration commitment is
  made before governance is operational. Phase 1 builds the
  control plane. Regional data-plane migration is later. China
  cell is a parallel workstream, not blocking. Retirement of
  legacy systems is the last phase and is gated on the last
  workload actually migrating. Sponsor-rotation risk is addressed
  in Phase 0.
- **75–89** — Phases are named and sequenced. Registry-first is
  present. China treated as parallel. Sponsor-independence
  acknowledged.
- **60–74** — A phased plan exists but the sequencing is by
  activity (build → migrate → optimize) rather than by
  reversibility. Registry is not obviously first.
- **40–59** — A Gantt chart exists; no sequencing rationale.
- **0–39** — No roadmap, or a big-bang migration proposed.

## Dimension 6 — Documentation, diagrams, cross-artifact consistency (10%)

**What the grader is looking for**: the submission's artifacts
agree with each other; diagrams name the data flowing on each
arrow; ADRs cover the material decisions.

**Scoring anchors**:

- **90–100** — README, SOLUTION-equivalent, architecture doc, and
  rubric-equivalent are internally consistent. Diagrams annotate
  arrows with residency class and transfer mechanism. ADRs cover
  the ten decisions from the reference (or equivalents).
- **75–89** — Consistent artifacts; diagrams present; some ADRs.
- **60–74** — Documents present; small inconsistencies (e.g.,
  registry described one way in one doc and differently in
  another); diagrams present but not annotated.
- **40–59** — Documents are sparse or contradict each other.
- **0–39** — Documentation is aspirational only.

## Anti-patterns (automatic deductions apply where noted)

The following are common submission failure modes. Any of them
appearing in a submission requires the grader to note it in the
scoring justification; the automatic deductions above apply where
listed.

1. **"Multi-region" mistaken for "global-compliant."** Multiple
   regions in the same regulatory boundary is not a global
   design. Grader notes this in Dimension 1 justification.
2. **Control plane holds personal data.** Design defect. See
   Dimension 1 automatic deduction.
3. **China modeled as `cn-north-1`.** Not a region; a peer cell.
   See Dimension 4 automatic deduction.
4. **AI-Act classification in a spreadsheet.** Not a control. See
   Dimension 3.
5. **Cost-optimizing the region layout in Phase 1.** Governance
   comes first. See Dimension 5.
6. **Multi-cloud everywhere or nowhere.** Neither is a decision.
   See Dimension 4.
7. **Sponsor-dependent design.** A platform that only works while
   the current CDO is in seat is not a global platform.
8. **Governance as Phase 3.** Governance is Phase 0.
9. **Diagram without policy.** An unannotated diagram scores 0 on
   the "annotated arrows" component of Dimension 6.
10. **200-FTE steady-state platform team for a large enterprise.**
    Design is not honestly operable; grader flags in Dimension 5 or
    6 depending on where the mis-sizing manifests.

## Grader worksheet

For each submission, produce:

- **Dimension scores** (six numeric scores).
- **Floor-rule results** (residency floor: pass/fail; registry
  floor: pass/fail).
- **Weighted total**.
- **Justification per dimension** (2–4 sentences each).
- **Notable strengths** (2–3 items).
- **Highest-value improvement** (one item, phrased actionably).

Return the worksheet with the score. The single highest-value
improvement is the most important feedback for the learner and is
often more valuable than the score itself.

## Reference calibration

Two calibration points for graders:

- The reference solution in `../SOLUTION.md` +
  `../architecture/target-architecture.md` is designed to score
  **90+** on Dimensions 1–5 and **~85** on Dimension 6 (deliberate
  open items marked `needs-research` prevent a 95+ on
  documentation).
- A submission that copies the reference architecture verbatim but
  cannot answer the regulatory dry-runs from SOLUTION §3 should
  score **~65** on Dimension 1 — the shape is right, but the
  defensibility is missing.

Grader disagreement between "the shape is right" and "the
defensibility is missing" is common. When in doubt, run one
regulatory dry-run with the learner present and score based on
their answers.
