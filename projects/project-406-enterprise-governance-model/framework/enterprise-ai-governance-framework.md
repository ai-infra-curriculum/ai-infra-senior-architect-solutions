# Enterprise AI Governance Framework

> Reference framework for the Halcyon enterprise AI governance
> model. Read alongside `../SOLUTION.md` (the reasoning) and
> `../governance/architecture-review-board-charter.md` and
> `../governance/decision-authority-raci.md` (the operating
> artifacts). This framework composes with the responsible-AI
> framework (Project 403), the innovation-programme design
> (Project 404), and the external-voice programme (Project
> 405), rather than replacing any of them.

**Version**: 1.0
**Status**: Reference framework
**Owner**: Board Strategy Committee (ratification); Chief
Information Officer (operational chair of the AIGC)

---

## 1. Purpose

This framework establishes the enterprise-level AI governance
model for Halcyon Industrial Group. Its purpose is to make
sure every in-scope AI decision has:

- **A defined scope test**, so no decision falls between
  bodies and no decision routes to three bodies
  unnecessarily.
- **A defined authority**, so the role that decides each
  class of decision is enumerated and known ex ante.
- **A defined governance body**, so the operational body
  with substantive expertise makes the substantive call
  without the enterprise being unable to see the aggregate.
- **A defined evidence trail**, so audit and Board oversight
  can be discharged from records generated in the ordinary
  course of the workflow.

The framework does not replace the four existing
operational bodies (the AI Architecture Review Board, the
Responsible AI Board, the Innovation Portfolio Board, and
the External Voice Review Board). It defines their scope,
their interfaces, and the enterprise-level AI Governance
Committee that sits above them and reports to the Board.

---

## 2. Scope

### 2.1 Inclusive test

A decision is inside the enterprise AI governance scope if
it satisfies at least one of:

1. **Data test.** The decision commits Halcyon to build,
   buy, deploy, or continue operating a system whose output
   materially depends on statistical inference from
   training or reference data. The test is functional; the
   vocabulary used by the project team does not affect the
   test.
2. **Autonomy test.** The decision commits Halcyon to a
   system that takes actions on Halcyon's or a customer's
   behalf whose action space is not fully enumerable ex
   ante, even where a human is nominally in the loop.
3. **Regulatory test.** The decision commits Halcyon to a
   system that would be a "high-risk AI system" under the
   EU AI Act, an "AI system" under NIST AI RMF, or under
   the scope of ISO/IEC 42001 or a sector-specific AI
   supervisory regime.
4. **Reputation test.** The decision commits Halcyon to a
   system that would reasonably be characterised by an
   external reader as "an AI system" — for example, a
   public product-page description, a customer-facing
   narrative, or a regulator submission using the term.

### 2.2 Exclusive test

A decision is outside the enterprise AI governance scope if
all of the following hold:

- The system's outputs are deterministic functions of its
  inputs.
- The system does not sit within a regulated boundary that
  requires AI classification.
- The system's failure modes are already covered by an
  existing governance domain (functional safety,
  cybersecurity, data privacy, product safety) at a depth
  those domains consider sufficient.

### 2.3 Ambiguity rule

Where scope is ambiguous, the decision is treated as
in-scope for the first review pass. The AI Architecture
Review Board triages inbound items and can rule an item
out of scope with an argued case; the AIGC ratifies
recurring rulings.

The reverse mis-routing (an item ruled out that later turns
out to be in-scope) is the primary failure mode the scope
tests are designed to prevent.

### 2.4 Scope changes

The scope tests are reviewed at each annual framework
review and re-approved by the Board Strategy Committee.
Interim amendments require AIGC recommendation and Board
Strategy Committee ratification; interim amendments are
rare and are recorded in the framework changelog.

---

## 3. The AI Governance Committee

### 3.1 Purpose

The AI Governance Committee (AIGC) is the enterprise-level
coordinating body for AI governance. It owns the framework
itself, the scope definition, the decision-class model, the
RACI, the portfolio-prioritisation model, the Board-
oversight instrumentation, and the compliance-and-audit
posture. It does not decide individual AI systems'
architecture, responsible-AI posture, innovation-portfolio
allocation, or external-communication surface use; those
are the operational bodies' authorities.

### 3.2 Composition

Fixed-role voting seats:

| Seat | Role |
|---|---|
| Chair | Chief Information Officer |
| Technology | Chief Technology Officer or delegate at that level |
| Finance | Chief Financial Officer delegate authorised for AI-portfolio commitments |
| Legal | General Counsel or delegate at that level |
| Security | Chief Information Security Officer or delegate at that level |
| Data | Chief Data Officer or delegate at that level |
| Privacy | Chief Privacy Officer or delegate at that level |
| ARB | Chair of the AI Architecture Review Board |
| RAIB | Chair of the Responsible AI Board (Project 403) |
| IPB | Chair of the Innovation Portfolio Board (Project 404) |
| EVRB | Chair of the External Voice Review Board (Project 405) |

Non-voting standing seats:

| Seat | Role |
|---|---|
| Internal Audit | Head of Internal Audit (present for records, does not vote to preserve audit independence) |
| Board liaison | Board Strategy Committee liaison; attends by invitation for framework amendments and quarterly review |
| Secretary | AIGC Secretariat (executes the archive; does not vote) |

### 3.3 Authority

The AIGC is binding on:

- **Framework amendments.** Recommends to the Board
  Strategy Committee for ratification. Interim operational
  amendments (agenda changes, non-substantive cadence
  adjustments) are within AIGC authority; substantive
  amendments require ratification.
- **Scope-definition ambiguity rulings.** Rules on
  ambiguous scope calls by the ARB or by any operational
  body.
- **Decision-class assignment for novel decision types.**
  Where a decision does not fit an existing class, the
  AIGC assigns the class or amends the class list.
- **RACI amendments.** Reviews and ratifies amendments to
  the enterprise RACI.
- **Portfolio-category ceilings.** Within the CFO-approved
  aggregate envelope, sets the category ceilings and their
  quarterly re-balancing.
- **Inter-body interface changes.** Where two operational
  bodies' scopes touch and a new interface is required, the
  AIGC ratifies.
- **Class 2 (regulatory-classification) decisions.**
  Whether a Halcyon AI system is classified under a
  specific regulatory regime; General Counsel is the
  responsible officer, AIGC is the ratifying body.
- **Class 9 (audit-finding remediation) plan
  ratification.** Reviews and ratifies remediation plans
  for audit findings; the Head of Internal Audit tracks
  execution.

The AIGC is advisory (not binding) on:

- **Individual-system architecture decisions.** ARB is the
  authority; the AIGC receives portfolio-level information.
- **Individual responsible-AI-posture decisions.** RAIB is
  the authority; the AIGC receives framework-level
  information.
- **Individual innovation-portfolio-allocation decisions
  within category.** IPB is the authority within the
  innovation category; the AIGC receives portfolio-level
  information.
- **Individual external-communication decisions.** EVRB is
  the authority per its tiered review; the AIGC receives
  strategic-posture-level information.

The AIGC is explicitly out of scope for:

- Individual model architecture, training, evaluation,
  or deployment decisions below the ARB threshold.
- HR decisions about individual AI-team members.
- Corporate decisions outside the AI portfolio (general IT
  investment, non-AI product decisions).
- Financial-reporting attestation (CFO scope) except where
  AI-related internal controls are the subject of the
  attestation.

### 3.4 Quorum

- Voting quorum is eight of the eleven voting seats,
  including Chair, Legal, and Finance as non-optional.
- Quarterly Board-review meetings require the Board
  Strategy Committee liaison to be present.
- Emergency convocation quorum is five voting seats
  including Chair or Chair's named delegate, Legal, and
  either Security or Finance.

### 3.5 Decision rule

- Consensus preferred. Where consensus is not reached, the
  AIGC decides by majority of voting seats present. Dissent
  is recorded.
- The Chair does not have a casting vote. Tied votes at
  routine AIGC meetings defer to the next meeting.
  Tied votes on time-sensitive items escalate to the Board
  Strategy Committee liaison with the choices and
  positions on record.
- Silent approval is not permitted. A seat that abstains
  does not count as a positive vote. A seat that does not
  attend records absence.

### 3.6 Cadence

- **Monthly standing meeting.** Standing 150 minutes.
  Reviews the framework's operating status, cross-body
  interface items, portfolio-category actuals against
  ceilings, the dashboard delta since prior month, and
  Class 2 or Class 9 items in queue.
- **Quarterly Board review.** Standing 90 minutes with the
  Board Strategy Committee liaison. Reports the quarterly
  dashboard, portfolio-composition changes, dissent
  above threshold, regulatory-posture changes, and
  incidents in the period.
- **Semi-annual portfolio review with CFO.** Standing 90
  minutes. Integrated into the enterprise capital-planning
  cycle.
- **Annual framework review.** Standing offsite. Reviews
  the framework end-to-end, re-approves scope tests,
  reviews decision-class model, ratifies RACI amendments,
  re-approves portfolio-category ceilings, refreshes
  policy register.
- **Emergency convocation.** For Critical-severity
  incidents, regulator notices, or Board Audit Committee
  direction, the AIGC convenes on the on-call rota within
  the same business day.

### 3.7 Dissent recording

Dissent is a first-class artifact. Every AIGC decision
records:

- Which seats voted for, which against, which abstained,
  which were absent.
- Dissenting positions in one to three sentences,
  contributed by the dissenter.
- Whether the dissent is procedural, substantive, or
  risk-based.
- The Board's response — did the dissent change the
  decision, the conditions, or nothing.

Dissent above a threshold (three or more voting seats on a
Class 1 or Class 2 decision) triggers automatic escalation
to the Board Strategy Committee liaison for awareness.

---

## 4. Governance principles

The framework operates against seven principles. Every
downstream decision derives from one of them.

1. **Accountability travels to a named role.** Every
   in-scope AI system has a named accountable role at the
   Halcyon-officer level, recorded in the system's
   governance record.
2. **Decisions are made at the appropriate authority
   level.** Decisions are enumerated by class; each class
   has a named authority in the RACI. Decisions above the
   authority escalate; decisions inside the authority do
   not require escalation.
3. **Bodies compose without overlap.** The four operational
   bodies decide within their scopes. No decision requires
   two bodies to agree without a defined interface; no
   decision falls between bodies.
4. **The Board and its committees discharge oversight, not
   management.** The Board sees a dashboard drawn from
   records outside management curation; the Board's
   questions and management's responses are governance
   artifacts.
5. **Investment prioritisation is portfolioed.**
   AI-adjacent spend is one portfolio, categorised,
   prioritised against argued criteria, and defended as a
   portfolio composition to the Board Audit Committee.
6. **Compliance is by-product, not project.** Regulatory,
   contractual, and audit obligations are mapped to
   workflow steps that produce evidence in the ordinary
   course of operation.
7. **The framework survives personnel change.** Every role
   in the framework has a named successor; the framework
   is reviewed on cadence regardless of leadership
   transitions.

---

## 5. Governance-body topology

### 5.1 Operational bodies

| Body | Scope | Charter reference |
|---|---|---|
| AI Architecture Review Board (ARB) | Architecture decisions; platform-tenancy models; reference architectures; technology selection above threshold; cross-system data-flow topology | `../governance/architecture-review-board-charter.md` |
| Responsible AI Board (RAIB) | Responsible-AI framework; bias-testing and fairness posture; transparency posture; safety-critical AI classification; AI-incident postmortem | `../../project-403-responsible-ai-framework/governance/` |
| Innovation Portfolio Board (IPB) | Innovation-portfolio allocation; R&D-spend prioritisation for exploratory AI; external-research partnerships; portfolio-level stage-gate decisions | `../../project-404-innovation-program-design/governance/` |
| External Voice Review Board (EVRB) | External-communication surface use; standards-body participation; analyst relations; executive-briefing programme; community-and-open-source posture | `../../project-405-industry-thought-leadership/governance/` |

### 5.2 Enterprise body

The AI Governance Committee (§3) coordinates the four
operational bodies and reports to the Board Strategy
Committee and Board Audit Committee.

### 5.3 Board-committee interfaces

| Board committee | AI-related oversight owned |
|---|---|
| Board Strategy Committee | Framework ratification; scope-definition ratification; annual framework review; deep dives on strategic-portfolio items |
| Board Audit Committee | Compliance-and-audit posture; audit-finding oversight; portfolio-composition annual review; regulatory-classification decisions of Board consequence |
| Board Risk Committee (where present) | Enterprise AI risk-appetite statement; enterprise-risk-register AI entries; incident-response oversight |

Where the Board Risk Committee does not exist as a separate
committee, its AI-oversight items merge into the Board Audit
Committee's agenda.

### 5.4 Inter-body interfaces

Interface disciplines between operational bodies are defined
so no decision requires two bodies to agree without a named
interface, and no decision falls between:

- **ARB ↔ RAIB.** Architecture decisions that materially
  change the risk profile of an RAIB-classified system
  require RAIB awareness at ARB's Tier B or above. RAIB
  responsible-AI classifications are inputs to ARB
  architecture review.
- **ARB ↔ IPB.** Innovation-stage systems moving from
  exploration to production require ARB architecture
  approval; ARB decisions on platform-hosting eligibility
  are inputs to IPB stage-gate reviews.
- **RAIB ↔ IPB.** Innovation-stage systems that would be
  responsible-AI-classified on production adoption are
  reviewed by the RAIB at defined stage gates during
  innovation. RAIB does not gate exploration.
- **EVRB ↔ RAIB.** External communication about Halcyon's
  responsible-AI posture is reviewed by the EVRB against
  the RAIB framework. RAIB does not decide publication
  surfaces; EVRB does not decide framework content.
- **EVRB ↔ ARB.** External communication describing
  Halcyon's AI architecture is reviewed by the EVRB
  against the ARB-approved reference architecture.
- **AIGC ↔ Board Strategy Committee.** Framework
  ratification; deep-dive convocation on strategic items.
- **AIGC ↔ Board Audit Committee.** Compliance-and-audit
  posture reporting; audit-finding oversight; portfolio
  annual review.
- **AIGC ↔ Board Risk Committee.** Risk-appetite input;
  incident-response reporting.

Where an interface is unclear or under-utilised, the AIGC
convenes an interface review at the next monthly meeting
and clarifies the interface at the next annual framework
review.

---

## 6. Decision classes

### 6.1 Enumerated classes

The framework enumerates ten decision classes. Full
authority mapping is in
`../governance/decision-authority-raci.md`.

| # | Class | Primary authority |
|---|---|---|
| 1 | Framework and policy decisions | Board Strategy Committee ratifies; AIGC recommends |
| 2 | Regulatory-classification decisions | AIGC decides; General Counsel R |
| 3 | AI system deployment decisions above threshold | ARB with RAIB consultation |
| 4 | Investment-portfolio allocation decisions | CFO ratifies; AIGC recommends |
| 5 | Responsible-AI posture decisions | RAIB decides |
| 6 | Innovation-portfolio decisions | IPB decides |
| 7 | External-communication decisions | EVRB decides per its tiered review |
| 8 | Incident-response decisions | CISO coordinates; RAIB substantive review; AIGC post-incident review |
| 9 | Audit-finding remediation decisions | Head of Internal Audit tracks; AIGC ratifies plans |
| 10 | Individual-system operating decisions | Platform-team leadership within guardrails |

### 6.2 Class thresholds

Where a class threshold is defined by dollar value, revenue
exposure, or customer count, the threshold is set annually
by the AIGC in coordination with the CFO. Thresholds are
published in the RACI.

### 6.3 Novel decision types

Where a decision does not fit an existing class, the
proposing body routes the decision to the AIGC for class
assignment. The AIGC may assign to an existing class or
propose an amendment to the class list.

---

## 7. Investment prioritisation and portfolio management

### 7.1 Portfolio categories

AI-adjacent spend is categorised into five categories:

| Category | Scope | Funding authority |
|---|---|---|
| Core-platform | Shared platform and enabling capabilities (Project 402) | CIO / CTO under CFO envelope |
| Business-line-AI | AI systems owned by specific business units for specific business outcomes | Business unit under CFO envelope |
| Responsible-AI-operations | Operating cost of the responsible-AI framework (bias testing, transparency artifacts, safety evaluation, audit evidence) | RAIB under CFO envelope |
| Innovation-portfolio | Exploratory AI spend as governed by IPB (Project 404) | IPB under CFO envelope |
| External-programme | External-voice programme operating cost (Project 405), standards participation, community and open-source | EVRB under CFO envelope |

Each category has a ceiling within the CFO-approved AI
aggregate envelope. Ceilings are re-balanced quarterly by
the AIGC within the aggregate; the aggregate is
re-approved semi-annually with the CFO.

### 7.2 Prioritisation criteria

Within each category, prioritisation runs against five
published criteria:

1. **Expected outcome value** measured against the
   category-relevant metric (business outcome for
   Business-line-AI; utility metric for Core-platform;
   compliance-obligation coverage for Responsible-AI-
   operations; strategic-option value for Innovation-
   portfolio; influence outcome for External-programme).
2. **Strategic option value** — value created by preserving
   the ability to make a subsequent decision (e.g., early
   platform investment that enables a business-unit AI
   system in two years' time).
3. **Regulatory-exposure reduction** — value created by
   reducing Halcyon's exposure to specific regulatory
   obligations or audit findings.
4. **Platform-multiplier effect** — value created by the
   spend generating capability re-used by other Halcyon
   AI systems.
5. **Defensibility of alternatives** — value discounted by
   the availability of a cheaper or better alternative
   (buy versus build; open-source versus commercial;
   internal versus external).

Criteria are not weighted with a single formula. Individual
category prioritisation may weight the criteria differently
(Innovation-portfolio weights strategic-option value
heavily; Responsible-AI-operations weights regulatory-
exposure reduction heavily). Weightings are set annually
by category owners with AIGC and CFO consent.

### 7.3 Review cadence

| Cadence | Reviewer | Scope |
|---|---|---|
| Quarterly | AIGC | Portfolio composition at category level; category rebalancing within envelope |
| Semi-annually | CFO capital-planning process | AI aggregate envelope for enterprise capital plan |
| Annually | Board Audit Committee | Portfolio-composition-and-outcome report |

Off-cadence portfolio decisions are permitted only for
material and time-critical items (regulator notice,
Critical incident, contractual obligation). The AIGC chair
convenes off-cadence review.

### 7.4 Portfolio transparency

The portfolio composition, category ceilings, actual spend,
and criteria weightings are visible to all AIGC members and
to the CFO's capital-planning office. Business-unit level
detail below category is visible to the respective business
unit and its AIGC representative.

---

## 8. Board-level oversight

### 8.1 AIGC dashboard

The AIGC dashboard is delivered quarterly to the Board
Strategy Committee and Board Audit Committee. The dashboard
is drawn from records outside AI-programme management —
Internal Audit records, CFO records, CISO records, HR
records — and is a report, not a presentation.

The dashboard has six panels:

| # | Panel | Source |
|---|---|---|
| 1 | Portfolio composition — actual against envelope, drift arrows | CFO records; category-owner records |
| 2 | Decision-authority activity — decisions by class; escalations; dissent | AIGC and operational-body archives |
| 3 | Regulatory posture — in-scope systems by classification; changes in period; regulator activity | General Counsel and RAIB records |
| 4 | Incident record — AI incidents by severity; MTTD and MTTR; Board-notification triggers | CISO and RAIB incident logs |
| 5 | Audit posture — open findings; remediation status; aged findings against SLA | Internal Audit records |
| 6 | Framework health — named-role vacancy rate; framework-review status; policy-refresh status | HR records; framework changelog |

Panels are delivered as data plus a one-page management
commentary. The Board reads the data first.

### 8.2 Deep-dive triggers

The framework enumerates thresholds that trigger a Board-
level deep dive:

- Critical-severity AI incident.
- Audit finding rated High or Critical.
- Regulatory notice, consultation, or investigation
  touching a Halcyon AI system.
- Portfolio-category drift beyond stated tolerance (each
  category defines its tolerance at annual review).
- Two consecutive quarters of missed dashboard reporting
  (framework-health failure).
- Framework amendment proposals with material scope,
  authority, or oversight impact.
- Two consecutive quarters of a headline dashboard metric
  outside the AIGC's stated tolerance band.

The Board Chair may convene a deep dive outside the
triggers. The triggers exist to force convocation that the
Chair might otherwise defer.

### 8.3 Board-committee AI-oversight charters

Board Strategy Committee: framework ratification, scope-
definition ratification, annual framework review, strategic-
portfolio deep dives.

Board Audit Committee: compliance-and-audit posture, audit-
finding oversight, portfolio-composition-and-outcome
annual review, regulatory-classification decisions of Board
consequence, incident deep dives.

Board Risk Committee (where present): AI risk-appetite
statement, enterprise-risk-register AI entries, incident-
response oversight, and top-decile-risk deep dives.

A director on more than one committee is aware which hat is
on for AI oversight questions. The AIGC's Board liaison
coordinates.

---

## 9. Compliance and audit

### 9.1 Regulatory-obligation register

The AIGC maintains the regulatory-obligation register. For
each applicable regulation, the register lists:

- The regulatory instrument (e.g., EU AI Act Article 9,
  Article 10, Article 15).
- The obligation in operating terms (e.g., "risk-management
  system in place across the AI system lifecycle").
- The workflow step or steps that generate the evidence
  for the obligation.
- The archive location for the evidence.
- The named responsible role.
- The review cadence for the mapping.

New obligations enter the register before their effective
date. Obligations without a mapped workflow step are
treated as gaps and remediated.

### 9.2 Evidence by workflow

Every workflow that produces a governance artifact produces
the artifact in an audit-retrievable form by default:

- Named submitter, named reviewers, decision date, decision
  outcome, conditions, and dissent records.
- Retention per the archive-retention policy (§9.5).
- Access control per the archive-access-control policy.
- Chain of custody: amendments are new records, not edits
  to old records; the audit trail is preserved.

### 9.3 Internal Audit programme

The Head of Internal Audit maintains a rolling AI-audit
programme on a three-year cycle covering:

- Framework adherence at each operational body.
- Regulatory-obligation-register completeness and evidence
  presence.
- Portfolio-model integrity — category ceilings, actuals,
  and criteria weightings.
- Board-oversight-dashboard data provenance and integrity.
- Incident-response effectiveness — detection, escalation,
  remediation.
- RACI adherence — decisions taken by the RACI-defined
  authority.

Findings enter the framework's remediation workflow (Class
9) and are reported on the AIGC dashboard and to the Board
Audit Committee.

### 9.4 External-audit readiness

External auditors — statutory auditors reviewing AI-related
disclosures, ISO/IEC 42001 certification bodies, EU AI Act
notified bodies, sector-specific supervisors — are served
from the same archives Internal Audit uses. Where a
specific external audit requires additional artifacts,
those artifacts are generated once and archived alongside
the existing evidence.

The framework does not run a separate "audit preparation"
programme. If evidence is not present in the ordinary
archive on the day of the audit notice, the ordinary
workflow discipline has failed and the failure is a
framework-health issue, not an audit-preparation issue.

### 9.5 Archive retention

- Standard retention: seven years from decision date.
- Extended retention: standards-body decisions and
  regulatory-consultation content retained per the
  applicable standard or regulatory retention rule.
- Extended retention: safety-critical AI-system decisions
  retained for the duration of the system's operating life
  plus seven years.
- Regulatory-classification decisions and their evidence
  retained per applicable regulatory recordkeeping
  requirements (typically ten years, longer where
  specified).

### 9.6 Archive access

- AIGC and operational-body members have full read access
  to their scope.
- Internal Audit and external audit have read access on
  request, unmediated.
- Content submitters have read access to their own
  submissions.
- Access is logged. Access anomalies are reviewed monthly
  by the CISO.

---

## 10. Policy register

### 10.1 Enterprise AI policies

The framework maintains an enterprise policy register.
Policies with mandatory scope include (non-exhaustive):

| Policy | Owner | Review cadence |
|---|---|---|
| AI-system acceptable-use policy | AIGC | Annual |
| Third-party-AI procurement policy | Procurement + AIGC | Annual |
| Data-for-AI use policy | Chief Data Officer + AIGC | Annual |
| Personal-data-in-AI privacy policy | Chief Privacy Officer + AIGC | Annual |
| AI-employee conduct policy | HR + AIGC | Annual |
| AI incident-response policy | CISO + RAIB | Annual |
| AI security policy | CISO + AIGC | Annual |
| Foundation-model use policy | AIGC + RAIB | Semi-annual (rapidly evolving domain) |
| Open-source-AI contribution policy | EVRB + Legal | Annual |
| Standards-body-participation policy | EVRB + AIGC | Annual |

Each policy is owned by a named role and reviewed on
cadence. The AIGC ratifies policy changes at the framework
level; policy owners maintain the operating detail.

### 10.2 Policy hierarchy

Enterprise AI policies compose with (and do not override)
enterprise general policies (Code of Conduct, information-
security, privacy, procurement). Where an enterprise general
policy and an enterprise AI policy touch the same subject
matter, the AI policy adds AI-specific requirements without
softening the general policy.

### 10.3 Policy exceptions

Exception requests are:

- Submitted to the policy owner with an argued case.
- Reviewed against the policy owner's exception criteria.
- Recorded in the policy-exception register with expiry
  date and remediation plan.
- Reported to the AIGC quarterly.

Standing exceptions are not permitted. All exceptions have
an expiry date.

---

## 11. Framework refresh cadence

### 11.1 Annual review

The AIGC conducts an annual framework review, ratified by
the Board Strategy Committee, covering:

- Scope tests (re-approval or amendment).
- Governance principles (re-approval).
- Governance-body topology (re-approval; interface review).
- Decision-class model (re-approval; class amendments).
- RACI (re-approval; role and threshold amendments).
- Portfolio-category ceilings and criteria weightings.
- Board-oversight dashboard panels and deep-dive triggers.
- Compliance-and-audit posture and regulatory-obligation
  register.
- Policy register status.
- Named-role successor register status.

The annual review produces a framework changelog entry with
approved amendments and their effective dates.

### 11.2 Interim amendments

Interim amendments are permitted for:

- Regulatory changes requiring immediate compliance
  posture updates.
- Board Strategy Committee direction.
- Critical incident post-mortem recommendations.
- Framework-health failures requiring policy or
  cadence adjustment.

Interim amendments are ratified by the Board Strategy
Committee where they touch Class 1 authority. Non-Class-1
interim amendments may be ratified by the AIGC and reported
to the Board Strategy Committee at the next quarterly
review.

### 11.3 External review

At each Phase 3 external review (initially at month 18–24,
then triennially), the framework is reviewed against:

- Peer-organisation governance disclosures.
- ISO/IEC 42001 certification-body observations (where
  Halcyon is certified or is pursuing certification).
- EU AI Act compliance-audit findings (where applicable).
- IIA Three Lines Model reviews (where Internal Audit
  requests external validation).

External review results are reported to the Board Strategy
Committee and Board Audit Committee.

---

## 12. Named-role successor register

Every named role in the framework has:

- A named incumbent.
- A named successor (either a specific role or a specific
  named person; the reference framework prefers named
  role, e.g., "Deputy General Counsel" over a named
  person).
- A transition-handover checklist.

The successor register is reviewed at the annual framework
review and on every role transition. A role transition
without a successor on record is a framework-health event
recorded on the dashboard.

---

## 13. Framework changelog

Framework amendments are recorded in a changelog:

- Amendment number and effective date.
- Ratifying body (Board Strategy Committee for Class 1;
  AIGC otherwise).
- Section amended.
- Substance of the amendment.
- Reference to the decision record.

The changelog is the authoritative history of the framework
and is public within Halcyon (accessible to all AIGC
members, operational-body members, Internal Audit, and the
Board committees). The changelog is retained per the
archive-retention policy.

---

## Appendix A — Class 2 (regulatory classification) decision template

Template used for Class 2 decisions:

```
Regulatory-Classification Decision Record
─────────────────────────────────────────

System identifier: <system name and internal ID>

Owning business unit: <business unit>

Named accountable role: <role, not person>

Applicable regulatory instrument(s):
  - <e.g., EU AI Act, Article X; NIST AI RMF; ISO/IEC 42001>

Argued classification:
  <two paragraphs against the regulatory tests>

Referenced technical inputs:
  <references to ARB, RAIB, IPB records>

General Counsel opinion:
  <signed opinion or reference to signed opinion>

AIGC decision:
  Classification: <e.g., High-risk AI System per EU AI Act>
  Vote: <for / against / abstain / absent per seat>
  Dissent: <recorded>

Conditions attached:
  <ongoing obligations attached to the classification>

Next review:
  <re-classification review date>

Archive location:
  <archive identifier>
```

---

## Appendix B — Class 4 (portfolio-allocation) decision template

Template used for Class 4 decisions above the AIGC-delegated
threshold:

```
Portfolio-Allocation Decision Record
─────────────────────────────────────

Category: <Core-platform / Business-line-AI / Responsible-
           AI-operations / Innovation-portfolio /
           External-programme>

Category ceiling and current actual:
  <numbers>

Proposed allocation:
  <numbers>

Prioritisation-criteria evaluation:
  - Expected outcome value: <argument>
  - Strategic option value: <argument>
  - Regulatory-exposure reduction: <argument>
  - Platform-multiplier effect: <argument>
  - Defensibility of alternatives: <argument>

Category-owner recommendation:
  <recommendation>

CFO delegate assessment:
  <assessment>

AIGC decision:
  Approved / declined / deferred
  Vote: <per seat>
  Dissent: <recorded>

Effect on aggregate envelope:
  <numbers>

Next review:
  <quarterly review date at which actuals will be assessed>

Archive location:
  <archive identifier>
```

---

## Appendix C — Class 9 (audit-finding remediation) template

Template used for audit-finding remediation plans:

```
Audit-Finding Remediation Plan
──────────────────────────────

Finding source: <Internal Audit / ISO/IEC 42001 body /
                  EU AI Act notified body / statutory
                  auditor / sector supervisor>

Finding identifier: <auditor's identifier>

Finding severity: <Critical / High / Medium / Low>

Finding summary:
  <auditor's finding text>

Halcyon acceptance:
  Accepted / partially accepted with argued position /
  contested with argued position

Remediation plan:
  <steps, owners, target dates>

Interim mitigation:
  <if any; especially for High or Critical findings>

AIGC ratification:
  <date, vote, dissent>

Internal Audit tracking:
  <tracking identifier>

Target closure date:
  <date>

Board Audit Committee reporting:
  <schedule>

Archive location:
  <archive identifier>
```

---

## Related documents

- `../SOLUTION.md` — the reference solution defending the
  reasoning behind this framework.
- `../governance/architecture-review-board-charter.md` — the
  reference ARB charter.
- `../governance/decision-authority-raci.md` — the reference
  enterprise RACI.
- `../rubric/evaluation-rubric.md` — the grading rubric
  graders apply to learner submissions.
- `../../project-402-global-ai-platform-architecture/` — the
  global platform whose ARB this framework composes with.
- `../../project-403-responsible-ai-framework/` — the
  Responsible AI framework whose RAIB this framework
  composes with.
- `../../project-404-innovation-program-design/` — the
  Innovation Portfolio Board this framework composes with.
- `../../project-405-industry-thought-leadership/` — the
  External Voice Review Board this framework composes with.
