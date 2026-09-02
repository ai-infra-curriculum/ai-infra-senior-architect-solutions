# Enterprise RACI for AI Decisions

> Reference decision-authority matrix for Halcyon's enterprise
> AI governance model. Read alongside `../SOLUTION.md`,
> `../framework/enterprise-ai-governance-framework.md` §6
> (decision-class model), and
> `../governance/architecture-review-board-charter.md`. The
> framework's guarantee — that no in-scope AI decision falls
> between bodies and no decision routes to three bodies with
> no defined interface — depends on this RACI being read the
> same way by the Chief Financial Officer, the General
> Counsel, the Head of Internal Audit, and a first-line
> engineering manager.

**Version**: 1.0
**Status**: Reference RACI
**Owner**: AI Governance Committee (amendment recommendation);
Board Strategy Committee (ratification for Class 1
amendments); AIGC (ratification for non-Class-1 amendments)

---

## 1. How to read this document

### 1.1 RACI convention

The RACI uses the standard four letters with Halcyon-specific
definitions:

- **R — Responsible.** Does the work. Assembles the case,
  runs the analysis, drafts the artifact. Named role.
- **A — Accountable.** Owns the outcome. Ratifies the
  decision or approves the recommendation on behalf of the
  authority level. Exactly one role per class where feasible;
  named body where a body ratifies.
- **C — Consulted.** Provides substantive input the R must
  reflect. Absence of a required C invalidates the decision.
- **I — Informed.** Receives the decision record after the
  fact. Absence of I notification is a workflow failure but
  does not invalidate the decision.

Halcyon-specific rules:

- **Multiple R for the same class** is permitted where the
  substantive work is jointly owned (e.g., Class 8 incident
  response, jointly owned by CISO and RAIB substance
  reviewer). Where multiple R exist, the decision record
  names the specific responsibility split.
- **A is exactly one authority** per decision. Where a
  decision requires ratification by a body, the body is A
  and the body's decision rule (§4) governs.
- **C-with-veto** is distinguished from C. Where a C role
  has a veto (typically General Counsel on regulatory-
  adjacent items, CISO on security-boundary items), the
  RACI cell reads "C (veto)".
- **I-with-ack** is distinguished from I. Where an I role
  must record acknowledgement (typically the Board Strategy
  Committee liaison and Head of Internal Audit for Class 1,
  Class 2, and Class 9), the RACI cell reads "I (ack)".

### 1.2 Roles enumerated

The RACI references the following roles. Each is a named
role, not a named person. Successors are named in the
framework's §12 register.

| Short | Role |
|---|---|
| CEO | Chief Executive Officer |
| CFO | Chief Financial Officer |
| CIO | Chief Information Officer (AIGC Chair) |
| CTO | Chief Technology Officer (ARB Chair) |
| CISO | Chief Information Security Officer |
| CDO | Chief Data Officer |
| CPO-Priv | Chief Privacy Officer |
| GC | General Counsel |
| HIA | Head of Internal Audit |
| Sec-AIGC | AIGC Secretariat |
| ARB | AI Architecture Review Board (chaired by CTO) |
| RAIB | Responsible AI Board (chaired per Project 403) |
| IPB | Innovation Portfolio Board (chaired per Project 404) |
| EVRB | External Voice Review Board (chaired per Project 405; CMO operational chair) |
| AIGC | AI Governance Committee (chaired by CIO) |
| BSC | Board Strategy Committee |
| BAC | Board Audit Committee |
| BRC | Board Risk Committee (where present; otherwise its items merge into BAC) |
| Board | Full Board of Directors |
| BU-Exec | Business-unit executive with P&L authority for the AI system's home business unit |
| Plat-Lead | Head of AI Platform Engineering |
| Cat-Owner | Portfolio-category owner (per framework §7.1) |
| Sub-Team | Submitting team (project team, product team, or platform team originating the decision) |

### 1.3 Thresholds

Where a class threshold applies, the threshold is set
annually by the AIGC in coordination with the CFO and
published at §5 of this document. The RACI rows apply
above the threshold; below-threshold decisions run as
Class 10 (operating) or by the category owner within the
CFO envelope.

### 1.4 Fallback where a role is unfilled

Where a named role is unfilled (transition period, leave
of absence, unfilled vacancy), the framework's §12
successor register names the acting incumbent. The RACI is
read against the acting incumbent. A role transition
without a successor on record is a framework-health event
and is recorded on the AIGC dashboard (framework §8.1
panel 6).

Where the fallback is itself unfilled (successor also
absent), the escalation path in §4 of this document
governs: decisions requiring the role's R, A, or C (veto)
input defer until the role is filled or the AIGC ratifies
an interim delegate.

---

## 2. Decision-class summary

The framework enumerates ten decision classes (framework
§6). This RACI provides one row per class plus a
sub-row where a class has a threshold splitting
above-threshold and delegated-authority behaviour.

| # | Class | R | A | C (with veto marked) | I (with ack marked) |
|---|---|---|---|---|---|
| 1 | Framework and policy | AIGC / Sec-AIGC | BSC | CFO, GC (veto on legal), CISO, HIA, CDO, CPO-Priv, ARB, RAIB, IPB, EVRB | Board (ack), BAC (ack) |
| 2 | Regulatory-classification | GC | AIGC | RAIB, CISO, CPO-Priv, ARB, BU-Exec | BSC liaison (ack), BAC (ack), HIA (ack) |
| 3 | AI deployment above threshold | ARB (Chair) / Sub-Team | CIO (or CTO where CIO delegates) | RAIB (veto for RAI-classified systems), CISO (veto for security-boundary), CDO, CPO-Priv, BU-Exec, Plat-Lead, FinOps seat | AIGC, IPB (for graduating innovation), EVRB (for externally-visible systems) |
| 4a | Investment-portfolio allocation (above AIGC-delegated threshold) | Cat-Owner / AIGC | CFO | AIGC chair, GC (regulatory-adjacent), CISO (security-adjacent) | BAC (ack, annual), Board (via annual portfolio report) |
| 4b | Investment-portfolio allocation (within AIGC-delegated threshold) | Cat-Owner | AIGC chair | CFO delegate, other Cat-Owners at rebalancing | BAC (quarterly dashboard) |
| 5 | Responsible-AI posture | RAIB (Chair) / Sub-Team | RAIB (body) | GC (veto on regulatory-adjacent), CISO, EVRB (for public-facing posture), ARB (architecture implications) | AIGC, BAC (via dashboard), BSC (via framework review) |
| 6 | Innovation-portfolio | IPB (Chair) / Sub-Team | IPB (body) | RAIB (production-classification consultation), ARB (platform-hosting eligibility), CFO delegate | AIGC (portfolio-level), BSC (annual innovation review) |
| 7a | External-communication (Tier A / B per EVRB charter) | EVRB reviewer set / Sub-Team | EVRB (body per its tiered review) | GC, CISO, RAIB (for RAI content), ARB (for architecture content) | AIGC (aggregate metrics) |
| 7b | External-communication Tier C (strategic) | EVRB (Chair) / Sub-Team | EVRB (body) + AIGC (aware) | GC, CISO, RAIB, ARB, BSC liaison | AIGC (strategic-posture-level), BSC (via liaison) |
| 8a | Incident-response operational (severity Medium / High) | CISO | CISO | RAIB (substance), GC, BU-Exec, Sub-Team | AIGC (post-incident), Comms (external) |
| 8b | Incident-response (Critical severity) | CISO / RAIB / GC (joint R) | CEO on Critical-severity operating response; AIGC ratifies post-incident actions | ARB (architecture change), EVRB (external-comms), Board Chair (aware) | BAC (ack), BSC (ack), Board (per Chair) |
| 9 | Audit-finding remediation | HIA (tracks) / Cat-Owner or body-Chair whose scope the finding falls in (drafts plan) | AIGC (ratifies plan) | GC (regulatory-adjacent), CFO (cost implications), affected operational body | BAC (ack), Board (via BAC annual) |
| 10 | Individual-system operating (within guardrails) | Plat-Lead / Sub-Team | Plat-Lead or BU-Exec (per business-unit delegation) | ARB (via guardrails, not per-decision), RAIB (via guardrails, not per-decision) | AIGC (via aggregate reporting) |

Below-threshold decisions in Class 3, Class 4, and Class 7
run at the lower row (4b, 7a) or as Class 10 depending on
the class-specific rule at §3.

Every row is expanded in §3 with authority-source, decision
record required, escalation path, and archive location.

---

## 3. Class-by-class detail

### 3.1 Class 1 — Framework and policy decisions

**In scope.** Amendments to the enterprise AI governance
framework, the scope tests, the RACI, the governance
principles, the portfolio-category model, the Board-oversight
dashboard, the compliance-and-audit posture, and the
enterprise AI policy register (framework §10).

**R.** The AIGC drafts the amendment through its Secretariat
and its operational-body chair members. The amendment case
includes the argued rationale, the impact analysis on the
existing framework, the transition rule, and the effective
date.

**A.** The Board Strategy Committee ratifies. Where the
amendment touches Board Audit Committee scope
(compliance-and-audit posture, audit-finding oversight), the
BAC is co-ratifier.

**C.**

- CFO. Portfolio-category or spend-threshold amendments.
- GC (veto on legal). Any amendment touching regulatory
  classification, regulatory-obligation register, or
  external-audit posture.
- CISO. Any amendment touching incident response or
  security posture.
- HIA. Any amendment touching internal-audit programme,
  archive discipline, or evidence-generation workflow.
- CDO. Any amendment touching data-for-AI policy or the
  data-governance interface.
- CPO-Priv. Any amendment touching personal-data-in-AI
  policy or the privacy programme interface.
- Operational body chairs (ARB, RAIB, IPB, EVRB). Any
  amendment touching their scope or the interfaces
  between them.

**I.** The full Board acknowledges Class 1 ratifications via
the BSC's report. The BAC acknowledges via its own report
where compliance-and-audit posture is amended.

**Threshold.** All Class 1 items are above-threshold by
definition. There is no "small framework amendment."
Operational amendments are covered in framework §11.2 and
are not Class 1.

**Decision record.** A Framework Amendment record (framework
§13 changelog) with the ratifying body, the effective date,
the amendment substance, and the reference to the AIGC
recommendation memo.

**Escalation path.** BSC ratification is the terminal
authority for Class 1. Where the BSC declines an amendment,
the AIGC returns to draft. Where the amendment touches the
BAC's scope and the two committees do not concur, the
disagreement escalates to the full Board.

**Archive.** Framework changelog and BSC decision archive.

### 3.2 Class 2 — Regulatory-classification decisions

**In scope.** Whether a Halcyon AI system is a "high-risk AI
system" under the EU AI Act, subject to a specific
regulator's AI supervision, subject to ISO/IEC 42001
certification scope, or covered by a sector-specific AI
regulatory obligation.

**R.** The General Counsel is Responsible. GC leads the
argued classification memo per framework Appendix A. GC may
delegate the drafting to the Head of Regulatory Affairs, the
Head of Legal for the relevant business line, or an
external firm, but the classification memo is signed by GC.

**A.** The AIGC ratifies. AIGC decision rule (framework
§3.5) governs the vote. Where the classification changes
Halcyon's regulatory posture materially, the AIGC also
notifies the BAC and, where present, the BRC.

**C.**

- RAIB. Responsible-AI classification is an input.
- CISO. Security-posture implications of the
  classification.
- CPO-Priv. Personal-data implications.
- ARB. Architecture implications of the classification
  (e.g., a "high-risk" classification triggers additional
  reference-architecture obligations).
- BU-Exec. Business-unit awareness of the operating
  implications (compliance obligations, audit
  obligations, disclosure obligations).

**I (with ack).** The BSC liaison acknowledges. The BAC
acknowledges for classifications that materially change
audit-programme scope. HIA acknowledges for the audit-
programme adjustment.

**Threshold.** No threshold. All in-scope AI systems have a
Class 2 record on file (which may be "no regulatory
classification applies," with the argued case for that
position).

**Decision record.** The framework Appendix A template. The
record is retained per framework §9.5 extended-retention
rule for regulatory-classification decisions (typically ten
years, longer where specified).

**Escalation path.** Where the AIGC cannot reach the vote
threshold, the item defers to the next AIGC meeting; where
time-sensitive, the AIGC Chair escalates to the BSC liaison
with the choices on record. Where GC and the AIGC disagree
on classification, the disagreement escalates to the BSC.

**Archive.** AIGC archive and General Counsel's regulatory-
classification archive.

### 3.3 Class 3 — AI deployment decisions above threshold

**In scope.** Deployment of a new AI system into production
above the annual Class 3 threshold. Threshold criteria (any
one triggers): revenue exposure above the annual limit;
customer count above the annual limit; safety
classification (per RAIB); Class 2 regulatory
classification; or aggregate deployment spend above the
annual limit. Threshold values in §5.

**R.** The ARB Chair (via the ARB) drafts the Class 3
approval record with the Sub-Team as co-R for the technical
material. The Sub-Team provides the reference-architecture
conformance statement, the platform-tenancy admission
request, the technology-selection references, and the
security / data / privacy / unit-economics assessments.

**A.** The CIO is Accountable (or the CTO where CIO
delegates the Class 3 accountability to CTO by standing
delegation). The Accountable role signs the deployment
approval and is answerable to the Board and the AIGC for
Class 3 outcomes.

**C.**

- RAIB (veto for RAI-classified systems). Absence of RAIB
  sign-off blocks deployment of an RAI-classified system.
- CISO (veto for security-boundary changes). Absence of
  CISO sign-off blocks deployment where the system
  crosses a security boundary requiring architectural
  review.
- CDO. Data-flow topology and data-classification impact.
- CPO-Priv. Personal-data impact and privacy-by-design
  review.
- BU-Exec. Business-unit operational readiness.
- Plat-Lead. Platform-tenancy admission and platform-team
  operational readiness.
- FinOps seat (via ARB). Unit-economics assessment.

**I.** The AIGC (via monthly reports). The IPB where the
system is graduating from innovation. The EVRB where the
system is externally visible.

**Threshold.** Set annually per §5. Below-threshold
deployments run as Class 10 within platform-team and
business-unit delegated authority.

**Decision record.** The ARB Charter Appendix A template.

**Escalation path.** ARB Tier 2 review is the default. Tier
3 (BSC-ratified) is required where the deployment carries
material strategic implications or where the ARB dissent
threshold is met. Where CIO (A) and ARB (R) disagree on
Tier 2 approval, the item escalates to the AIGC for
interface ruling.

**Archive.** ARB archive with cross-reference to Class 2
record where applicable and to Class 8 pre-incident
runbook where applicable.

### 3.4 Class 4 — Investment-portfolio allocation

Class 4 splits into 4a (above the AIGC-delegated threshold)
and 4b (within the AIGC-delegated threshold).

#### 3.4.1 Class 4a — above the AIGC-delegated threshold

**In scope.** Allocation of AI-adjacent budget within the AI
portfolio across categories above the AIGC's delegated
threshold. Typical examples: net new commitment to the
Core-platform category, cross-category rebalancing above
the delegated threshold, external-programme category
expansion touching CFO's capital-planning cycle.

**R.** The category owner (Cat-Owner) drafts the allocation
memo per framework Appendix B. The AIGC drafts the
portfolio-composition impact analysis via its Secretariat.

**A.** The CFO ratifies. AIGC recommendation is a required
input; CFO ratification governs.

**C.** AIGC Chair. GC where the allocation is regulatory-
adjacent (e.g., a Responsible-AI-operations spend increase
in response to a regulatory obligation). CISO where the
allocation touches security posture. Other Cat-Owners at
rebalancing.

**I.** The BAC acknowledges Class 4a decisions in its
annual portfolio-composition-and-outcome review (framework
§7.3). The Board receives the annual portfolio report.

**Threshold.** The AIGC-delegated threshold is set annually
with the CFO. Values in §5.

**Decision record.** The framework Appendix B template.

**Escalation path.** Where CFO and AIGC disagree, the item
escalates to the BSC (for strategic implications) or to the
BAC (for compliance-and-audit implications). Where the
allocation would breach the CFO-approved aggregate
envelope, the item escalates to the enterprise capital-
planning process and to the Board.

**Archive.** AIGC portfolio archive and CFO capital-planning
archive.

#### 3.4.2 Class 4b — within the AIGC-delegated threshold

**In scope.** Rebalancing within a category or between
categories within the AIGC-delegated threshold. Below-
threshold routine allocations under the category owner's
delegated authority within the CFO envelope.

**R.** Cat-Owner.

**A.** AIGC Chair (via monthly meeting).

**C.** CFO delegate to the AIGC. Other Cat-Owners at
rebalancing.

**I.** The BAC receives quarterly dashboard reporting
(framework §8.1 panel 1).

**Threshold.** Below the Class 4a threshold; §5.

**Decision record.** Category-owner memo referencing the
framework Appendix B template; archived through the AIGC
Secretariat.

**Escalation path.** Cross-category items disputed by more
than one Cat-Owner escalate to the AIGC full body for
resolution at the next monthly meeting.

**Archive.** AIGC portfolio archive.

### 3.5 Class 5 — Responsible-AI posture decisions

**In scope.** Halcyon's position on a specific responsible-
AI question. Examples: bias-testing threshold for a
customer-facing model, transparency posture for an
autonomous decision-making system, third-party fine-tuning
posture, deployment posture of a model class in a
safety-critical context, model-card publication policy.

**R.** The RAIB Chair (via the RAIB) drafts the posture
memo. Sub-Team provides technical inputs and operating
implications.

**A.** The RAIB (body) is Accountable. Its own decision rule
(per Project 403 charter) governs.

**C.**

- GC (veto on regulatory-adjacent). Absence of GC sign-off
  blocks posture decisions that would take Halcyon
  outside a regulatory obligation.
- CISO. Security implications of the posture.
- EVRB. Any posture decision with public-facing
  implications, so external communication of the posture
  is coherent with the review workflow's tiering.
- ARB. Architecture implications of the posture (e.g., a
  transparency-posture change requires reference-
  architecture updates).

**I.** The AIGC receives the posture record. The BAC
receives the aggregate posture panel on the dashboard. The
BSC receives posture changes as part of the annual
framework review.

**Threshold.** No dollar threshold. All posture decisions
affecting Halcyon-branded AI systems run through Class 5.

**Decision record.** RAIB decision record per Project 403
charter, cross-referenced from the AIGC archive.

**Escalation path.** Where RAIB and ARB or RAIB and EVRB
disagree at the operational-body level, the interface ruling
escalates to the AIGC (framework §5.4). Where the posture
touches Class 2 regulatory classification, the item
co-routes to Class 2 with GC as R for the classification
question.

**Archive.** RAIB archive with cross-reference from the
AIGC archive.

### 3.6 Class 6 — Innovation-portfolio decisions

**In scope.** Innovation-portfolio allocation within the
IPB-owned category envelope, stage-gate transitions within
the innovation programme, external-research partnership
approvals for exploratory AI work, portfolio-level go/no-go
for innovation-stage AI systems.

**R.** IPB Chair (via the IPB). Sub-Team provides the
proposal.

**A.** IPB (body). Its own decision rule (per Project 404
charter) governs.

**C.**

- RAIB. Systems that would be RAI-classified on production
  adoption are consulted at defined stage gates.
- ARB. Platform-hosting eligibility at the graduation
  stage gate; architecture readiness assessment.
- CFO delegate. Category-envelope check and cross-category
  implications.

**I.** The AIGC receives portfolio-level changes. The BSC
receives the annual innovation review.

**Threshold.** IPB-owned category envelope is the aggregate
threshold; within the envelope, IPB delegated authority
governs. Cross-category rebalancing triggers Class 4a or
Class 4b.

**Decision record.** IPB stage-gate record per Project 404
charter, cross-referenced from the AIGC archive.

**Escalation path.** Graduation-stage systems whose
production adoption would require Class 2 or Class 3
approval have those approvals as pre-conditions of stage-
gate exit; the IPB does not substitute for the ARB or the
AIGC.

**Archive.** IPB archive with cross-reference from the AIGC
archive.

### 3.7 Class 7 — External-communication decisions

Class 7 splits into 7a (Tier A/B per EVRB charter) and 7b
(Tier C strategic).

#### 3.7.1 Class 7a — Tier A / Tier B

**In scope.** Publication of AI-related content on programme
surfaces at Tier A (routine, low-risk) and Tier B (reviewed
by the four EVRB sign-off seats).

**R.** EVRB reviewer set per its tiering (Communications,
Legal, Security, relevant technical voice). Sub-Team is
co-R for content.

**A.** EVRB (body) per its tiered review.

**C.**

- GC. Legal and IP implications.
- CISO. Security-sensitive content.
- RAIB. Content on Halcyon's Responsible-AI posture.
- ARB. Content describing Halcyon's AI architecture.

**I.** AIGC (aggregate metrics via quarterly dashboard).

**Threshold.** EVRB tiering per Project 405 charter is the
threshold.

**Decision record.** EVRB decision record per Project 405
charter.

**Escalation path.** Content whose tier is ambiguous is
triaged to Tier B or Tier C by the EVRB Chair. Content
touching regulatory posture escalates to the EVRB Chair
plus GC for co-approval.

**Archive.** EVRB archive.

#### 3.7.2 Class 7b — Tier C strategic

**In scope.** Publication of AI-related content at Tier C
per the EVRB charter — strategic-posture positions, first-
of-kind standards-body positions, high-risk external
narratives on Responsible-AI, regulatory-consultation
content.

**R.** EVRB Chair. Sub-Team is co-R for content.

**A.** EVRB (body) with AIGC awareness. Where the content
takes Halcyon to a strategic position materially different
from the current posture, the AIGC is notified before the
EVRB approval is final. AIGC does not override; AIGC is
informed with ack.

**C.** GC (veto on legal), CISO, RAIB (RAI substance), ARB
(architecture accuracy), BSC liaison (strategic-posture
awareness).

**I.** AIGC (strategic-posture level), BSC (via liaison).

**Threshold.** Per EVRB tiering.

**Decision record.** EVRB decision record with AIGC cross-
reference and, where applicable, BSC-liaison ack record.

**Escalation path.** Content whose strategic implications
extend beyond publication (Halcyon commits to an operating
position at a regulator, for example) routes to Class 2 for
the regulatory-classification question and to Class 1 where
a framework amendment is implied.

**Archive.** EVRB archive with cross-reference from AIGC.

### 3.8 Class 8 — Incident-response decisions

Class 8 splits into 8a (Medium / High severity) and 8b
(Critical severity).

#### 3.8.1 Class 8a — Medium / High severity

**In scope.** Response to an AI-system incident at Medium or
High severity per the CISO's incident-severity matrix
(framework §9 and CISO's operating framework).

**R.** CISO coordinates operational response. Sub-Team is
co-R for the substantive response.

**A.** CISO for operational response.

**C.**

- RAIB. Substance of the incident where the incident
  touches responsible-AI issues.
- GC. Legal implications (regulator notification,
  contractual notification).
- BU-Exec. Business-unit operating implications.

**I.** AIGC (post-incident review at the next monthly
meeting). Communications (external notification per EVRB
tiering).

**Threshold.** CISO's Medium and High classifications per
the incident-severity matrix; the matrix is reviewed
annually with the AIGC.

**Decision record.** Incident record per CISO's incident-
response framework, cross-referenced from the AIGC archive.

**Escalation path.** Medium incidents escalate to High if
severity re-classification is warranted; High incidents
escalate to Critical (8b) on re-classification.

**Archive.** CISO incident archive with AIGC cross-
reference.

#### 3.8.2 Class 8b — Critical severity

**In scope.** Response to an AI-system incident classified
Critical per the CISO's matrix. Typical Critical criteria:
material customer harm, regulatory-consultation trigger,
Board-notification trigger, cross-system compromise.

**R.** CISO, RAIB (substance), and GC (legal) jointly. Each
signs the operating response section relevant to its
authority; the CISO is R for the operational-response
integration.

**A.** CEO for the Critical-severity operating response.
AIGC ratifies post-incident actions (Class 1 amendments
where the incident recommends framework change).

**C.** ARB (architecture change response), EVRB (external
communications), Board Chair (awareness).

**I.** BAC (ack), BSC (ack), Board (per Board Chair).

**Threshold.** CISO's Critical classification.

**Decision record.** Incident record with joint sign-offs;
post-incident review record ratified by the AIGC and
cross-referenced from the BAC archive.

**Escalation path.** Critical incidents automatically
trigger a Board-level deep dive per framework §8.2. The
BAC or BSC (per the incident's substance) convenes the deep
dive.

**Archive.** CISO incident archive, AIGC post-incident
archive, Board deep-dive archive.

### 3.9 Class 9 — Audit-finding remediation

**In scope.** Response to internal and external audit
findings — acceptance of the finding, remediation plan,
plan ratification, closure.

**R.** The Head of Internal Audit tracks. The category
owner or operational body chair whose scope the finding
falls in drafts the remediation plan.

**A.** The AIGC ratifies the remediation plan.

**C.** GC (regulatory-adjacent findings), CFO (cost
implications), affected operational body (substance).

**I.** BAC (ack), Board (via BAC annual).

**Threshold.** No dollar threshold. All findings — Critical,
High, Medium, Low — enter the workflow, with cadence
scaled to severity.

**Decision record.** Framework Appendix C template.

**Escalation path.** Findings rated Critical or High
automatically trigger BAC deep-dive per framework §8.2.
Where the AIGC and the finding source (typically Internal
Audit) disagree on acceptance or remediation, the
disagreement escalates to the BAC.

**Archive.** Internal Audit archive with AIGC cross-
reference.

### 3.10 Class 10 — Individual-system operating decisions

**In scope.** Day-to-day operating decisions within the
guardrails set by the ARB (reference architecture,
platform-tenancy admission conditions) and the RAIB
(responsible-AI classification, RAIB posture). Examples:
feature-flag change, model-version increment within a
version series, retraining within an approved cadence,
capacity increment within an approved envelope, log-
retention parameter within policy.

**R.** Platform-team lead (Plat-Lead) or Sub-Team.

**A.** Plat-Lead or BU-Exec per business-unit delegation
(the delegation itself is a Class 3 sub-record ratified at
the deployment approval; a Class 10 outcome outside the
delegation is out-of-scope for Class 10).

**C.** ARB via guardrails, not per-decision. RAIB via
guardrails, not per-decision.

**I.** AIGC via aggregate reporting on the dashboard.

**Threshold.** By definition, within the Class 3 and Class 5
guardrails. An operating decision that would take the
system outside the guardrails is not Class 10; it is Class
3 (deployment re-approval) or Class 5 (posture change).

**Decision record.** Platform-team operating log with
guardrail-compliance assertion.

**Escalation path.** A pattern of Class 10 decisions
approaching the guardrail (frequency, magnitude, or
proximity to a threshold) is a signal for ARB Tier 1
review at the next weekly meeting. Individual decisions do
not escalate.

**Archive.** Platform-team operating log; the AIGC dashboard
consumes aggregate metrics.

---

## 4. Escalation

### 4.1 Standing escalation matrix

| From | To | Trigger |
|---|---|---|
| Operational body (ARB / RAIB / IPB / EVRB) | AIGC | Interface dispute; dissent above the body's threshold; scope-ambiguity recurrence; framework-adherence self-flag |
| AIGC | BSC | Framework amendments (Class 1); scope-definition ratification; strategic-posture positions (Class 7b) |
| AIGC | BAC | Compliance-and-audit posture changes; portfolio-composition annual review; Class 9 items above BAC-reporting threshold; regulatory-classification decisions of Board consequence |
| AIGC | BRC (where present) | AI risk-appetite matters; enterprise-risk-register AI entries; incident-response oversight items |
| BSC / BAC / BRC | Full Board | Items where the committee cannot ratify within its own authority |
| Any body | AIGC Chair (emergency) | Time-sensitive Class 2, 3, 8b items outside standard cadence |

### 4.2 Escalation cadence

- Routine escalation: at the next standing meeting of the
  receiving body.
- Priority escalation: within five business days.
- Emergency escalation (Class 8b, regulator notice,
  Critical audit finding): within one business day; the
  receiving body convenes emergency session per its charter.

### 4.3 De-escalation

- The AIGC may return an escalated item to the
  originating operational body with an argued
  instruction (re-work, additional consultation, defer).
- The BSC / BAC / BRC may return an item to the AIGC with
  an argued instruction.
- The Board may return an item to the ratifying committee
  with an argued instruction.

De-escalation is a first-class decision and is archived.

---

## 5. Thresholds (annual)

Threshold values are set annually by the AIGC in
coordination with the CFO and published as an appendix to
this RACI. The reference framework provides indicative
values; each Halcyon subsidiary sets its own within the
group envelope.

| Class | Threshold criterion | Indicative value (reference) |
|---|---|---|
| 3 | Deployment revenue exposure (annual, per system) | $10M+ |
| 3 | Customer count | 100+ enterprise or 100,000+ end-users |
| 3 | Safety classification | Any RAIB safety-critical classification |
| 3 | Aggregate deployment spend (per system, first-year) | $5M+ |
| 4a | Portfolio-allocation single decision | $25M+ |
| 4a | Category-rebalancing amount | 5%+ of category envelope |
| 4b | Delegated Cat-Owner routine allocation | Within category envelope, no floor |
| 8a Medium / High | Per CISO matrix | Reviewed annually |
| 8b Critical | Per CISO matrix | Reviewed annually |
| 9 (Board reporting) | Aged findings not remediated within SLA | Any Critical or High, 6+ months open |

Threshold rules:

- **Multiple thresholds met.** Where a decision meets more
  than one threshold criterion, the higher-authority row
  applies. A Class 3 deployment that also has Class 2
  regulatory-classification implications runs the Class 2
  RACI in parallel; the Class 3 approval requires the
  Class 2 record on file.
- **Threshold at the boundary.** Decisions within 10% of
  a threshold on either side may be routed to the higher-
  authority row by the AIGC Chair's judgement, especially
  where the direction of the boundary is unclear (e.g.,
  revenue exposure grows during the deployment period).
- **Threshold amendments.** Threshold amendments are Class
  1 (framework and policy) decisions. Threshold refreshes
  at the annual review are not framework amendments if
  they update indicative values without changing the
  criteria.

---

## 6. RACI amendment

### 6.1 Recommendation

The AIGC recommends RACI amendments. Recommendations are
drafted through the Secretariat and reviewed at a monthly
AIGC meeting.

### 6.2 Ratification

- **Class 1 amendments** (adding or removing a decision
  class, changing an A role, changing threshold criteria)
  require BSC ratification.
- **Non-Class-1 amendments** (adding a C, changing a C to
  C (veto), refining a role name, updating a threshold
  indicative value) require AIGC ratification with BSC-
  liaison awareness.
- **Operational amendments** (correcting a role short-form,
  clarifying a threshold rule without changing it) may be
  approved by the AIGC Chair with Secretariat archival
  discipline.

### 6.3 Effective date

Amendments become effective on the ratification date and
are reflected in the framework changelog (framework §13).
Amendments do not retroactively re-classify decisions
already taken; already-taken decisions are archived under
the RACI version in force at the decision date.

### 6.4 Version tracking

- The current-version RACI is at `HEAD` in this document.
- The version history is in the framework changelog
  (framework §13).
- Superseded versions are archived per framework §9.5.

---

## 7. Reading the RACI in practice

### 7.1 Worked example — a Class 3 deployment with RAI implications

A business unit proposes to deploy a customer-facing AI
recommender that RAIB has classified as Responsible-AI-
class 2 (transparency and appeal obligations apply). Revenue
exposure crosses the Class 3 threshold.

The RACI reads:

1. The Sub-Team drafts the deployment approval with the
   ARB (Chair as R). Reference-architecture conformance,
   platform-tenancy admission, technology-selection
   references, security / data / privacy / unit-economics
   assessments assembled.
2. RAIB (C with veto) reviews the RAI classification and
   the operating implications. RAIB sign-off is required.
3. CISO (C with veto) reviews the security-boundary
   implications. Sign-off required.
4. CDO and CPO-Priv (C) review data-flow and personal-
   data implications. Sign-off required.
5. BU-Exec (C) confirms operational readiness.
6. Plat-Lead (C) confirms platform-team readiness.
7. FinOps seat via ARB (C) confirms unit-economics
   assessment.
8. ARB decides at Tier 2. Vote recorded per ARB charter
   §4.
9. CIO (A) signs the deployment approval.
10. The AIGC (I) is informed at the next monthly meeting;
    the deployment is on the next quarterly dashboard.
11. The IPB (I) is informed if the system graduated from
    innovation.
12. The EVRB (I) is informed and reviews the public
    announcement per its own tiering (routed as Class
    7a / 7b as applicable).

Any missing R, A, or C (veto) signature blocks deployment.
An I omission is a workflow failure but does not invalidate
the deployment.

### 7.2 Worked example — a Class 4a rebalancing above threshold

The CFO capital-planning cycle proposes to shift $30M from
Innovation-portfolio to Core-platform on the basis of the
prior year's platform-multiplier outcome.

The RACI reads:

1. The Cat-Owners for Innovation-portfolio and Core-
   platform (co-R) draft the memo per framework Appendix
   B.
2. The AIGC (co-R via Secretariat) drafts the portfolio-
   composition impact analysis.
3. AIGC Chair (C), GC (C for regulatory-adjacent), CISO
   (C for security-adjacent), other Cat-Owners (C).
4. CFO (A) ratifies.
5. BAC (I ack) receives the change; it appears in the
   annual portfolio-composition-and-outcome review.
6. Board (I) receives via the annual portfolio report.

Missing C (veto) is not defined for this class; missing C
from Cat-Owners is a workflow failure and the CFO cannot
ratify without their input.

### 7.3 Worked example — a Class 2 regulatory classification

An LLM-based agent used inside Halcyon's field-service
routing may fall under the EU AI Act's high-risk AI system
scope for safety-component-of-a-machine deployment.

The RACI reads:

1. GC (R) drafts the classification memo per framework
   Appendix A.
2. RAIB (C), CISO (C), CPO-Priv (C), ARB (C), BU-Exec (C)
   contribute their substantive views.
3. AIGC (A) ratifies. AIGC decision rule (framework §3.5)
   governs.
4. BSC liaison, BAC, HIA (I ack) receive the classification.
5. The classification becomes an input to Class 3
   (deployment) and Class 5 (responsible-AI posture)
   decisions.

The record is retained per framework §9.5 extended-
retention.

### 7.4 Worked example — an unfilled role

Suppose the Chief Data Officer role is unfilled during a
transition. The RACI is read against the framework §12
successor register: the Deputy Chief Data Officer serves
as the acting incumbent. All C rows requiring CDO input
route to the Deputy for the transition period.

If the Deputy is also unfilled: the AIGC ratifies an
interim delegate (typically the Head of Data Platform
Engineering) with a stated end date. Decisions requiring
the CDO's C input during the vacancy are archived with
the interim-delegate signature and the AIGC ratification
of the delegate.

A vacancy without a successor recorded appears on the AIGC
dashboard framework-health panel.

---

## 8. Related documents

- `../SOLUTION.md` — the reference solution defending the
  reasoning behind this RACI.
- `../framework/enterprise-ai-governance-framework.md` — the
  enterprise framework this RACI operates under.
- `../governance/architecture-review-board-charter.md` — the
  ARB charter whose Class 3, Class 8 (architecture change),
  and Class 10 (guardrails) authorities anchor the ARB
  columns in this RACI.
- `../rubric/evaluation-rubric.md` — the grading rubric
  graders apply to learner submissions.
- `../../project-403-responsible-ai-framework/governance/`
  — the RAIB charter whose Class 5 and Class 8b
  authorities anchor the RAIB columns in this RACI.
- `../../project-404-innovation-program-design/governance/`
  — the IPB charter whose Class 6 authority anchors the
  IPB column.
- `../../project-405-industry-thought-leadership/governance/external-voice-charter.md`
  — the EVRB charter whose Class 7 authority anchors the
  EVRB column.
