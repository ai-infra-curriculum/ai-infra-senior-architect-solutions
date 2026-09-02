# SOLUTION — Responsible AI Framework

> Read this *after* you have drafted your own Responsible AI framework.
> This is the reasoning the reference design is defending, not a scoring
> key. A different framework that defends the same properties is a valid
> answer.

## 1. Solution overview

A senior architect answers three questions in a Responsible AI
programme design review:

1. **How does the organization know what AI systems it operates,
   and under what classification?** — the inventory-and-taxonomy
   question. Almost every downstream failure of a RAI programme
   traces back to a system that was not on the inventory or was
   mis-classified at intake.
2. **What is enforced, and by what control?** — the enforceability
   question. Principles are cheap; the platform behaviour that
   makes a principle real is the artifact. Every claim in a
   Responsible AI framework has to be resolvable to a named control.
3. **What is visible to whom, and on what cadence?** — the
   transparency-and-oversight question. Board Risk, Audit, and
   the public each need a defined view. If the three views are not
   produced from the same platform records, they will disagree,
   and the programme's credibility does not survive the first
   disagreement.

The reference target state is a **registry-anchored, policy-as-code
Responsible AI framework** whose Ethics Board is chartered as an
advisory-with-teeth body, whose bias and explainability
requirements are enforced at deployment-time by the model registry,
and whose Board and public reporting are produced from the same
underlying records.

The **key trade-off accepted** is friction: every AI system in
scope has to be registered, classified, and evidenced before it
runs. A programme that lets first-line teams "self-attest" and
back-fill will be cheaper on day one and non-defensible on day
one hundred. The reference chooses defensibility.

## 2. Worked answer (the reference framework)

### 2.1 Principles (five, not twelve)

The reference framework commits to five principles. Each principle
maps to at least one enforced control; principles without controls
are removed rather than published.

1. **Lawfulness and rights.** Aurora operates AI systems in
   compliance with the EU AI Act, sectoral insurance regulation
   (EIOPA, NAIC, national supervisors), data-protection law
   (GDPR, LGPD, DPDP, US state privacy laws), and non-
   discrimination law (EU, US federal, US state, UK Equality Act,
   equivalents). *Enforced by*: registry classification, policy
   engine gating.
2. **Human oversight in scope.** For every high-risk AI system,
   a natural person is accountable in the loop or on the loop.
   The oversight design is documented and testable. *Enforced by*:
   registry evidence bundle; deployment blocked without
   oversight-design artifact.
3. **Fairness in evidence, not intent.** Every high-risk and
   material limited-risk system declares fairness metrics before
   deployment and generates them as a side-effect of evaluation.
   Drift on the declared metrics is monitored and responded to.
   *Enforced by*: registry evaluation gate; monitoring alerts.
4. **Explainability appropriate to use.** Every high-risk system
   ships with an explanation strategy suitable to the decision
   it affects. Decisions communicated to individuals include the
   basis the framework says are required. *Enforced by*:
   registry evidence bundle; explanation-strategy artifact
   required for promotion.
5. **Transparency by default, private by exception.** What
   Aurora operates is publicly listed in aggregate; what is
   confidential (specific model artifacts, security-sensitive
   detail) is documented as an exception. *Enforced by*:
   transparency-report generator reads from the registry;
   exceptions require named approval logged in the registry.

**Why five and not twelve.** Twelve-principle frameworks read well
and enforce nothing. Every principle above is engineered against.
Principles that were considered and dropped as unenforceable at
Aurora's scale — "beneficial", "aligned with human values",
"robust" — are dropped because they cannot be resolved to a
control the platform holds. They belong in the CEO letter, not in
the framework.

### 2.2 AI system inventory and taxonomy

Every AI system is registered before it can operate. The reference
registry entry carries:

- **System identity**: name, version, hash of the deployed
  artifact.
- **Owner**: business unit, accountable executive (role, not
  person), first-line owner (role, not person), MRM (model-risk-
  management) reviewer (role).
- **Purpose**: the decision the system affects, in one sentence a
  non-technical reviewer can read.
- **Data**: pointer to the training data lineage, with each
  dataset's data-classification (residency, sensitivity,
  provenance) recorded — the model registry does not hold the
  data itself.
- **Regulatory classification**: EU AI Act (prohibited /
  high-risk / limited-risk / minimal-risk); sectoral (insurance-
  regulated: yes/no; consumer-credit-regulated: yes/no); state-
  law scope (Colorado SB 21-169, NYC Local Law 144, Illinois HB
  3773, and equivalents applicable to the jurisdiction of the
  affected consumer).
- **NIST AI RMF profile**: which functions (GOVERN, MAP, MEASURE,
  MANAGE) the system has evidence against, and where the gaps
  are.
- **Fairness declaration**: metric(s) selected, protected
  attributes analyzed (where lawful), evaluation cadence,
  thresholds for action.
- **Explanation strategy**: audience(s), granularity, method,
  and the artifact the individual affected receives.
- **Human-oversight design**: reviewer role, escalation path,
  override authority, and audit hooks.
- **Post-market monitoring plan**: signals monitored, cadence,
  incident thresholds, and the individual accountable.
- **Approvals**: sign-off history (first-line owner, MRM, Ethics
  Board where required, external where required).

Systems that fail to register cannot be deployed. Systems that
change their purpose, data, or classification re-enter the
approval flow.

**Why registry-centric.** The registry is the only object in a
Responsible AI programme that outlives the model, the pipeline,
the training cluster, and the team. Anything that lives elsewhere
(a Confluence page, a JIRA project, a slide deck) rots. The
registry is the single artifact a regulator, an internal auditor,
and the Board Risk Committee can all point at.

### 2.3 EU AI Act operationalization

Classification is carried in the registry, not in a compliance
checklist. Aurora's operative categories:

- **Prohibited**. The platform refuses to accept these models.
  Attempted registration is logged and escalated to the Ethics
  Board and the Chief Compliance Officer. The Ethics Board
  charter requires a written finding on any refused registration.
- **High-risk (Annex III)**. Underwriting (life-and-health risk
  assessment), credit-adjacent underwriting decisions, employment
  and worker-management tools where applicable, and any other
  Annex III-scope use. The registry requires the complete
  evidence bundle before promotion to production:
  - Risk-management system record (Art. 9-equivalent).
  - Data-governance record covering training, validation, and
    testing data (Art. 10-equivalent), including provenance
    and representativeness discussion.
  - Technical documentation (Art. 11-equivalent) sufficient for
    a competent authority.
  - Automatic logging and traceability configuration (Art.
    12-equivalent).
  - Transparency and user information design (Art. 13-
    equivalent), naming the audiences.
  - Human oversight design (Art. 14-equivalent).
  - Accuracy, robustness, and cybersecurity evidence (Art.
    15-equivalent).
  - Conformity assessment record (Art. 43-equivalent);
    self-assessment where the module permits it, notified-body
    assessment where required.
  - Post-market monitoring plan (Art. 72-equivalent).
- **Limited-risk (transparency-obligated)**. Systems interacting
  with individuals, generating synthetic content, or otherwise
  triggering Article 50-equivalent obligations. The registry
  checks that the transparency configuration is present and that
  the disclosure text is version-controlled.
- **Minimal-risk**. Standard governance; still registered, still
  monitored, but the evidence-bundle requirements are lighter.

**Why in the registry, not in a compliance folder.** High-risk
obligations attach for the life of the system. The registry is
the only object that lives that long. If classification lives in
a folder, it will be inconsistent with reality within a quarter.

### 2.4 Bias and explainability standards

The reference framework treats fairness and explainability as
**declared-and-enforced** properties, not aspirational ones.

**Fairness declaration**. For every system where a fairness metric
is meaningful, the model owner declares:

- **Which fairness definition applies to this decision** (e.g.,
  demographic parity, equalized odds, calibration within groups,
  predictive parity, error-rate balance) and **why that one**.
  The framework does not mandate a single definition — it is
  mathematically impossible to satisfy several definitions
  simultaneously — but it requires the choice to be argued in
  writing.
- **The protected attributes analyzed**, and where analysis
  requires proxy or inference, how that inference is done and
  its known error properties. Analysis of protected attributes
  is bound by the applicable jurisdiction's rules — the
  framework acknowledges that legal permission to analyze varies
  by jurisdiction and by use case (e.g., insurance-specific
  rules on the use of certain attributes).
- **The threshold and monitoring cadence** at which drift
  triggers a defined action, and what that action is (pause,
  retrain, human-review-escalation, notify Ethics Board).

**Explainability strategy**. Explanation is designed for the
audience that receives it:

- **The individual affected** (applicant, policyholder, claimant)
  receives an explanation that meets the applicable legal
  requirement (GDPR Art. 22 meaningful information about the
  logic; insurance-sectoral disclosure requirements; state-law
  requirements in Colorado, NYC, Illinois where in scope). This
  is the primary explanation; it is designed first.
- **The reviewer / accountable person** (underwriter, claims
  adjuster) receives the explanation that supports the human-
  oversight function. Different granularity, different
  vocabulary, different persistence.
- **The regulator / auditor** receives system-level
  documentation, evaluation records, and (on request) the
  technical documentation described in the Art. 11-equivalent
  bundle.
- **The internal governance function** (MRM, Ethics Board)
  receives aggregate explainability quality metrics as part of
  the monitoring pack.

**Why declared-and-enforced.** The two most common failure modes
of Responsible AI programmes are (a) fairness metric picked after
the model was already deployed to justify the deployment, and
(b) explainability generated on demand for a regulator inquiry
rather than as a routine artifact. Declaring before deployment
and generating as a side-effect of evaluation removes both
failure modes.

**Enforcement point.** The registry gate for high-risk and
material limited-risk promotions checks that:

1. A fairness declaration exists.
2. The evaluation results for that declaration are present and
   in-date.
3. The explanation strategy is documented and the artifact
   generator is configured.
4. Monitoring for both is wired.

A promotion attempt failing any of the four is rejected. Overrides
require Ethics Board sign-off; overrides are counted and reported.

### 2.5 Ethics Board — chartered, not aspirational

The AI Ethics Board is defined in `governance/ethics-board-charter.md`
as an advisory-with-teeth body: it does not run the business, but
it has hard-stop authority on specific classes of decision and
formal escalation to the Board Risk Committee on defined triggers.

Key charter properties (full text in the charter):

- **Composition and independence**. Fixed-role composition
  including at least two external members, quorum defined,
  independence tested annually.
- **Authority**. Advisory on system-owner decisions; **binding**
  on: (a) registration or promotion of any high-risk system,
  (b) transparency-report exceptions, (c) override of a
  fairness/explainability gate, (d) any use of an emerging AI
  capability not yet in the framework's taxonomy.
- **Dissent recording**. Ethics Board decisions record dissent
  explicitly. Dissent above a threshold triggers automatic
  escalation to the Board Risk Committee. A unanimous board is
  reviewed, not celebrated.
- **Cadence**. Monthly standing meeting, with defined standing
  agenda and defined "always-covered" items (registry deltas,
  incident reviews, exception counts, upcoming regulatory
  events).
- **External review**. The Board's own operating effectiveness
  is reviewed annually by an external party. Findings are
  reported to the Board Risk Committee.

**Why chartered.** An ethics board without a charter is a monthly
meeting. An ethics board with a charter is a governance instrument.

**Why "binding on specific classes."** Ethics boards that are
"advisory to leadership" fail closed under commercial pressure.
Ethics boards that "run the business" fail open under
operational pressure. The chartered scope of binding authority
is narrow, defended, and enough.

### 2.6 Board-level oversight

The Board Risk Committee and Audit Committee each receive a
defined pack.

**Board Risk Committee (quarterly, with an interim ad-hoc trigger)**
receives:

- The inventory count by classification.
- Exception counts (Ethics Board overrides, monitoring alerts,
  policy waivers) with trend.
- High-risk system incident summary (any live incident, any
  closed incident since last).
- Regulatory landscape update (EU AI Act phase-in, state-law
  landings, sectoral supervisor communications).
- One "deep-dive" per meeting — a rotating in-depth review of a
  single high-risk system or a single control.

**Audit Committee (semi-annually)** receives:

- Internal audit findings on the RAI programme (control
  effectiveness).
- External audit findings (where applicable — SOX-adjacent,
  ISAE 3402-adjacent, sectoral supervisor-driven).
- Ethics Board's own operating-effectiveness review.
- Remediation status on any open findings.

Both packs are produced by a scheduled job that reads from the
registry and the monitoring stack. Manual assembly of the pack
is a smell: it means the underlying record was not enough, and
the record is what a regulator would ask to see.

**Escalation thresholds** are stated (not left to judgement):

- Any high-risk system with a fairness metric that has drifted
  past the declared threshold triggers Ethics Board review at
  the next meeting; a repeat drift triggers Board Risk Committee
  notification at the next quarterly cycle or via the interim
  ad-hoc trigger if severity warrants.
- Any promotion override by the Ethics Board is reported to the
  Board Risk Committee at the next cycle regardless of
  severity.
- Any regulator inquiry naming an Aurora AI system triggers
  same-day notification to the Board Chair and the Ethics Board
  Chair.

### 2.7 Public transparency reporting

The reference framework commits to an **annual public transparency
report** and a **quarterly summary update** on the corporate
website.

The annual report contains:

- Count of AI systems by classification (high-risk vs. limited-
  risk vs. minimal-risk), and by business line.
- Purpose statements for high-risk systems (the same one-sentence
  purpose from the registry, cleared for public consumption).
- Fairness posture at aggregate — how many systems have declared
  fairness metrics, how many have live monitoring, how many have
  had an incident in the reporting period.
- Human oversight posture at aggregate.
- Regulatory posture — where Aurora stands on the EU AI Act
  phase-in, on state-law compliance, and on sectoral supervisor
  expectations.
- Ethics Board activity summary — meetings held, decisions
  taken, dissent instances, external-review status.
- Incident summary at a level of detail cleared by Legal and by
  the Chief Communications Officer, and consistent with
  regulatory-notification obligations.

The quarterly update contains the count deltas, any material
event, and the pointer to the annual report.

**How it is produced.** A scheduled job reads the registry, the
monitoring stack, and the Ethics Board records; produces the
report drafts against a template; and routes them to Legal,
Communications, and the Chief Risk Officer for review before
publication. The template is versioned; changes to the template
require Ethics Board sign-off.

**What is not public.** Model-specific technical detail,
security-sensitive detail (adversarial hardening, red-team
findings), and detail that would materially aid gaming of the
system are documented as exceptions in the transparency policy
and are not published. Exceptions are counted and reported to
the Board.

**Why publishable-not-persuadable.** A transparency report that
requires a bespoke engineering effort per cycle is a marketing
artifact, not a transparency artifact. A report produced from
records is testable; a report drafted from slides is not.

### 2.8 Regulatory roadmap — surviving drift

The EU AI Act phases in through 2027; sectoral guidance evolves;
US state laws land unevenly. The reference roadmap survives all
three by treating each requirement as an item in the policy
engine, not as a bespoke project.

**Phase 0 (Months 0-3) — Inventory as observatory.** Registry
stood up as a read-only observatory over existing AI systems
across underwriting, claims, and group benefits. Every system
is inventoried, classified provisionally, and its evidence gaps
recorded. **Highly reversible.** Nothing new deploys through the
registry yet.

**Phase 1 (Months 3-9) — Charter and controls.** Ethics Board
chartered and operational. Policy engine authoritative for *new*
deployments only. Fairness-declaration and explanation-strategy
templates published. First-line teams trained. **Medium
reversibility.**

**Phase 2 (Months 9-18) — Backfill and gate.** Existing high-risk
systems back-fill the evidence bundle on a defined schedule;
systems that do not back-fill by the deadline are frozen from
material change until they do. Registry gate becomes authoritative
for all classes. **Low reversibility per system**, but the registry
allows per-system triage — the framework does not force a
big-bang date.

**Phase 3 (Months 18-24) — Reporting and external review.** First
public transparency report drafted, reviewed, published. First
external Ethics Board effectiveness review. First internal audit
of the RAI programme end-to-end. **Distinct workstream from
Phase 2 backfill**; can proceed in parallel once first backfilled
system is complete.

**Phase 4 (Months 24-36) — Optimization and maturity.** Second
public report; second external review; monitoring cadence and
threshold tuning based on empirical incident data; regulatory
changes incorporated as policy-engine updates rather than as
new projects.

**Why sequenced by reversibility.** Same reasoning as Project 402:
a wrong Phase 0 decision costs weeks; a wrong Phase 3 decision
costs public credibility. Registry-first, charter-second, gate-
third, report-fourth is the ordering that keeps the cheap
decisions cheap and the expensive decisions defended.

### 2.9 What is deferred, and why

A small number of items are deferred deliberately:

- **Notified-body vs. self-assessment path** for specific
  high-risk systems. The Act's Article 43-equivalent modules and
  their applicability to specific Aurora systems require Legal
  input at the point of promotion, not at the point of framework
  design. Tracked as **FOLLOWUP-EUAI-CA-01** on the RAI backlog.
- **US-state-law-specific evidence templates**. The framework
  commits to being state-law-aware; the specific evidence
  template per state law is deferred to Legal per state as the
  law is applied to Aurora's book. Tracked as
  **FOLLOWUP-US-STATE-EV-01**.
- **Insurance-sectoral supervisor deep-dives** — EIOPA opinions,
  NAIC Model Bulletin implementations by state, PRA thematic
  reviews. Cited as supervisory expectations; the specific
  bilateral commitments Aurora makes are a business decision the
  framework informs rather than makes. Tracked as
  **FOLLOWUP-SEC-SUPER-01**.

Deferrals are scoped, time-bound, and tracked. They are not open
research questions blocking the reference framework.

## Implementation

The implementation approach is defined by the roadmap in
Section 2.8, the enforcement points in Sections 2.3–2.4, and
the reporting model in Sections 2.6–2.7. Rather than repeat those,
this section names the invariants an implementation team must
hold:

- **Registry-first.** No system is in scope until it is in the
  registry. Every gate downstream — Ethics Board review,
  transparency report, Board dashboard — reads from the registry.
  If the registry is not authoritative in Phase 1, the fairness
  and explainability claims in Section 2.4 are not enforceable
  in Phase 2.
- **Enforcement is code.** Fairness declaration, explanation
  strategy, human-oversight design, and evidence bundles are
  enforced by the registry gate. Every control has a build
  owner and an automated conformance test defined in
  `framework/responsible-ai-framework.md`.
- **Ethics Board authority is scoped, not aspirational.** The
  charter defines what the Board is binding on and what it is
  advisory on. Implementation preserves that split — the
  binding items are wired into the registry gate; the advisory
  items are logged for later governance visibility.
- **Reporting reads from records.** Board packs and public
  transparency reports are generated by a scheduled job over
  registry and monitoring records. If a pack needs manual
  assembly, the underlying record is missing a field — fix the
  record, not the assembler.
- **Sponsor-neutral operating cadence.** Ethics Board cadence,
  registry gates, and reporting cycles run on schedule
  regardless of leadership transitions. The design does not
  depend on the current Chief Risk Officer being in seat.

Sizing, team topology, and per-artifact build ownership are
captured in `framework/responsible-ai-framework.md`; that
document is the operational companion to this SOLUTION.

## 3. Validation steps

A senior architect validates a Responsible AI framework against
the following. If any check fails, the framework is not yet
ready for review.

**Structural checks**:

1. Pick a random AI system in production. Can you point to the
   registry entry, name the classification, name the accountable
   owner (role, not person), and produce the last evaluation
   evidence in under fifteen minutes? If not, the inventory is
   an aspiration.
2. For a high-risk system, name the fairness metric declared,
   the last three evaluations against it, the monitoring signal
   since, and the threshold at which action is taken. Can any
   of these be resolved from a slide instead of from the
   registry? If yes, the enforcement is aspirational.
3. Show the last three Ethics Board decisions. For each, name
   the vote, the dissent recorded, the follow-up committed, and
   the artifact where the decision is stored. If any is
   irretrievable, the Ethics Board is a meeting, not a
   governance body.

**Regulatory dry-runs**:

4. A regulator writes to Aurora asking "how many high-risk AI
   systems do you operate, and in what jurisdictions?" What is
   the source-of-truth artifact for the answer? How long to
   produce it? Who signs it out?
5. A regulator writes asking for the technical documentation
   for the underwriting risk-assessment system. Which artifacts
   from the evidence bundle are produced? Which require
   engineering escalation?
6. A journalist publishes a story alleging Aurora's claims
   fraud-scoring system disadvantages a protected group. What
   is the first record consulted? What is the Board-facing
   response, and where does it come from?

**Operational dry-runs**:

7. A model owner in the group-benefits business wants to deploy
   a new system that recommends benefit uptake to employees.
   Walk through the intake, classification, evidence bundle,
   Ethics Board review, and promotion path. At which points
   is the deployment blocked, and by what?
8. A fairness monitor on a live high-risk system trips its
   declared threshold. Walk through the response path from
   alert to Ethics Board review to Board Risk Committee
   notification. Which of the steps are automated, which are
   human, and which are on a clock?
9. The Ethics Board Chair resigns. What breaks in the framework?
   (Correct answer: not the framework; possibly the composition;
   definitely the transition-period cadence.)

If steps 1–9 can be walked through without hand-waving, the
framework is review-ready. If any require "we would need to
build that," the framework is not yet complete.

## 4. Rubric — quick reference

The full rubric lives at `rubric/evaluation-rubric.md`. The six
weighted dimensions are:

1. **Inventory and taxonomy defensibility** (weight: 20%). Can
   the organization answer "what do we operate?" from a single
   named artifact?
2. **EU AI Act operationalization** (weight: 20%). Is
   classification in the registry with an enforced evidence
   bundle, or in a checklist?
3. **Bias and explainability enforceability** (weight: 15%).
   Are fairness and explainability declared before deployment,
   generated as a side-effect of evaluation, and monitored?
4. **Ethics Board charter defensibility** (weight: 15%). Is
   the Board's authority scoped and binding on specified
   classes, with dissent recorded and external review annual?
5. **Board oversight and public transparency** (weight: 15%).
   Are Board packs and public reports produced from platform
   records, not from slides?
6. **Regulatory roadmap sequenced by reversibility** (weight:
   10%). Is Phase 0 the read-only observatory, Phase 4 the
   optimization?

Remaining 5% is distributed across documentation quality,
consistency across artifacts, and named-person-independence.

A submission scoring below 60 on Dimension 1 (inventory) or
Dimension 3 (bias/explainability enforceability) is non-passing
regardless of other scores. A senior architect who cannot show
either "what we operate" or "how we know it's fair and
explainable" has not demonstrated the level.

## 5. Common mistakes

**1. Twelve principles, zero controls.** A framework that publishes
twelve virtues and enforces none is a marketing artifact. Every
principle in a senior submission is mapped to a control that
holds it.

**2. Inventory as a spreadsheet.** A spreadsheet is not an
inventory. Anything that can drift out of sync with the operating
platform will drift, and the drift will not be noticed until a
regulator asks.

**3. Fairness metric picked after deployment.** A metric picked
after the model is live is a metric picked to justify the model.
The framework requires declaration *before* promotion; the
registry gate enforces it.

**4. One fairness metric to rule them all.** Different decision
types warrant different fairness definitions; the impossibility
of simultaneously satisfying several is a mathematical fact, not
a policy failing. The framework requires argued choice per
system, not one-size-fits-all.

**5. Explainability as a report-on-request.** Generating
explanations only when a regulator asks is a signal that the
platform does not treat explainability as a first-class artifact.
The framework requires it as a side-effect of evaluation.

**6. Ethics Board with no charter.** An "AI Ethics Board" that
meets when it can, has no defined authority, and does not record
dissent is a meeting. The reference charter is defended precisely
because the charter is where authority lives.

**7. Board pack assembled manually.** If the Board Risk Committee
pack is assembled from slides each quarter, the underlying
records are not adequate, and the assembly is where the truth
gets lost. Reference packs are generated.

**8. Public transparency report written like a marketing brochure.**
A transparency report that reads like a corporate values page is
not transparency; it is public relations. The reference report is
produced from records and cites its own sources.

**9. Ignoring regulatory drift.** A framework tuned exactly to
the EU AI Act as of a specific date decays. The reference
framework treats individual requirements as policy-engine items
so a change is a policy update, not a project.

**10. Named-person dependencies.** If the framework only works
while the current Chief Risk Officer is in seat, the framework
is a personal project, not an enterprise governance instrument.
Every role in the reference framework is a role, not a name.

## 6. References

Regulatory, standards, and framework references cited or relied
upon by this solution:

- **EU Artificial Intelligence Act** — Regulation (EU) 2024/1689.
  Risk classification (Titles II–III), Annex III (high-risk use
  cases including credit-adjacent and employment), obligations
  on providers and deployers of high-risk AI systems (Articles
  9–15), transparency obligations (Article 50), post-market
  monitoring (Article 72), conformity assessment (Article 43).
  <https://eur-lex.europa.eu/eli/reg/2024/1689/oj>
- **NIST AI Risk Management Framework (AI 100-1)** — the four
  functions (GOVERN, MAP, MEASURE, MANAGE) frame the operating
  model.
  <https://www.nist.gov/itl/ai-risk-management-framework>
- **NIST AI RMF Generative AI Profile (AI 600-1)** — supplemental
  guidance for generative-AI risks, referenced where Aurora
  deploys generative capabilities.
  <https://www.nist.gov/itl/ai-risk-management-framework>
- **ISO/IEC 42001:2023** — Artificial intelligence — Management
  system. The reference framework aligns to ISO/IEC 42001's
  management-system disciplines (policy, roles, risk assessment,
  internal audit, management review).
  <https://www.iso.org/standard/81230.html>
- **ISO/IEC 23894:2023** — Artificial intelligence — Guidance on
  risk management. Complements 42001 with risk-management
  process detail.
  <https://www.iso.org/standard/77304.html>
- **ISO/IEC 27001:2022** — Information security management
  systems. Referenced as the neighbouring management-system to
  which the AI-specific system integrates.
  <https://www.iso.org/standard/27001>
- **OECD AI Principles** — <https://oecd.ai/en/ai-principles>
- **General Data Protection Regulation (GDPR)** — Regulation
  (EU) 2016/679. In particular Article 22 (automated
  decision-making) and Recitals 71–72.
  <https://eur-lex.europa.eu/eli/reg/2016/679/oj>
- **Brazil Lei Geral de Proteção de Dados (LGPD)** — Law No.
  13,709/2018. Article 20 on review of automated decisions.
  <https://www.planalto.gov.br/ccivil_03/_ato2015-2018/2018/lei/l13709.htm>
- **India Digital Personal Data Protection Act, 2023 (DPDP)**.
  <https://www.meity.gov.in/writereaddata/files/Digital%20Personal%20Data%20Protection%20Act%202023.pdf>
- **UK Data Protection Act 2018** and the ICO's guidance on AI
  and data protection.
  <https://www.legislation.gov.uk/ukpga/2018/12/contents>
  <https://ico.org.uk/for-organisations/uk-gdpr-guidance-and-resources/artificial-intelligence/>
- **UK Equality Act 2010** — non-discrimination framework
  referenced for UK-scope systems.
  <https://www.legislation.gov.uk/ukpga/2010/15/contents>
- **US federal non-discrimination statutes** as applicable to
  insurance and employment (Civil Rights Act of 1964, Age
  Discrimination in Employment Act, Americans with Disabilities
  Act, Genetic Information Nondiscrimination Act) — cited as
  neighbouring law that the framework is designed against.
- **NAIC Model Bulletin on the Use of Algorithms, Predictive
  Models, and Artificial Intelligence Systems by Insurers**
  (adopted 2023) — the sectoral expectation for insurance in
  the US; state-by-state adoption applies.
  <https://content.naic.org/> (NAIC portal — Model Bulletin
  text is distributed by NAIC)
- **Colorado SB 21-169** — algorithmic underwriting; the
  Colorado Division of Insurance rules on external consumer
  data and information sources are the operative implementation.
  <https://leg.colorado.gov/bills/sb21-169>
- **NYC Local Law 144** — automated employment decision tools;
  cited as an example of state/city-law that the framework
  survives without a rewrite.
  <https://www.nyc.gov/site/dca/about/automated-employment-decision-tools.page>
- **Illinois HB 3773** — Illinois AI in employment amendments to
  the Human Rights Act (effective 2026). Cited as another
  example of state-law drift the framework is designed against.
  <https://www.ilga.gov/> (Illinois General Assembly portal)
- **EIOPA opinion on artificial intelligence governance and
  risk management** — European Insurance and Occupational
  Pensions Authority; sectoral supervisor guidance the
  framework is defended against.
  <https://www.eiopa.europa.eu/>
- **White House OSTP — Blueprint for an AI Bill of Rights** —
  cited as a US-federal policy signal; non-binding.
  <https://www.whitehouse.gov/ostp/ai-bill-of-rights/>
- **Council of Europe Framework Convention on AI** (2024) —
  cited as an emerging international-treaty signal.
  <https://www.coe.int/en/web/artificial-intelligence>

Related solutions in this repository:

- `projects/project-402-global-ai-platform-architecture/SOLUTION.md`
  — the platform architecture on which this framework is enforced.
- `projects/project-401-transformation-strategy/SOLUTION.md` —
  the transformation-strategy view that funds a programme like this.
- `modules/mod-405-responsible-ai/SOLUTION.md` — the module view
  of the same problem space at coarser granularity.
- `modules/mod-403-enterprise-governance/SOLUTION.md` — the
  enterprise-governance patterns this framework composes with.

## Time budget

- **Review-time read**: 45 minutes to read this SOLUTION plus
  `framework/responsible-ai-framework.md`. This is the minimum
  to participate in a framework review.
- **Full deliverable read**: 4–5 hours to read all artifacts
  (SOLUTION, framework, ethics-board charter, rubric) with the
  referenced regulations open in a second tab.
- **Learner-side build**: a strong learner produces a defensible
  first draft in 25–35 hours of focused work, plus a further
  10–15 hours iterating after Legal and internal-audit review.

## Status

**Version**: 1.0
**Status**: Reference solution
**Owner**: Senior Architect curriculum track
