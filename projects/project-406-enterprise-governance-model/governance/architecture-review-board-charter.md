# AI Architecture Review Board — Charter

> Reference charter for the Halcyon AI Architecture Review
> Board (ARB). Read alongside `../SOLUTION.md` (the reasoning),
> `../framework/enterprise-ai-governance-framework.md` (the
> enterprise framework this charter operates under), and
> `../governance/decision-authority-raci.md` (the RACI whose
> Class 3, Class 8, and Class 10 rows depend on this Board
> existing and being able to say "no" to named projects
> without carrying the reputational cost personally).

**Version**: 1.0
**Status**: Reference charter
**Owner**: Board Strategy Committee (charter ratification);
Chief Technology Officer (operational chair)

---

## 1. Purpose

The AI Architecture Review Board is the technical arbiter for
AI architecture decisions inside Halcyon. It exists so that:

- **Architecture calls are made against a defended reference,
  not against the loudest advocate.** The Halcyon platform
  reference architecture (Project 402), the Halcyon
  responsible-AI classification (Project 403), and the
  Halcyon innovation-portfolio stage-gate (Project 404) each
  produce inputs the ARB weighs. Architecture is decided; it
  is not narrated.
- **Class 3 deployment decisions (per the framework's decision
  classes; see `../framework/enterprise-ai-governance-framework.md`
  §6) are ratified by an authority whose signature can be
  produced from the archive.** No AI system above the Class 3
  threshold reaches production without an archived ARB
  approval.
- **Cross-body architecture questions have a defined home.**
  Architecture questions that touch responsible-AI, innovation
  portfolio, or external-voice concerns have named interface
  disciplines; the ARB does not adjudicate the Responsible AI
  Board's, Innovation Portfolio Board's, or External Voice
  Review Board's substantive questions and does not have its
  own substantive questions overruled by them.
- **The scope-ambiguity ruling has a first hop.** Where a
  system's inclusion in the enterprise AI governance scope is
  ambiguous (framework §2.3), the ARB triages the item and
  produces an argued ruling; the AIGC ratifies recurring
  rulings.

The ARB is designed against three failure modes documented
in enterprise architecture review functions:

- **Editorial-committee drift.** ARBs that meet, comment, and
  never approve become "review committees" that projects
  route around. The reference ARB has binding authority on
  Class 3, on reference-architecture amendments, and on
  above-threshold technology selection; approval or
  conditional approval is the output, not a set of comments.
- **Business-unit capture.** ARBs staffed only by the
  business unit whose project is under review become
  self-approval bodies. The reference ARB is composed of
  fixed roles across Halcyon with rotation and conflict
  discipline.
- **Technical-faction capture.** ARBs staffed by a single
  technical faction (e.g., only platform engineers, only ML
  researchers) develop blind spots the faction shares.
  Composition covers platform, ML, data, security, and
  responsible-AI perspectives.

---

## 2. Composition

### 2.1 Fixed-role voting seats

The ARB has eleven fixed-role voting seats. Each seat is
filled by a role, not a person; when the incumbent rotates,
the seat transfers.

| Seat | Role |
|---|---|
| Chair | Chief Technology Officer or delegate at that level |
| Deputy Chair | Head of Enterprise Architecture |
| Platform | Head of AI Platform Engineering (Project 402 platform owner) |
| ML architecture | Chief AI Scientist or delegate at Distinguished level |
| Data architecture | Chief Data Officer delegate at the data-architecture level |
| Security architecture | CISO delegate at the security-architecture level |
| Privacy architecture | Chief Privacy Officer delegate at the privacy-architecture level |
| Business-unit rep A | Rotating business-unit senior architect (18-month term) |
| Business-unit rep B | Rotating business-unit senior architect (18-month term, staggered against Rep A) |
| SRE / Operations | Head of AI Platform SRE |
| Cost / FinOps | Head of AI Platform FinOps (representing the CFO's capital-planning office on unit-economics questions) |

### 2.2 Standing invitees (non-voting)

The following are standing invitees. They attend, contribute
to discussion, and do not vote:

- **RAIB liaison.** Attends when a submission concerns an
  RAIB-classified or potentially-classified system.
- **IPB liaison.** Attends when a submission is emerging
  from the innovation portfolio and approaching production.
- **EVRB liaison.** Attends when an architecture decision
  will be described externally (reference-architecture
  publications, standards-body submissions).
- **AIGC Secretariat.** Attends for cross-body coordination
  and archive discipline. Does not vote to preserve the
  Secretariat's neutral archival role.
- **Internal Audit.** Attends on request for framework-
  adherence review; does not vote to preserve audit
  independence.
- **Third-party risk / Procurement.** Attends when a
  third-party AI service or platform is under review.

### 2.3 Board Strategy Committee liaison

The Board Strategy Committee liaison attends by invitation
for reference-architecture ratification, above-threshold
technology selection with strategic implications, and the
annual charter review. Non-voting.

### 2.4 Independence

The ARB does not require independent external members. It
handles Halcyon-internal architecture decisions. Independent
review of the ARB's own decisions comes from:

- Internal Audit's rolling framework-adherence review
  (Project 406 framework §9.3).
- The Phase 3 external framework review (framework §11.3).
- The AIGC's monthly interface review where cross-body
  disputes are surfaced.

### 2.5 Term and rotation

| Seat | Term |
|---|---|
| Chair | No fixed term; rotates with the CTO role |
| Deputy Chair | No fixed term; rotates with the Head of Enterprise Architecture role |
| Platform / ML / Data / Security / Privacy / SRE / FinOps | Rotate with the underlying role |
| Business-unit rep A / B | 18-month terms, staggered by nine months so at most one seat rotates in any six-month window |

Rotation of business-unit reps is coordinated by the AIGC
Secretariat with the business units' senior-architecture
leadership. A rotating seat has a named successor on file
before the term expires (framework §12).

---

## 3. Authority

### 3.1 Binding decisions

The ARB is binding on:

- **Reference-architecture amendments.** Changes to the
  Halcyon AI reference architecture (Project 402) require
  ARB approval before publication and adoption by business
  units. Amendments touching the platform-tenancy model,
  the cross-tenant isolation guarantee, or the data-flow
  topology require Tier 2 (full-Board) review.
- **Class 3 (deployment above threshold) approvals.**
  Deployment of a new AI system into production above the
  framework's Class 3 threshold requires ARB approval with
  RAIB consultation where the system is or would be
  responsible-AI-classified. Absence of an archived ARB
  approval blocks deployment.
- **Above-threshold technology selection.** Selection of a
  foundation model, an ML platform, an AI-specific data
  system, or a comparable component above the annual
  technology-selection threshold requires ARB approval. The
  threshold is set annually by the AIGC in coordination
  with the CFO and CTO.
- **Cross-system data-flow topology.** Architecture decisions
  that create a new cross-system data flow between AI
  systems, or between an AI system and a non-AI system of
  record, require ARB approval where the flow crosses a
  data-classification, privacy, or security boundary.
- **Scope-ambiguity triage.** For inbound items where scope
  is ambiguous under framework §2, the ARB rules the item
  in-scope or out-of-scope with an argued case. Recurring
  rulings escalate to the AIGC for ratification and possible
  amendment of the scope tests.
- **Platform-tenancy admission.** Admission of a new AI
  system to the Project 402 platform requires ARB approval
  against the platform-tenancy model. Non-admission with an
  ARB argument routes to platform-independent hosting or
  back to the business unit for redesign.
- **Reference-integration-pattern amendments.** Changes to
  the reference integration patterns (batch, real-time,
  agent, retrieval-augmented, human-in-the-loop) require
  ARB approval before adoption.

### 3.2 Advisory positions

The ARB is advisory (not binding) on:

- **Individual model architecture within an approved
  reference.** Where a system follows the ARB-approved
  reference architecture and integrates via approved
  patterns, model choice within the system is a platform-
  team decision. The ARB reviews on request.
- **Responsible-AI substantive positions.** The RAIB owns
  responsible-AI-substance decisions (bias-testing
  thresholds, fairness posture, safety classification).
  The ARB reviews architecture implications of RAIB
  decisions and advises on architectural feasibility.
- **Innovation-portfolio allocation.** The IPB owns
  innovation-portfolio decisions. The ARB advises on
  architecture readiness of innovation-stage systems at the
  stage gate where they approach production.
- **External communication of architecture content.** The
  EVRB owns publication surfaces. The ARB reviews
  architecture content for accuracy and IP posture and
  advises the EVRB.
- **Business-unit build-vs-buy decisions inside category
  budget.** The business unit and its CFO delegate decide.
  The ARB advises where the choice touches platform
  tenancy, reference-architecture conformance, or the
  category-multiplier assessment.

### 3.3 Explicitly out of scope

The ARB does not adjudicate:

- **Individual-system operating decisions.** Feature-flag
  rollouts, model-version increments within a version
  series, retraining schedules within an approved cadence,
  capacity increments within the approved envelope. These
  are Class 10 decisions and belong to platform-team
  leadership within guardrails.
- **Non-AI enterprise-architecture decisions.** Enterprise
  IT architecture that does not touch an in-scope AI
  system is enterprise-architecture-function scope.
- **Financial-approval decisions above the AIGC's delegated
  threshold.** The CFO decides Class 4 spend above the
  delegated threshold. The ARB advises on architecture
  content of the request.
- **Responsible-AI framework itself.** The RAIB owns the
  Responsible AI framework. The ARB uses it; it does not
  redesign it.
- **HR decisions about AI-team staffing.** Platform-team
  hiring, performance management, and organisational
  design are HR and line-management scope.

---

## 4. Quorum and decision rules

### 4.1 Quorum

The ARB reviews at three tiers matched to reversibility of
the decision.

- **Tier 1 (async, straightforward).** Reference-architecture-
  conforming Class 3 deployments, platform-tenancy admissions
  for standard tenancy classes, technology selection within
  the approved catalogue. Reviewed asynchronously in the
  ARB's queue. Sign-offs required: Chair or Deputy Chair,
  Platform seat, plus the relevant subject-matter seat
  (Security for a security-boundary change, Data for a
  data-flow change, etc.). Target latency: five business
  days.
- **Tier 2 (synchronous, full-Board).** Reference-architecture
  amendments, cross-tenancy changes, above-threshold
  technology selection, novel integration patterns, and any
  Class 3 deployment where the RAIB liaison flags
  responsible-AI concern. Quorum: eight of the eleven
  voting seats, including Chair or Deputy Chair, Platform,
  Security, and at least one of ML architecture or Data
  architecture. Target latency: two weeks from item receipt
  to convened decision.
- **Tier 3 (Board Strategy Committee ratified).** Amendments
  to the reference architecture with strategic
  implications, above-threshold technology selection where
  the strategic-option value is a material argument, and
  cross-body architecture disputes escalated from the AIGC.
  Tier 3 is convened as a Tier 2 review with the Board
  Strategy Committee liaison present, and the outcome is
  submitted to the Board Strategy Committee for
  ratification within its cycle.
- **Emergency (Tier D-equivalent).** Production-incident
  architecture change under Class 8 (incident response).
  Convened by the Chair on the on-call rota within the
  same business day. Post-hoc ratification at the next
  weekly meeting; full-Board notification within five
  business days.

### 4.2 Decision rule

- Consensus preferred. Where consensus is not reached, the
  ARB decides by majority of voting seats present. Dissent
  is recorded (§4.3).
- The Chair does not have a casting vote. Tied votes at
  Tier 2 defer to the next Board meeting or, on
  submitter's request, escalate to the AIGC for interface
  ruling.
- Silent approval is not permitted. A seat that abstains
  does not count as a positive vote. A seat that does not
  attend records absence.
- Conditional approval is a first-class outcome. The Board
  may approve with named conditions; the conditions are
  archived alongside the approval and their satisfaction is
  tracked before production entry.

### 4.3 Dissent recording

Dissent is a first-class artifact. Every ARB decision
records:

- Which seats voted for, which against, which abstained,
  which were absent.
- The dissenting position in one to three sentences,
  contributed by the dissenter.
- The category of dissent: procedural (workflow issue),
  substantive (architecture-position issue), or risk
  (unaddressed exposure).
- The Board's response — did the dissent change the
  decision, the conditions, or nothing.

Dissent above a threshold (three or more dissenting voting
seats on a Tier 2 decision, or two on a Tier 2 decision
touching platform tenancy, cross-tenancy isolation, or
regulatory-classification-adjacent architecture) escalates
to the AIGC for awareness. The AIGC may direct re-review or
convene an interface review with the affected operational
bodies.

---

## 5. Cadence

### 5.1 Standing meetings

- **Weekly Tier 1 queue and Tier 2 preparation.** Standing
  60 minutes. Attendees: Chair or Deputy Chair, Platform,
  the subject-matter seats with items on the agenda,
  Secretariat. Async approvals recorded through the ARB
  archive. Purpose: clear the Tier 1 queue, prepare
  materials for the following week's Tier 2 review, triage
  new inbound items to a tier.
- **Bi-weekly Tier 2 review.** Standing 150 minutes.
  Attendees: full Board (voting seats), standing invitees
  as relevant to the agenda. Purpose: convened Tier 2
  decisions.
- **Monthly cross-body coordination.** Standing 90 minutes
  with RAIB, IPB, and EVRB liaisons present. Purpose:
  cross-body interface items, pending Class 3 items with
  responsible-AI or innovation-portfolio interactions,
  publication-surface items where architecture accuracy
  is under review.
- **Quarterly framework review.** Standing 90 minutes with
  the AIGC Secretariat and the AIGC's monthly-review
  input. Purpose: reference-architecture drift review,
  decision-class threshold review, framework-adherence
  self-assessment ahead of the AIGC monthly meeting.
- **Annual charter and reference-architecture review.**
  Standing offsite (day-length). Attendees: full Board,
  Board Strategy Committee liaison, AIGC Secretariat.
  Purpose: re-approve the charter, re-approve the
  reference architecture, refresh the technology-selection
  threshold, refresh the platform-tenancy model.

### 5.2 Emergency convocation

- Tier D-equivalent emergency review convenes on the
  on-call rota within the same business day.
- The rota is published quarterly with named on-call
  seats (Chair, Platform, Security, one of ML architecture
  or Data architecture) and their coverage windows.
- The Chair may convene a full-Board emergency session
  for incidents crossing multiple architecture domains;
  the AIGC Secretariat notifies the AIGC and, where the
  incident is Critical severity, the Board Audit Committee
  liaison.

### 5.3 Async and remote

- Async decisions are permitted for Tier 1 items where the
  archive and reviewer sign-offs are complete within the
  tier's target latency.
- Remote attendance is standard. In-person is reserved for
  the annual review and for specific Tier 2 items where
  the Chair judges in-person review essential.

---

## 6. Standing agenda

### 6.1 Weekly agenda

1. Confirmation of prior week's Tier 1 decisions (archive
   check).
2. Tier D incidents in the period; post-incident review.
3. Tier 1 queue: approvals, conditions, deferrals.
4. Tier 2 preparation: items convened for the following
   week's review, materials owner, reviewer assignments.
5. Scope-ambiguity triage items.
6. Cross-programme interactions (RAIB, IPB, EVRB) requiring
   ARB input inside the week.
7. Any other business.

### 6.2 Bi-weekly Tier 2 agenda

1. Standing report from the AIGC Secretariat: framework
   updates affecting ARB scope, cross-body items.
2. Convened Tier 2 items:
   - Reference-architecture amendments.
   - Class 3 deployments with responsible-AI or platform-
     tenancy considerations.
   - Above-threshold technology selection.
   - Novel integration-pattern proposals.
3. Conditions-satisfaction check on prior Tier 2 approvals
   with conditions.
4. Cross-body escalations: items sent from RAIB, IPB, or
   EVRB requiring ARB input.
5. Framework-adherence review of the ARB's own decisions
   in the period (self-audit).

### 6.3 Monthly cross-body coordination agenda

1. Interface items with RAIB, IPB, EVRB liaisons.
2. Pending Class 3 items with cross-body implications.
3. Scope-boundary drift review (are more items than
   expected being routed as ambiguous?).
4. Standards-body positions with architecture implications
   (EVRB / ARB interface).
5. Innovation-portfolio stage-gate readiness (IPB / ARB
   interface).
6. Responsible-AI classification impact on architecture
   (RAIB / ARB interface).

### 6.4 Quarterly and annual reviews

- Reference-architecture drift indicators.
- Decision-class threshold review (are Tier 1 items
  arriving at Tier 2 latency, or vice versa?).
- Framework-adherence findings from Internal Audit.
- Portfolio-composition impact of ARB approvals in the
  quarter.

---

## 7. Conflicts of interest

### 7.1 Standing declarations

Voting seats maintain standing declarations of interest:

- External board memberships, advisory roles, and paid
  engagements with technology vendors whose products fall
  under ARB technology-selection authority.
- Personal ownership stakes in companies whose products
  compete for ARB technology-selection decisions.
- Family or personal relationships with named executives
  of Halcyon vendors, customers, competitors, or partner
  organisations where the relationship could reasonably
  create a conflict.
- Open-source project stewardship where the project is
  under ARB technology-selection or reference-architecture
  consideration.

Declarations are refreshed annually and immediately upon
a material change. The AIGC Secretariat holds the
declaration register.

### 7.2 Per-decision conflicts

Where a specific decision touches a declared interest, the
conflicted seat:

- Discloses the conflict at the top of the decision item.
- Withdraws from voting on that item.
- May contribute factual information (with the Chair's
  agreement) but does not participate in the argued
  deliberation.

The Chair may recuse a seat where a conflict is disclosed
mid-discussion. Where the Chair is conflicted, the Deputy
Chair convenes the item.

### 7.3 Programme-adjacent conflicts

- Voting seats do not simultaneously hold compensated
  advisory positions at technology vendors whose products
  are under active ARB technology-selection review.
- Voting seats disclose open-source project stewardship
  roles where the project appears in the reference
  architecture or the technology-selection catalogue;
  stewardship is typical and not disqualifying but must be
  visible.
- Where a rotating business-unit rep's home business unit
  is the submitter of a Tier 2 item, the rep may
  contribute factual information and does not vote on
  the item.

---

## 8. Escalation

### 8.1 Upward escalation to the AIGC

The following items escalate from the ARB to the AIGC:

- Tier 2 decisions with dissent above threshold (§4.3).
- Scope-ambiguity rulings that recur (three or more items
  raising the same ambiguity type in a rolling six-month
  window).
- Interface disputes with the RAIB, IPB, or EVRB not
  resolved at the monthly cross-body coordination.
- Reference-architecture amendment proposals with material
  strategic-option or platform-tenancy implications.
- Technology-selection decisions where the strategic-option
  value or the CFO delegate assessment produces an
  unresolved position at the ARB.
- Framework-adherence findings raised by Internal Audit
  against the ARB.

### 8.2 Upward escalation to the Board Strategy Committee

The AIGC escalates the following items received from the
ARB to the Board Strategy Committee:

- Reference-architecture amendments with strategic
  implications (Tier 3).
- Above-threshold technology selection with strategic
  implications (Tier 3).
- Cross-body architecture disputes where the AIGC's
  interface ruling requires Board-level ratification.
- Framework amendments (Class 1) recommended by the ARB.

### 8.3 Downward direction

The AIGC may direct the ARB to:

- Re-review a decision.
- Change a standing threshold (technology-selection
  threshold, Class 3 threshold, Tier 1/Tier 2 boundary).
- Reconstitute a rotating business-unit seat.
- Convene an emergency interface review with a named
  operational body.
- Adopt a scope-tests amendment for triage rulings.

Board Strategy Committee direction (via the AIGC) may
direct the ARB to amend the reference architecture, the
technology-selection catalogue, or the platform-tenancy
model. Directions are recorded in the ARB archive and
reflected in the next annual review.

### 8.4 Lateral coordination

The ARB coordinates without escalation with:

- **Responsible AI Board (Project 403).** Interface covers
  Class 3 deployments of RAIB-classified systems,
  reference-architecture updates with responsible-AI
  implications, and Class 8 incident architecture changes
  where the incident touches responsible-AI substance.
- **Innovation Portfolio Board (Project 404).** Interface
  covers stage-gate readiness of innovation-stage systems
  approaching production, platform-tenancy admission for
  innovation-graduation systems, and IPB-owned technology
  choices at the innovation-scale threshold.
- **External Voice Review Board (Project 405).** Interface
  covers publication of reference-architecture content,
  standards-body positions with architecture implications,
  and executive-briefing curriculum modules touching
  Halcyon AI architecture.
- **Chief Data Officer / Chief Privacy Officer**. Interface
  covers cross-system data-flow topology decisions and
  privacy-by-design architecture reviews.
- **CISO / Security architecture function.** Interface
  covers security-boundary architecture and Class 8
  incident architecture response.
- **CFO capital-planning office.** Interface covers unit-
  economics reviews of platform-tenancy admissions and
  above-threshold technology selection with material
  aggregate-cost implications.

---

## 9. Records and archive

### 9.1 What is archived

The ARB archives:

- All Tier 1, Tier 2, and Tier D decisions with reviewer
  identities, comments, and conditions.
- The current-and-historical reference architecture, each
  version with the amending decision and effective date.
- The current-and-historical technology-selection catalogue
  with entry/exit decisions.
- The current-and-historical platform-tenancy model with
  amendment decisions.
- Scope-ambiguity triage rulings.
- Meeting minutes for all standing meetings.
- Dissent records with dissenter identity and position.
- Emergency (Tier D) approvals with post-hoc ratification
  records.
- Conditional-approval condition-satisfaction records.
- Conflicts-of-interest declarations and per-decision
  recusals.

### 9.2 Retention

- Standard retention: seven years from decision date.
- Extended retention: reference-architecture versions
  retained for the duration of any deployed system built
  against them plus seven years.
- Extended retention: safety-critical AI-system deployment
  approvals retained for the duration of the system's
  operating life plus seven years (aligning with the
  framework's §9.5 rule for safety-critical systems).
- Regulatory-classification-adjacent architecture decisions
  retained per the applicable regulatory recordkeeping
  requirement (typically ten years).

### 9.3 Accessibility

- Voting seats and standing invitees have full read
  access.
- Submitters have read access to their own submissions
  and to reference-architecture content applicable to
  their work.
- Internal Audit and external audit have read access on
  request, unmediated.
- Access is logged. Access anomalies are reviewed monthly
  by the CISO delegate seat.

### 9.4 Chain of custody

- The AIGC Secretariat is the archive owner (the framework's
  §9.6 discipline).
- The archive is stored in a controlled document management
  system with immutable versioning.
- Decisions may be amended only by explicit follow-on
  decisions; the audit trail is preserved.
- Reference-architecture versions are immutable once
  ratified; amendments are new versions with a linked
  decision record.

---

## 10. Amendment

- This charter is amended by the Board Strategy Committee
  on recommendation from the ARB Chair via the AIGC.
- Substantive amendments (scope of authority, quorum,
  fixed-role seats, cadence) require Board Strategy
  Committee ratification.
- Operational amendments (agenda ordering, standing-invitee
  additions, non-substantive cadence adjustments) may be
  approved by the ARB directly and recorded in the next
  quarterly AIGC review.
- The charter is reviewed at the annual charter-and-
  reference-architecture review (§5.1) at minimum.

---

## Appendix A — Class 3 deployment-approval decision template

Template used for Class 3 deployment approvals above the
framework's threshold. Complements the framework's
Appendix A (Class 2) and Appendix B (Class 4) templates.

```
Class 3 Deployment Approval
───────────────────────────

System identifier: <system name and internal ID>

Owning business unit: <business unit>

Named accountable role: <role, not person>

Class-3 threshold criterion:
  <which threshold criterion applies — revenue exposure,
   customer count, safety classification, spend, or
   Class 2 regulatory classification>

Responsible-AI classification (RAIB):
  <RAIB classification or "not RAI-classified"; if
   RAI-classified, reference to RAIB record>

Reference-architecture conformance:
  <conforming / conforming with named deviation / novel
   pattern, with named deviations and reasons>

Platform-tenancy admission:
  <platform-hosted / independent-hosted, with reason>

Technology selection:
  <components at or above the threshold; catalogue
   references>

Cross-system data flows:
  <flows crossing data classification, privacy, or
   security boundaries; approvals in place>

Security architecture review:
  <CISO delegate assessment>

Data / privacy architecture review:
  <CDO / CPO delegate assessment>

Unit economics assessment:
  <FinOps seat assessment>

ARB decision:
  Approved / conditionally approved / declined / deferred
  Tier: <Tier 1 async / Tier 2 convened / Tier 3 Board-
        ratified>
  Vote: <per seat>
  Dissent: <recorded>

Conditions attached:
  <conditions and satisfaction owners>

Next review:
  <re-review trigger and date>

Archive location:
  <archive identifier>
```

---

## Appendix B — Reference-architecture amendment decision template

Template used for reference-architecture amendments.

```
Reference-Architecture Amendment
────────────────────────────────

Amendment identifier: <version number>

Proposed by: <role or body>

Sections amended:
  <section references in the reference architecture>

Substance of amendment:
  <one to three paragraphs>

Rationale:
  <argued reason; expected impact>

Impact on existing systems:
  <systems requiring re-review, grace-period design,
   deprecation schedule>

Impact on the platform-tenancy model:
  <if any>

Impact on the technology-selection catalogue:
  <if any>

Cross-body implications:
  RAIB: <if any>
  IPB: <if any>
  EVRB: <if any, e.g., publication of the amendment>

Consultation record:
  <who reviewed, feedback, dispositions>

ARB decision:
  Approved / declined / deferred
  Tier: <Tier 2 / Tier 3 Board-ratified>
  Vote: <per seat>
  Dissent: <recorded>

Effective date:
  <date>

Grace period / transition rule for existing systems:
  <as applicable>

Archive location:
  <archive identifier>
```

---

## Appendix C — Scope-ambiguity triage template

Template used for scope-ambiguity triage rulings under
framework §2.3.

```
Scope-Ambiguity Triage Ruling
─────────────────────────────

Item identifier: <inbound-item ID>

Submitter: <role or body>

Item description:
  <one paragraph>

Scope tests evaluated (framework §2):
  Data test: <met / not met / ambiguous, with reason>
  Autonomy test: <met / not met / ambiguous, with reason>
  Regulatory test: <met / not met / ambiguous, with reason>
  Reputation test: <met / not met / ambiguous, with reason>
  Exclusive test: <all conditions met / not met, with
                  reason>

ARB ruling:
  In-scope / out-of-scope
  Tier of subsequent review if in-scope: <Tier 1 / Tier 2>
  Assigned decision class if in-scope: <Class N>

Argued reasoning:
  <one to three paragraphs>

Recurring-ruling flag:
  <yes / no; if yes, count in the rolling six-month window
   and referenced prior rulings>

Escalation to AIGC:
  <required / not required; if required, at next monthly
   meeting>

Archive location:
  <archive identifier>
```

---

## Appendix — Signature block for charter ratification

```
Ratified by the Board Strategy Committee on:
  <date>

Ratifying members:
  <named signatories>

Effective from:
  <date>

Next scheduled review:
  <date, annual>
```

---

## Related documents

- `../SOLUTION.md` — the reference solution defending the
  reasoning behind this charter.
- `../framework/enterprise-ai-governance-framework.md` — the
  enterprise framework this charter operates under.
- `../governance/decision-authority-raci.md` — the enterprise
  RACI whose Class 3, Class 8, and Class 10 rows depend on
  the ARB's binding authority.
- `../rubric/evaluation-rubric.md` — the grading rubric
  graders apply to learner submissions.
- `../../project-402-global-ai-platform-architecture/` — the
  platform whose reference architecture the ARB owns
  amendments to.
- `../../project-403-responsible-ai-framework/governance/` —
  the Responsible AI Board this ARB coordinates with on
  Class 3 deployments of RAIB-classified systems.
- `../../project-404-innovation-program-design/governance/` —
  the Innovation Portfolio Board this ARB coordinates with
  on innovation-stage systems approaching production.
- `../../project-405-industry-thought-leadership/governance/external-voice-charter.md`
  — the External Voice Review Board this ARB coordinates
  with on architecture publications and standards-body
  positions.
