# SOLUTION — Enterprise AI Governance Model

> Read this *after* you have drafted your own enterprise AI
> governance model. This is the reasoning the reference design
> is defending, not a scoring key. A different model that
> defends the same properties is a valid answer.

## 1. Solution overview

A senior architect answers five questions in an enterprise AI
governance review:

1. **What is inside the AI governance scope, and what is
   deliberately not?** — the scope question. Frameworks that
   skip this drift into "all technology decisions with any AI
   content route to the AI Governance Committee," which is
   how governance bodies suffocate their own decision-making
   capacity within two quarters.
2. **Who decides what, by role, not by title?** — the
   authority question. Every failure mode of an enterprise
   governance model lives on the spectrum between "the CEO
   decides everything" (unscalable, and the CEO does not
   actually decide it — a proxy does, without accountability)
   and "the working group decides everything" (unscalable
   the other direction, and no one at Board level can defend
   the aggregate). The reference model picks defensible
   points on that spectrum for each decision class and
   defends them.
3. **How do the existing AI-governance bodies compose without
   overlap or gap?** — the topology question. Halcyon has
   accumulated bodies for a reason; a framework that ignores
   them and centralises everything into a new body earns the
   opposition of every business unit that trusts one of the
   existing bodies.
4. **How does AI investment get prioritised as a portfolio,
   not as an approval queue?** — the portfolio question. A
   framework whose investment model is "approve if net-
   present-value positive" reduces every AI decision to a
   spreadsheet contest and hides the strategic-optionality
   value the CFO knows exists but cannot separately quantify.
5. **How does the Board discharge its oversight duty in a way
   that would survive a fiduciary-duty test?** — the Board
   question. The Board is not the AI decision-maker; it is
   the AI decision-overseer. A framework that gives the
   Board a narrative-only briefing is a framework whose
   Board members' individual liability exposure is
   unmanaged.

The reference target state is a **scope-defined, role-based,
composed-body AI governance framework** operating an
enterprise AI Governance Committee that sits above four
existing operational bodies (AI Architecture Review Board,
Responsible AI Board, Innovation Portfolio Board, External
Voice Review Board), reports on a defined dashboard to the
Board Strategy and Audit Committees, runs the AI investment
portfolio against argued categorisation, and produces audit
evidence as a by-product of the workflow.

The **key trade-off accepted** is between the desire for a
single centralised AI decision body (which would be
politically simpler and structurally weaker) and the
observed reality that Halcyon's existing bodies each cover
a distinct decision class with defensible expertise. The
reference model composes them; the cost is interface
discipline. The reference model accepts that cost and
defends it, because the alternative — collapsing four
domain-specific bodies into one committee — produces exactly
the "everything routes to the AI Governance Committee" failure
mode.

## 2. Worked answer (the reference framework)

### 2.1 The scope definition (what is inside AI governance)

The reference framework opens with a written scope definition
in three components: the inclusive test, the exclusive test,
and the ambiguity rule.

**Inclusive test.** A decision is inside enterprise AI
governance if it satisfies at least one of:

- **Data test.** The decision commits Halcyon to build, buy,
  deploy, or continue operating a system whose output
  materially depends on statistical inference from training
  or reference data (whether that inference is called machine
  learning, AI, statistical modelling, or otherwise). The
  test is functional, not vocabulary-based; a "rule-based"
  system whose rules are fitted to historical data is inside
  the definition.
- **Autonomy test.** The decision commits Halcyon to a system
  that takes actions on Halcyon's behalf, or on a customer's
  behalf, whose action space is not fully enumerable ex
  ante — even if a human is nominally in the loop for each
  action.
- **Regulatory test.** The decision commits Halcyon to a
  system that would be a "high-risk AI system" under the EU
  AI Act, an "AI system" under NIST AI RMF, or under the
  scope of ISO/IEC 42001, regardless of what Halcyon calls
  it internally.
- **Reputation test.** The decision is externally visible
  (public product, customer-facing narrative, regulator
  submission) and would be reasonably characterised by the
  general reader as "an AI system."

**Exclusive test.** A decision is *not* inside enterprise AI
governance if all of the following hold:

- The system's outputs are deterministic functions of its
  inputs (no learnt component, no probabilistic action
  choice).
- The system does not sit within a regulated boundary that
  requires AI classification (EU AI Act, product-safety
  regime with AI amendments, financial-services AI-
  supervision, healthcare-device AI classifications).
- The system's failure modes are covered by an existing
  governance domain (functional safety, cybersecurity,
  data privacy, product safety) at a depth those domains
  consider sufficient.

**Ambiguity rule.** Where scope is ambiguous, the decision
is treated as *inside* the AI governance scope for the first
review pass. The Architecture Review Board triages inbound
items and can rule an item out of scope with a documented
argument. The reverse — an item routed out that later turns
out to be in — is the failure mode governance is designed to
prevent.

**Why explicit, functional tests and not a definition.** A
definition of "AI" that starts "AI is..." accumulates edge
cases the first time someone with a rule-based expert system
argues they are inside or outside the definition depending on
whether it helps them. Functional tests are auditable: an
auditor can walk from the tested property back to a specific
system and back forward to its governance path. The reference
framework accepts the cost of maintaining the tests over the
cost of arguing definitions in each review.

**What the scope test is deliberately not.** The reference
framework does not gate on:

- The word "AI" appearing in project documentation. Trivially
  gameable, and creates perverse incentives to relabel work.
- The system's implementation stack (whether it uses a
  specific framework or library). Implementation stacks drift;
  the governance question is functional, not technological.
- The size of the training-data set. There is no natural
  threshold; small models are inside scope where their
  functional properties trigger the tests, and large models
  are outside scope where they do not (a large LLM used only
  as offline documentation search may not trigger any
  governance test even at scale).

### 2.2 The governance principles

The reference framework sets seven governance principles.
Every downstream decision derives from one of them, and every
principle survives an "explain it to the Board Audit
Committee" test.

1. **Accountability travels to a named role.** Every
   in-scope AI system has a named accountable role at the
   Halcyon-officer level. When a system fails in a way that
   requires enterprise response, the named role owns the
   response. The role, not the person, is the accountable
   party; role transitions do not create accountability gaps.
2. **Decisions are made at the appropriate authority level.**
   Decisions are enumerated by class; each class has a named
   authority level in the RACI. Decisions above the class
   authority escalate; decisions inside the class authority
   do not require escalation.
3. **Bodies compose without overlap.** The Architecture
   Review Board decides architecture; the Responsible AI
   Board decides responsible-AI posture; the Innovation
   Portfolio Board decides innovation-portfolio allocation;
   the External Voice Review Board decides external-voice
   surface use; the AI Governance Committee owns the
   enterprise framework and interoperability. No decision
   requires two bodies to agree without a defined
   interface; no decision falls between bodies.
4. **The Board and its committees discharge oversight, not
   management.** The Board sees a dashboard, not project
   updates. The Board's questions to management are recorded
   as governance artifacts; the responses are recorded as
   governance artifacts. Management does not brief the Board
   in narrative form to obscure operating detail.
5. **Investment prioritisation is portfolioed.** AI-adjacent
   spend is one portfolio, categorised, prioritised against
   argued criteria, and defended at the Board Audit Committee
   as a portfolio composition — not as a sum of individual
   project cases.
6. **Compliance is by-product, not project.** Regulatory,
   contractual, and audit obligations are mapped to workflow
   steps that produce evidence in the ordinary course of
   operation. Compliance audits find the evidence in place;
   compliance functions do not run a parallel data-gathering
   exercise on audit demand.
7. **The framework survives personnel change.** Every role
   in the framework has a named successor. The framework is
   reviewed on a defined cadence regardless of whether the
   incumbent CIO, CTO, CFO, or General Counsel changes.

**Why seven and not twenty.** A framework with twenty
principles has no operating principles. The reference
framework reduces to the smallest set that a director could
ask a management witness to defend, one principle at a time,
without the witness reaching for a cheat sheet.

### 2.3 The governance-body topology

The reference framework preserves the four existing bodies
and adds one coordinating body. It does not centralise.

**Enterprise AI Governance Committee (AIGC).** New. Owns the
enterprise AI governance framework itself, the scope
definition, the RACI, the portfolio-prioritisation model,
the Board-oversight instrumentation, and the compliance-and-
audit posture. Chaired by the Chief Information Officer.
Members are the four operational-body chairs plus General
Counsel, CFO delegate, CISO, Chief Data Officer, Chief
Privacy Officer, Head of Internal Audit (non-voting), and a
Board Strategy Committee liaison. Not a decision body for
individual AI systems; it is a decision body for the
framework and for cross-body coordination.

**AI Architecture Review Board (ARB).** Existing platform
body (Project 402), now with an explicit AI mandate under
the enterprise framework. Owns architecture decisions:
platform-tenancy models, reference architectures, integration
patterns, technology selection above a threshold, cross-
system data-flow topology. Composition and authority defined
in `governance/architecture-review-board-charter.md`.

**Responsible AI Board (RAIB).** Existing body (Project 403).
Owns responsible-AI framework itself, bias-testing and
fairness posture, transparency posture, safety-critical AI
classification, incident-and-postmortem review for AI-
system incidents. Framework in
`../project-403-responsible-ai-framework/`.

**Innovation Portfolio Board (IPB).** Existing body (Project
404). Owns innovation-portfolio allocation, R&D spend
prioritisation for exploratory AI work, external-research
partnership decisions, and portfolio-level go/no-go for
innovation-stage AI systems. Framework in
`../project-404-innovation-program-design/`.

**External Voice Review Board (EVRB).** Existing body
(Project 405). Owns external-communication surface use for
AI content, standards-body participation, analyst relations,
executive-briefing programme, community-and-open-source
posture. Framework in
`../project-405-industry-thought-leadership/`.

**Interfaces.** The AIGC defines interfaces between the four
operational bodies. Key interfaces:

- **ARB ↔ RAIB.** Architecture decisions that materially
  change the risk profile of a Responsible-AI-classified
  system require RAIB awareness at Tier B or above; RAIB
  positions on responsible-AI classification are inputs to
  ARB architecture review. Neither body overrules the
  other; disagreements escalate to the AIGC.
- **ARB ↔ IPB.** Innovation-stage systems moving from
  exploration to production require ARB architecture
  approval; ARB decisions on platform-hosting eligibility
  are inputs to IPB stage-gate reviews. Innovation-portfolio
  budget is not architecture approval and does not
  substitute for it.
- **RAIB ↔ IPB.** Innovation-stage systems that would be
  responsible-AI-classified on production adoption are
  reviewed by the RAIB at defined stage gates during
  innovation; the RAIB does not gate exploration by
  default. IPB retains portfolio-level authority.
- **EVRB ↔ RAIB.** External communication about Halcyon's
  responsible-AI posture is reviewed by the EVRB against
  the RAIB-owned framework; the EVRB does not redesign the
  framework; the RAIB does not decide publication surfaces.
- **AIGC ↔ Board Strategy Committee / Board Audit
  Committee.** Framework changes ratified by Board Strategy
  Committee; compliance-and-audit findings and remediation
  reported to Board Audit Committee. Both committees
  receive the AIGC quarterly dashboard.

**Why five bodies and not one.** Halcyon's existing bodies
have earned trust from different constituencies (business
units, legal, marketing, product, R&D). Centralising into a
new single body creates the problem of persuading four
constituencies simultaneously that the new body preserves
what each of them values, which never quite happens. The
composed model accepts that the coordination cost is
non-trivial and pays it with an explicit interface model.

**Why the AIGC is CIO-chaired.** Not CTO, not Chief AI
Officer (Halcyon does not have one, and the reference
framework does not create one). The CIO chairs because the
CIO is the officer with cross-domain authority who is
neither a business-unit champion nor a technical-faction
champion. A Chief AI Officer at Halcyon would be a
politically-visible role whose incumbent would become a
personality dependency; the reference framework declines
that risk.

### 2.4 The decision-class model

The reference framework enumerates decision classes and
maps each to an authority level in the RACI (see
`governance/decision-authority-raci.md` for the full
matrix). The decision classes are:

**Class 1 — Framework and policy decisions.** Changes to the
enterprise AI governance framework itself, the scope
definition, the RACI, the governance principles, the portfolio
model, the Board-oversight model, the compliance-and-audit
posture. Authority: Board Strategy Committee ratifies; AIGC
recommends; Board Audit Committee informed.

**Class 2 — Regulatory-classification decisions.** Whether a
Halcyon AI system is a high-risk AI system under EU AI Act,
subject to a specific regulator's AI supervision, or covered
by a specific standard's certification obligations. Authority:
AIGC decides; General Counsel is R (responsible) in RACI
terms; the operational body relevant to the system informed.

**Class 3 — AI system deployment decisions above threshold.**
Deployment of a new AI system into production above a
defined threshold (revenue exposure, customer count, safety
classification, or spend). Authority: ARB with RAIB
consultation; AIGC informed; CIO and business-unit
executive R.

**Class 4 — Investment-portfolio allocation decisions.**
Allocation of AI-adjacent budget within the AI portfolio
across categories, above the AIGC's delegated authority
threshold. Authority: CFO ratifies; AIGC recommends; Board
Audit Committee reviews annually.

**Class 5 — Responsible-AI posture decisions.** Halcyon's
position on a specific responsible-AI question (bias-testing
threshold, transparency posture, third-party fine-tuning
posture, deployment of a model class in a specific context).
Authority: RAIB decides; AIGC informed; General Counsel
consulted for regulatory-adjacent items.

**Class 6 — Innovation-portfolio decisions.** Innovation-
portfolio allocation, stage-gate transitions, external-
partnership approvals within the innovation programme.
Authority: IPB decides; AIGC informed on portfolio-level
changes.

**Class 7 — External-communication decisions.** External
communications about AI on programme surfaces. Authority:
EVRB decides per its tiered review; AIGC informed on
strategic-level positions.

**Class 8 — Incident response decisions.** Response to an
AI-system incident above a severity threshold. Authority:
Chief Information Security Officer coordinates operational
response; RAIB owns responsible-AI-substance review; AIGC
convenes post-incident review; Board Audit Committee
notified for High or Critical severity.

**Class 9 — Audit-finding-remediation decisions.**
Acceptance of an audit finding, agreement of remediation
plan, closure of finding. Authority: Head of Internal Audit
tracks; AIGC ratifies remediation plans; Board Audit
Committee reviews unresolved findings above a threshold.

**Class 10 — Individual-system operating decisions.**
Day-to-day operating decisions (feature-flag change, model
version rollout within a version series, retraining schedule,
capacity change). Authority: platform-team leadership within
guardrails set by ARB and RAIB. Not enterprise-level.

**Why ten classes and not three.** Three classes force
either loss of resolution ("everything above $10M is a Board
matter") or coarse mis-classification ("a policy change and
a feature-flag change are both operating decisions"). The
reference framework accepts that ten is the smallest
enumeration that preserves the natural authority boundaries
Halcyon's operating officers already recognise.

**Why not fifty.** Fifty classes force decision-authority
lookups on every submission and hide the pattern the RACI is
supposed to expose. The reference framework accepts that
some decisions live at the boundary between classes and
routes them to the AIGC for classification when needed.

### 2.5 Investment prioritisation and portfolio management

The reference framework runs AI-adjacent spend as a single
portfolio with argued categorisation. Three commitments.

**Commitment 1 — The portfolio has categories, not silos.**
AI-adjacent spend is categorised into:

- **Core-platform category.** The shared platform (Project
  402) and its enabling capabilities. Funded at whatever
  level the platform-tenancy model requires to sustain the
  business units it serves. Prioritisation logic: the
  platform is a utility; unit economics govern.
- **Business-line-AI category.** AI systems owned by
  specific business units for specific business outcomes.
  Prioritised by expected outcome value against a defensible
  metric per system, with the business unit as the funding
  authority.
- **Responsible-AI-operations category.** The operating
  costs of the responsible-AI framework: bias testing,
  transparency artifacts, safety-critical evaluation
  harnesses, audit-evidence generation. Funded as a
  compliance obligation; prioritisation is against
  regulatory exposure and audit-finding backlog.
- **Innovation-portfolio category.** Exploratory AI spend
  as governed by the IPB (Project 404). Prioritisation is
  IPB's; the AIGC sees the portfolio composition and
  aggregate exposure.
- **External-programme category.** External-voice programme
  operating cost (Project 405), standards participation,
  community-and-open-source contribution. Prioritisation
  is EVRB's within the AIGC-approved envelope.

**Commitment 2 — Prioritisation criteria are argued and
published.** Within each category, prioritisation runs against
a small set of published criteria. Not net-present-value alone
— strategic option value, regulatory-exposure reduction,
platform-multiplier effect, and defensibility of alternatives
are named. The reference framework accepts that this is a
richer decision than a single NPV rank and requires the CFO
to consent to the criteria, not just the aggregate spend.

**Commitment 3 — Reviews run on a defined cadence, not on
project-team demand.** The AI portfolio is reviewed:

- **Quarterly by the AIGC**, at the portfolio-composition
  level. Category rebalancing, category-level ceilings, and
  inter-category trade decisions.
- **Semi-annually by the CFO's capital-planning
  process**, integrated into the enterprise capital plan.
- **Annually by the Board Audit Committee**, as a
  portfolio-composition-and-outcome report.

Project-team-demand review requests are not blocked, but the
default cadence is quarterly. A project team that needs an
off-cadence portfolio decision escalates via the AIGC chair.

**Why categorised and criteria-argued.** A portfolio with no
categories is a spreadsheet ranked by whatever metric was
loudest that quarter. Categories force the CFO to defend not
"which project" but "which category and how much" — the more
useful question at the Board Audit Committee level. Criteria
that name strategic-option value and regulatory-exposure
reduction alongside NPV prevent the framework from becoming
a pure ROI machine that de-funds the compliance and
platform categories systematically.

**Why not project-by-project.** Project-by-project
prioritisation collapses into loudest-voice-wins because
the internal politics of any given quarter dominate. The
category model bounds the politics: even a loud business
unit competes only within its category ceiling.

### 2.6 Board-level oversight model

The reference framework instruments Board-level AI oversight
around three artifacts.

**Artifact 1 — The AIGC dashboard.** A defined dashboard
reported quarterly to the Board Strategy Committee and Board
Audit Committee. The dashboard is drawn from records outside
the AI programmes themselves — Internal Audit records for
audit findings, CFO records for portfolio spend, CISO
records for incidents, HR records for staffing coverage of
named roles. The dashboard is not a slide deck management
prepares; it is a report the AIGC generates from records
management does not curate.

The dashboard has six panels:

1. **Portfolio composition.** Actual spend by category
   against approved envelope, with drift arrows.
2. **Decision-authority activity.** Decisions taken by
   class in the period, with escalations, deferrals, and
   dissent records.
3. **Regulatory posture.** In-scope AI systems by
   classification, changes in classification in the period,
   and regulatory-consultation activity.
4. **Incident record.** AI-system incidents in the period
   by severity, mean time to detection, mean time to
   response, and Board-notification triggers.
5. **Audit posture.** Open audit findings, remediation
   status, aged findings against the framework SLA,
   findings closed in the period.
6. **Framework health.** Named-role vacancy rate, framework
   review status, policy-refresh status.

The dashboard is delivered as data plus a one-page
management commentary. The Board reads the data first.

**Artifact 2 — Deep-dive triggers.** The framework enumerates
thresholds that trigger a Board-level deep dive on a specific
topic. Triggers are:

- A Critical-severity AI incident.
- An audit finding rated High or Critical.
- A regulatory notice, consultation, or investigation
  touching a Halcyon AI system.
- Portfolio-category drift beyond a stated tolerance.
- Two consecutive quarters of missed dashboard reporting
  (a framework-health failure in its own right).
- Framework amendment proposals with material scope,
  authority, or oversight impact.

Deep dives are not the Board Chair's discretion alone; the
triggers are published. The Chair may convene a deep dive
outside the triggers, but the triggers exist to force
convocation the Chair might otherwise defer.

**Artifact 3 — Board-committee AI-oversight charters.** The
framework specifies what AI oversight the Board Strategy
Committee, Board Audit Committee, and (where present) Board
Risk Committee each own. Overlaps are resolved: framework
ratification sits with Strategy; compliance-and-audit
posture and audit-finding oversight sit with Audit;
enterprise-risk-appetite for AI sits with Risk. A director
sitting on more than one committee is aware which hat is
on for AI oversight questions.

**Why instrumented and not narrative.** A narrative Board
briefing is one management witness's view. In a fiduciary-
duty inquiry ex post, the question a director will be asked
is "on what basis were you satisfied," and the answer must
be more than "the CTO briefed us." A dashboard drawn from
records outside management's curation is defensible; a
briefing prepared by management is what the director will
be examined on.

**Why triggered deep dives.** Discretion-only deep dives
never happen for the difficult topics; they happen for the
topics the Chair already understands. Triggered deep dives
force convocation on topics the Board would otherwise
defer, which is exactly the fiduciary-duty question.

### 2.7 Compliance-and-audit framework

The reference framework treats compliance and audit as
by-product of workflow, not as a parallel programme. Four
commitments.

**Commitment 1 — Regulatory obligations are mapped to workflow
steps.** The framework maintains a regulatory-obligation
register: for each applicable regulation (EU AI Act,
NIST AI RMF alignment, ISO/IEC 42001 certification scope,
sector-specific AI supervision), the obligations are
enumerated, and each obligation is mapped to one or more
workflow steps in the operational bodies that produce the
evidence for the obligation. New obligations are mapped
before the effective date; obligations without a mapped
workflow step are treated as gaps and remediated.

**Commitment 2 — Evidence is generated by the workflow, not
by audit demand.** Every workflow that produces a governance
artifact produces the artifact in an audit-retrievable form
by default. The archive discipline from Project 405 for the
External Voice Review Board is generalised: every operational
body's decisions, artifacts, sign-offs, dissent records, and
conditions are archived with retention, access control, and
chain of custody. Internal Audit's programme is designed
against these archives.

**Commitment 3 — Internal Audit runs a defined AI-audit
programme.** The Head of Internal Audit maintains a rolling
AI-audit programme, three-year cycle, covering: framework-
adherence at each operational body, regulatory-obligation
mapping and evidence-completeness, portfolio-model integrity,
Board-oversight-dashboard data provenance, and incident-
response effectiveness. Findings enter the framework's
remediation workflow (Class 9) and are reported on the AIGC
dashboard.

**Commitment 4 — External-audit readiness is a posture, not
a project.** External auditors — statutory financial
auditors reviewing AI-related disclosures, ISO/IEC 42001
certification bodies, EU AI Act notified bodies for high-
risk AI systems, sector-specific supervisory audits — are
served from the same archives Internal Audit uses. The
framework does not run a distinct "audit preparation"
programme; where a specific external audit requires
additional artifacts, those artifacts are generated once
and archived.

**Why by-product and not project.** Compliance-as-project
produces two failure modes at once: the ordinary workflow
is not disciplined enough to survive audit without
retroactive assembly, and the audit-preparation cycle
consumes engineering capacity that could have been used to
prevent the finding in the first place. By-product
compliance accepts the cost of workflow discipline in the
ordinary course and eliminates the audit-preparation
cycle.

### 2.8 Governance — the AI Governance Committee

The AI Governance Committee is chartered in
`framework/enterprise-ai-governance-framework.md` §3 (the
AIGC section). Key properties:

- **Composition.** CIO (chair); CTO or delegate; CFO delegate
  at the level authorised for AI portfolio commitments;
  General Counsel or delegate; CISO or delegate; Chief Data
  Officer or delegate; Chief Privacy Officer or delegate;
  ARB Chair; RAIB Chair; IPB Chair; EVRB Chair; Head of
  Internal Audit (non-voting); Board Strategy Committee
  liaison (non-voting, attends by invitation for framework
  amendments and quarterly review).
- **Authority.** Binding on: framework amendments (with
  Board Strategy Committee ratification), scope-definition
  ambiguity rulings, decision-class assignment for novel
  decision types, RACI amendments, portfolio-category
  ceilings within the CFO-approved envelope, inter-body
  interface changes, regulatory-classification decisions
  (Class 2), and remediation-plan ratification (Class 9).
  Advisory on: individual system architecture decisions
  (ARB scope), individual responsible-AI-posture decisions
  (RAIB scope), individual innovation-portfolio-allocation
  decisions (IPB scope), and individual external-
  communication decisions (EVRB scope).
- **Cadence.** Monthly standing meeting for cross-body
  coordination and framework operations. Quarterly review
  with the Board Strategy Committee and Board Audit
  Committee (via liaison). Annual framework review with
  formal re-approval.
- **Dissent recording.** Cross-body disagreement escalated
  to the AIGC is recorded with the bodies' positions;
  where the AIGC decides against a body, the decision
  documents the argument.

**Why AIGC and not "AI Steering Committee".** Steering
committees advise. The AIGC is authoritative on the classes
listed. Halcyon's four existing operational bodies retain
their authorities; the AIGC exists to make sure the four
bodies compose, not to override them.

### 2.9 Roadmap — twenty-four months, sequenced by reversibility

**Phase 0 (Months 0–3) — Scope, principles, topology.** Scope
definition drafted, reviewed with each operational body,
ratified by the Board Strategy Committee. Seven governance
principles ratified. AIGC chartered and seated. Interfaces
between operational bodies drafted and reviewed by each.
Existing decisions inventoried against the scope definition;
gaps in scope coverage flagged. **Highly reversible.** No
authority changes yet; existing bodies continue under
existing charters.

**Phase 1 (Months 3–9) — RACI live; portfolio model
operating.** Decision-class model and RACI published and
mandatory for new decisions. Portfolio model live; categories
defined; category ceilings agreed with the CFO; first
quarterly portfolio review under the model. Regulatory-
obligation register live; mapping to workflow steps in
progress; gaps flagged. AIGC dashboard drafted; first two
quarterly dashboards produced (initially with data gaps,
which are themselves reported). **Medium reversibility.**

**Phase 2 (Months 9–18) — Backfill and steady state.** All
in-scope existing decisions retro-mapped to the RACI and
archived. Portfolio categories fully populated with baseline
data. AIGC dashboard on full data. Internal Audit programme
delivering first audit results; findings entering
remediation workflow. Second RAIB / IPB / EVRB / ARB
interface review complete. **Low reversibility per body
interface change** — bodies interpret their scopes in
different directions, and re-negotiating interfaces is
expensive — but the reference framework front-loads honest
interface discussions.

**Phase 3 (Months 18–24) — External review and framework
refresh.** First external framework review, informed by
comparators (peer-organisation governance disclosures,
ISO/IEC 42001 certification body observations, EU AI Act
compliance reviews). Framework reviewed against results;
Board Strategy Committee ratifies any framework update.
First ISO/IEC 42001 certification pass considered if the
framework maturity supports it (decision made in Phase 2
against the certification-readiness assessment; certification
is a defensible target, not automatically the right target).

**Beyond month 24.** The framework runs on an annual formal
review, quarterly AIGC operations, semi-annual portfolio
review with CFO, and continuous dashboard reporting. There
is no "phase 4"; the framework is now steady state, and
steady state is the point.

**Why sequenced by reversibility.** Same reasoning as
Projects 402–405. Chartering the AIGC is cheap and
reversible; changing a decision authority that the CFO or
General Counsel has come to rely on is not. The reference
sequences the cheap decisions early so the expensive ones
can be defended when they arrive.

### 2.10 What is deferred, and why

Some items are deliberately deferred beyond the reference:

- **Specific ISO/IEC 42001 certification decision.** Whether
  Halcyon pursues formal ISO/IEC 42001 certification, and
  at which entity level, is a Phase 2 decision made against
  a readiness assessment. Certification is a defensible
  target for some Halcyon business units and not for
  others; the framework produces certification-ready
  evidence regardless. Tracked as **FOLLOWUP-42001-01**.
- **AI risk-appetite statement at Board level.** The Board
  Risk Committee (where present) or Board Audit Committee
  (where the Risk Committee is not separate) is responsible
  for the enterprise AI risk-appetite statement. The
  framework provides the inputs and hosts the operating
  workflow that keeps the risk profile inside appetite;
  the appetite statement itself is a Board deliverable
  scheduled for the annual framework review. Tracked as
  **FOLLOWUP-APPETITE-01**.
- **Regional adaptations for EU AI Act designations, Japan,
  South Korea, and mainland China.** Halcyon operates in
  jurisdictions where regulatory-classification obligations,
  sector-supervisory practices, and audit expectations
  differ materially. The reference framework is the group
  frame; regional adaptations are designed in Phase 1 with
  regional leadership and General Counsel. Tracked as
  **FOLLOWUP-REGION-01**.
- **Third-party AI system procurement governance.** Halcyon
  procures third-party AI services (foundation models via
  API, embedded AI in industrial-partner platforms). The
  framework's scope tests apply to procured systems, but
  the operational procurement workflow, third-party risk
  management integration, and supplier due-diligence AI
  addendum are deferred to Phase 1 in coordination with
  Procurement and third-party risk management. Tracked as
  **FOLLOWUP-PROCURE-01**.

Deferrals are scoped, time-bound, and tracked. They are not
open research questions blocking the reference framework.

## Implementation

The implementation approach is defined by the roadmap in
Section 2.9, the decision-class model in Section 2.4, and
the compliance-and-audit approach in Section 2.7. This
section names the invariants an implementation team must
hold:

- **Scope-first.** No framework decision is defensible in
  the absence of the scope definition. If scope is not
  written and ratified in Phase 0, every downstream decision
  becomes a jurisdictional dispute between bodies.
- **Bodies compose; the AIGC does not override them.** The
  AIGC's role is coordination, not override. An AIGC that
  starts making individual-system architecture decisions,
  responsible-AI-posture decisions, portfolio-allocation
  decisions, or external-communication decisions has
  destroyed the composition and merged the bodies into
  itself. That failure mode is why the AIGC's authority is
  scoped explicitly.
- **RACI is the definition of authorised.** A decision
  taken by a role outside the RACI-defined authority is a
  governance failure, not a workflow shortcut. Fix the
  authority ambiguity before scaling the workflow.
- **Portfolio categories are defended, not renamed
  quarterly.** Portfolio-category names in the reference
  framework are stable across the twenty-four-month roadmap.
  Renaming categories to preserve a specific project team's
  budget is a governance failure.
- **Board oversight runs on data, not narrative.** If the
  dashboard cannot be produced without management
  curation, the dashboard is not doing its job. Fix the
  archive before scaling the reporting.
- **Compliance is by-product.** Any workflow whose
  compliance artifacts are assembled retroactively for
  audit is either wrongly designed or under-executed. Fix
  the workflow before the next audit cycle.
- **Named-role successors are non-optional.** Every named
  role in the framework has a named successor on file. A
  role transition without a successor is a governance
  failure, not an HR issue.
- **Framework review is not optional even in good
  quarters.** The framework review runs on schedule
  regardless of whether the current quarter has been
  quiet. A quiet quarter is exactly the quarter in which
  the framework should be reviewed, because the review
  will produce useful attention rather than
  reflex-defence.

Sizing, cadence detail, and per-body operating rhythm are
captured in `framework/enterprise-ai-governance-framework.md`;
that document is the operational companion to this SOLUTION.

## 3. Validation steps

A senior architect validates the framework against the
following. If any check fails, the design is not yet ready
for the Board Strategy Committee.

**Structural checks:**

1. Pick a random Halcyon system that Engineering thinks is
   AI. Walk it through the scope tests. Is it in scope or
   out, and by which test? Can the walkthrough be repeated
   by an auditor from the same artifacts, in under fifteen
   minutes? If not, the scope tests are informal.
2. Pick a random decision taken in the last ninety days that
   was in-scope. Can you produce the decision class, the
   authority under the RACI, the decision record, the
   dissent record if any, and the follow-on artifacts, from
   the archive? If not, the RACI is aspirational.
3. Show the last three AIGC dashboard reports. For each,
   trace one data point per panel back to the source
   record outside AI-programme management. If any trace
   requires a management commentary, the dashboard is
   narrative, not instrumented.

**Portfolio dry-runs:**

4. A business unit requests reallocation of budget between
   categories mid-year to fund an unplanned AI system.
   Walk through: category-ceiling check, prioritisation
   criteria against the specific request, AIGC and CFO
   review, portfolio impact. At which points is the request
   blocked, and by what?
5. The Chief AI Scientist proposes an innovation-portfolio
   allocation that, on stage-gate exit, would produce a
   production system requiring RAIB responsible-AI
   classification. Walk through IPB stage-gate, RAIB
   consultation, ARB architecture engagement, and AIGC
   awareness. Where does each body enter? Where does each
   body's authority stop?
6. The CFO requests a portfolio-composition review outside
   the standard quarterly cadence. Walk through the AIGC's
   response: convocation, data preparation, dashboard
   generation. What is the target latency? Which
   information does the CFO see that the standard quarterly
   dashboard does not?

**Regulatory and audit dry-runs:**

7. An EU AI Act notified body notifies Halcyon of a
   scheduled compliance audit for a specified high-risk
   AI system. Walk through: system identification, evidence
   compilation, audit-window scheduling, finding-response
   protocol. What is the target time to serve the audit
   from the existing archive?
8. Internal Audit issues a High-severity finding on
   framework adherence at one operational body. Walk
   through the finding-triage, AIGC response, remediation
   plan, and Board Audit Committee reporting. Where is the
   finding archived? What triggers the Board Audit
   Committee's deep dive?
9. The named AIGC chair (CIO) leaves Halcyon mid-cycle.
   What breaks? (Correct answer: not the framework; the
   AIGC's authority is a chair role, not a personal role;
   the named-successor clause governs the transition; the
   incoming CIO inherits the chair.)

**Incident dry-run:**

10. A production AI system produces an outcome that a
    customer characterises publicly as "the AI made a
    decision it should not have made." Walk through:
    incident classification, CISO operational response,
    RAIB substantive review, EVRB external-communications
    review, AIGC post-incident review, Board Audit
    Committee notification. What is the target latency for
    each step? Which decisions can be taken without AIGC
    convocation, and which cannot?

If steps 1–10 can be walked through without hand-waving, the
framework is review-ready. If any require "we would need to
build that," the framework is not yet complete.

## 4. Rubric — quick reference

The full rubric lives at `rubric/evaluation-rubric.md`. The
six weighted dimensions are:

1. **Scope definition defensibility** (weight: 20%). Are the
   scope tests functional, published, and consistent with
   the regulatory and reputation tests they claim to
   satisfy?
2. **Decision-authority enforceability (RACI)** (weight:
   20%). Is decision authority enumerated by class and
   role, with escalation paths defined and archival
   discipline?
3. **Body-topology composition** (weight: 15%). Do the four
   operational bodies retain scoped authority, with defined
   interfaces and no gaps between?
4. **Investment-portfolio model** (weight: 15%). Is the AI
   portfolio categorised with argued criteria, and does
   the CFO consent to the criteria rather than only to the
   aggregate?
5. **Board-oversight instrumentation** (weight: 15%). Is
   Board reporting a dashboard from records outside
   management curation, with published deep-dive triggers?
6. **Compliance-and-audit by-product** (weight: 15%). Is
   audit evidence a by-product of the ordinary workflow,
   not a project-mode retrofit?

A submission scoring below 60 on Dimension 1 (scope) or
Dimension 2 (RACI) is non-passing regardless of other
scores. A senior architect who cannot show either "what is
in scope" or "who decides" has not demonstrated the level.

## 5. Common mistakes

**1. A definition of "AI" instead of scope tests.** A
definition invites arguments about whether a specific
system is "really AI." Functional tests invite arguments
about whether a specific test is triggered, which is the
more useful argument for governance.

**2. A single centralised AI decision body.** Newly
chartered "AI Council" bodies that override the four
existing operational bodies produce a two-quarter
constituency-management project and a permanent
under-utilisation of the specialised expertise the
existing bodies had earned. The reference framework
composes.

**3. RACI expressed by seniority instead of role and
class.** "Executives approve big AI decisions" is not a
RACI. A RACI names the role, the class, and the
authority; escalations are defined and rare.

**4. Portfolio model that reduces to NPV rank.** Reducing
AI-adjacent spend to a single NPV rank de-funds the
compliance and platform categories systematically and
concentrates the portfolio in whichever business unit runs
the fastest ROI modelling. The reference framework accepts
that portfolio prioritisation is a richer decision than
that.

**5. Board briefing as narrative slide deck.** A Board
briefing whose entire content is management's presentation
is the fiduciary-duty briefing that fails in a Caremark-line
inquiry. The reference framework provides Board members
with data from records outside management curation.

**6. Compliance as project.** Building an "AI compliance
project" that runs in parallel to the ordinary workflow
produces the two-way failure mode: the ordinary workflow
is not disciplined enough to be auditable, and the
compliance project consumes capacity that would have
prevented the finding in the first place.

**7. Named-person authorities.** "The AI Lab Director
approves AI systems" is a personality dependency; the
framework's authority disappears when the incumbent
leaves. The reference framework names roles and
successors.

**8. Framework review only on trigger.** Frameworks that
are only reviewed when something goes wrong drift in the
quiet quarters and then produce panic revisions in the
loud quarter. The reference framework reviews on schedule
even in quiet quarters, and the review artifact is a
governance record in its own right.

**9. Overlapping-body decision routes.** Two bodies with
overlapping scopes produce either double-approval delay or
uncoordinated single-body-approves-half-the-decision
gaps. The reference framework enumerates body scopes at
interface level and escalates ambiguity to the AIGC.

**10. Missing regulatory-obligation mapping.** A framework
that lists "we comply with the EU AI Act" without mapping
specific obligations to specific workflow steps is
compliance-as-slogan; the audit finding at the first
external audit will be exactly that the mapping does not
exist.

## 6. References

Standards, frameworks, and canonical sources cited or relied
upon by this solution:

- **ISO/IEC 42001:2023** — Artificial intelligence
  management system. Cited because it is the primary
  standards vehicle for AI-management-system certification
  the framework's evidence generation is designed against.
  <https://www.iso.org/standard/81230.html>
- **ISO/IEC 23894:2023** — Artificial Intelligence —
  Guidance on risk management. Cited as the risk-management
  reference the framework's risk-appetite integration is
  designed against.
  <https://www.iso.org/standard/77304.html>
- **ISO/IEC 42005:2025** — AI system impact assessment.
  Cited as an emerging standard the framework's impact-
  assessment workflow is designed against.
  <https://www.iso.org/standard/44545.html>
- **ISO/IEC 38500:2024** — Governance of information
  technology. Cited as the general IT-governance reference
  the framework composes with.
  <https://www.iso.org/standard/81684.html>
- **ISO 31000:2018** — Risk management — Guidelines.
  Cited as the risk-management reference the framework's
  risk integration composes with.
  <https://www.iso.org/standard/65694.html>
- **ISO 37301:2021** — Compliance management systems.
  Cited as the compliance-management reference for the
  compliance-and-audit posture.
  <https://www.iso.org/standard/75080.html>
- **EU Artificial Intelligence Act** — Regulation (EU)
  2024/1689. Cited as a primary regulatory obligation the
  framework's regulatory-classification decisions (Class 2)
  and evidence generation are designed against.
  <https://eur-lex.europa.eu/eli/reg/2024/1689/oj>
- **NIST AI Risk Management Framework (AI 100-1)** — cited
  as a primary risk-management reference and the alignment
  reference for US-audience regulatory posture.
  <https://www.nist.gov/itl/ai-risk-management-framework>
- **NIST AI RMF Generative AI Profile (AI 600-1)** — cited
  as the generative-AI overlay the framework's decision-
  class model and evidence generation reference.
  <https://www.nist.gov/itl/ai-risk-management-framework>
- **OECD AI Principles** — cited as the international
  policy frame under which Halcyon's public governance
  posture is consistent.
  <https://oecd.ai/en/ai-principles>
- **Council of Europe Framework Convention on Artificial
  Intelligence (2024)** — cited as an emerging international
  treaty frame the framework's regulatory-obligation
  register anticipates.
  <https://www.coe.int/en/web/artificial-intelligence>
- **COBIT 2019** — governance-and-management framework for
  enterprise IT. Cited as a reference for governance-body
  decision-authority-model design.
  <https://www.isaca.org/resources/cobit>
- **COSO Enterprise Risk Management — Integrating with
  Strategy and Performance (2017)** — cited as the
  enterprise-risk-management reference the AI framework's
  Board-oversight instrumentation composes with.
  <https://www.coso.org/guidance-erm>
- **Caremark and its progeny (Delaware Chancery)** — cited
  as the fiduciary-duty precedent framing the Board-
  oversight design. Directors' oversight duty extends to
  AI systems by the same reasoning as compliance and
  cybersecurity oversight.
  Public Delaware Chancery Court opinions.
- **US Sarbanes-Oxley Act §302 / §404** — cited as the
  internal-controls-and-attestation frame the AI portfolio
  and compliance-and-audit posture composes with, where
  Halcyon files US securities reports.
  <https://www.sec.gov/rules/final/33-8238.htm>
- **IIA Three Lines Model (Institute of Internal
  Auditors, 2020 revision)** — cited as the three-lines
  reference the framework's internal-audit programme is
  designed against.
  <https://www.theiia.org/en/content/guidance/mandatory/standards/three-lines-model/>
- **PCAOB AS 2201 — An Audit of Internal Control Over
  Financial Reporting** — cited as the external-audit
  reference where AI-related internal controls interact
  with financial reporting.
  <https://pcaobus.org/oversight/standards/auditing-standards/details/AS2201>
- **ISO/IEC 27001:2022** — Information security management
  systems. Cited as the information-security management
  reference the AI security posture composes with.
  <https://www.iso.org/standard/27001>
- **ISO/IEC 5259 series (in development)** — data quality
  for analytics and machine learning. Cited as the data-
  quality reference the framework's data-governance
  interface anticipates.
  <https://www.iso.org/standard/81088.html>
- **US Delaware General Corporation Law** — cited as the
  general corporate-governance frame where Halcyon's
  Delaware-incorporated entities operate.
  <https://delcode.delaware.gov/title8/>

Related solutions in this repository:

- `projects/project-401-transformation-strategy/SOLUTION.md`
  — the transformation-strategy view whose governance the
  AIGC frames.
- `projects/project-402-global-ai-platform-architecture/SOLUTION.md`
  — the platform whose Architecture Review Board this
  framework composes with.
- `projects/project-403-responsible-ai-framework/SOLUTION.md`
  — the Responsible AI framework whose Responsible AI
  Board this framework composes with.
- `projects/project-404-innovation-program-design/SOLUTION.md`
  — the innovation programme whose Innovation Portfolio
  Board this framework composes with.
- `projects/project-405-industry-thought-leadership/SOLUTION.md`
  — the industry thought-leadership programme whose
  External Voice Review Board this framework composes with.

## Time budget

- **Review-time read**: 45 minutes to read this SOLUTION
  plus `framework/enterprise-ai-governance-framework.md`.
  This is the minimum to participate in a framework review.
- **Full deliverable read**: 3–4 hours to read all
  artifacts (SOLUTION, framework, ARB charter, RACI,
  rubric) with the referenced standards open in a second
  tab.
- **Learner-side build**: a strong learner produces a
  defensible first draft in 25–35 hours of focused work,
  plus a further 10–15 hours iterating after CFO, General
  Counsel, CISO, and Internal Audit review.

## Status

**Version**: 1.0
**Status**: Reference solution
**Owner**: Senior Architect curriculum track
