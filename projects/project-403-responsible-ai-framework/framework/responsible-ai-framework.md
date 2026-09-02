# Responsible AI Framework — Reference Artifact

> Reference Responsible AI framework for Project 403. Companion to
> `../SOLUTION.md` and `../governance/ethics-board-charter.md`. Read the
> SOLUTION first for the reasoning; this document is the artifact a
> framework review, an internal audit, and a Legal review would work from.

## 1. Framework principles

Aurora Life Group commits to five Responsible AI principles. Each
maps to at least one enforced control. Principles without controls
are not published.

1. **Lawfulness and rights.** AI systems are operated in compliance
   with the EU AI Act, applicable insurance-sectoral regulation
   (EIOPA opinions, NAIC Model Bulletin, national supervisors),
   data-protection law (GDPR, LGPD, DPDP, UK DPA, US state
   privacy law), and non-discrimination law of the affected
   jurisdictions.
2. **Human oversight in scope.** Every high-risk AI system has a
   designated human oversight role, with defined authority to
   intervene, override, or halt. The oversight design is
   documented as an artifact, not a slogan.
3. **Fairness in evidence, not intent.** Every high-risk and
   material limited-risk system declares its fairness posture
   before deployment and generates the corresponding evidence at
   evaluation.
4. **Explainability appropriate to use.** Every high-risk system
   ships with an explanation strategy suitable to the audience
   receiving it — the individual affected, the reviewer, the
   regulator, the governance function.
5. **Transparency by default, private by exception.** Aurora
   publishes what it operates in aggregate; exceptions are
   documented, approved, and counted.

The connection between each principle and the control that
enforces it is stated explicitly in Section 4.

## 2. Scope

**In scope**:

- AI systems developed in-house by Aurora, including modeling,
  scoring, ranking, generation, and recommendation systems that
  materially affect a decision about a person, a policy, or a
  claim.
- AI systems procured from a vendor and deployed under Aurora's
  brand, on Aurora's decisions.
- Foundation-model-based systems (whether accessed via an API,
  hosted internally, or fine-tuned) used in the above roles.

**Out of scope of this framework** (governed elsewhere):

- Statistical, actuarial, and rules-based systems that do not
  contain a learned component and do not present the risks the
  EU AI Act or NIST AI RMF are directed at. These are governed
  by Aurora's actuarial governance, Model Risk Management (MRM),
  and IT change-control frameworks.
- Non-AI decision-support tooling (BI dashboards, spreadsheet
  models) that a human uses to inform a discretionary decision.
- Vendor products that do not affect Aurora's own decisions
  (e.g., internal productivity AI whose outputs do not touch
  the underwriting, claims, or member-facing paths).

Scope decisions are recorded in the registry entry as part of
the intake artifact. A borderline case is resolved by the AI
Ethics Board, whose charter defines the authority to do so.

## 3. Roles and accountabilities

Roles are named, not people.

- **Chief Risk Officer** — accountable to the Board for the
  Responsible AI programme end-to-end.
- **Head of Responsible AI** (dotted to CRO) — programme
  ownership; convenes the AI Ethics Board.
- **AI Ethics Board** — chartered separately (see
  `../governance/ethics-board-charter.md`).
- **Business unit accountable executive** — accountable for the
  systems operated in the business unit; named in each registry
  entry as a role (e.g., Chief Underwriting Officer).
- **Model owner (first-line)** — accountable for a specific system
  end-to-end: intake, evidence, monitoring, response.
- **Model Risk Management (MRM) reviewer (second-line)** —
  independent challenge of first-line evidence; sign-off gate
  for high-risk promotion.
- **Internal Audit (third-line)** — periodic assessment of
  control effectiveness across the RAI programme.
- **Chief Compliance Officer** — regulatory-notification path;
  sign-off on classification decisions with regulatory
  implications.
- **Chief Legal Officer / General Counsel** — external
  regulatory-inquiry response; approval of classification changes
  with legal implications.
- **Chief Communications Officer** — approves external
  communications, including the public transparency report.
- **Data Protection Officer** — data-protection-law compliance;
  sign-off on registry entries containing personal-data
  processing.

Business-unit-specific responsibilities are captured in each
registry entry, not in this document, so that reorganization
does not silently break the framework.

## 4. Enforcement matrix — principles to controls

Every principle in Section 1 is enforced by one or more named
controls. This table is the framework's answer to "where is the
principle enforced?"

| Principle | Enforced by | At what moment | On failure |
|---|---|---|---|
| **1. Lawfulness and rights** | Registry classification field; policy engine gate on prohibited categories | Registration; every deployment | Registration rejected; incident logged; Ethics Board notified |
| **2. Human oversight** | Registry evidence bundle: `human-oversight-design.md` required for high-risk promotion | Promotion to production | Promotion blocked; MRM notified; Ethics Board reviews at next meeting if override requested |
| **3. Fairness in evidence** | Registry fairness declaration + evaluation artifact + monitoring wiring | Promotion (all three required); post-deployment (monitoring drift) | Promotion blocked; monitoring drift triggers response per declaration; repeat drift escalates to Ethics Board and Board Risk Committee |
| **4. Explainability** | Registry explanation-strategy artifact; explanation-generator configured for the audiences named | Promotion (both required); routine (explanations produced as side-effect of evaluation) | Promotion blocked; missing routine explanation logged as a control incident; MRM notified |
| **5. Transparency** | Transparency-report generator reads registry; exceptions require Ethics Board sign-off logged in registry | Annual report cycle; quarterly update cycle | Report cannot be published without generator run; unlogged exception blocks publication |

**Reading this table**: every claim the framework makes appears
in one of five rows, and every row names the object that holds
the claim. If a claim cannot be located in this table, it is not
enforced, and it is either removed from the framework or
downgraded to an aspiration.

## 5. AI system inventory — registry schema

The reference registry entry is the framework's single source of
truth for a system. Fields marked **(R)** are required for
registration; **(P)** are required for promotion to production;
**(M)** are maintained during operation.

### 5.1 Identity and ownership

- **(R) System name** — human-readable and unique within Aurora.
- **(R) System version** — semantic-version-compatible.
- **(R) Artifact hash** — hash of the deployed artifact bundle;
  updated per version.
- **(R) Business unit** — Underwriting, Claims, Group Benefits,
  Reinsurance, Group functions.
- **(R) Accountable executive role** — role, not person.
- **(R) Model owner role** — role, not person.
- **(P) MRM reviewer role** — role, not person.
- **(M) On-call rotation identifier** — the rotation that handles
  operational incidents on the system.

### 5.2 Purpose and scope

- **(R) Purpose statement** — one sentence, reviewer-readable,
  the same statement cleared for the public transparency report.
- **(R) Affected populations** — who is affected by decisions the
  system contributes to.
- **(R) Decision type** — the taxonomy value: e.g., underwriting
  eligibility, premium calculation input, claims triage routing,
  fraud-score contribution, member recommendation.

### 5.3 Data lineage

- **(R) Training data pointer** — the datasets and their
  classifications (residency class, sensitivity class, provenance).
  Not the data itself; a lineage pointer.
- **(R) Data-governance record** — the artifact establishing the
  representativeness, coverage, and known limitations of the
  training data.
- **(P) Validation and testing data pointers** — separate from
  training; documented independence.
- **(M) Data-drift-monitoring configuration** — signals watched,
  cadence, thresholds.

### 5.4 Regulatory classification

- **(R) EU AI Act classification**:
  - `prohibited` — registration refused; escalated.
  - `high-risk` — full evidence bundle required for promotion.
  - `limited-risk` — transparency configuration required.
  - `minimal-risk` — standard governance.
- **(R) Insurance-sectoral scope** — insurance-regulated (yes/no),
  which supervisor(s).
- **(R) Consumer-credit-adjacent scope** — yes/no; where yes, the
  applicable rules.
- **(R) US state-law scope** — the states in which the affected
  consumer resides, mapped to state-law rules the framework
  currently tracks (Colorado SB 21-169; NYC Local Law 144;
  Illinois HB 3773; equivalents added by policy update as they
  land).
- **(R) Other-jurisdiction scope** — UK, EU member states, LGPD
  Brazil, DPDP India, Singapore PDPA, others as applicable.
- **(P) Legal sign-off** — CLO or delegate on classification
  decisions with legal-liability implications.

### 5.5 NIST AI RMF profile

- **(P) Function coverage** — evidence pointer for each of GOVERN,
  MAP, MEASURE, MANAGE.
- **(P) Gap register** — declared gaps against NIST AI RMF, with
  remediation dates.

### 5.6 Fairness declaration

- **(P) Fairness definition** — the metric family chosen and the
  argued rationale for that choice.
- **(P) Protected attributes analyzed** — where lawful; where
  inference is required, the inference method and its known
  error properties.
- **(P) Evaluation cadence** — pre-deployment; post-deployment
  cadence; triggering events.
- **(P) Thresholds and actions** — the numeric threshold at which
  a defined action fires; the action list (pause, retrain, escalate,
  notify).
- **(M) Latest evaluation artifact** — pointer to the artifact
  produced by the last evaluation run.

### 5.7 Explanation strategy

- **(P) Audiences** — the audiences the system explains itself to;
  the framework's default four are: individual affected, reviewer,
  regulator, governance.
- **(P) Method per audience** — the explanation method
  (feature-attribution, counterfactual, natural-language summary,
  rule-list, exemplar) chosen per audience.
- **(P) Persistence policy** — how long the individual-facing
  explanation is retained, and where.
- **(M) Explanation quality signal** — the monitoring signal on
  the explanation's own quality (e.g., faithfulness measure,
  reviewer satisfaction).

### 5.8 Human oversight design

- **(P) Oversight-design document** — required artifact.
- **(P) Reviewer role** — role, not person; qualifications documented.
- **(P) Override authority** — who can override, how, and how the
  override is logged.
- **(P) Audit hook** — the audit trail signal produced whenever an
  oversight action is taken.

### 5.9 Post-market monitoring

- **(P) Monitoring plan** — signals monitored, cadence, incident
  thresholds, accountable individual (role).
- **(M) Latest monitoring run** — pointer.
- **(M) Open incident register** — pointer to the system's
  incidents in the corporate incident-management system.

### 5.10 Approvals and history

- **(P) Approvals log** — chronological record of sign-offs.
- **(P) Ethics Board decision (where applicable)** — pointer to
  the Ethics Board minute recording the decision.
- **(P) External assessment (where applicable)** — notified-body
  assessment record; sectoral-audit record.
- **(M) Change log** — every material change to the system
  produces a new entry that re-enters the approval flow.

## 6. Classification playbook

The framework classifies systems against three orthogonal axes:

1. **EU AI Act risk class** — prohibited, high-risk, limited-risk,
   minimal-risk.
2. **Sectoral scope** — insurance-regulated, employment-adjacent,
   consumer-credit-adjacent, none.
3. **Jurisdictional overlay** — EU, UK, US federal, US state
   overlays (Colorado, NYC, Illinois, others as applicable),
   Brazil, India, Singapore.

Aurora classifies at intake using the following playbook. The
playbook is deliberately conservative — when the answer is
"probably not high-risk," the classification defaults to
high-risk pending Legal sign-off, on the reasoning that a false
high-risk classification imposes evidence cost, whereas a false
low-risk classification imposes regulatory cost.

### 6.1 EU AI Act — decision tree summary

- Does the system's use case appear in **Article 5-equivalent
  prohibited categories**? → **Prohibited**. Registration refused.
- Does the use case appear in **Annex III** — biometrics for
  identification, critical infrastructure, education/vocational
  training, employment/worker management, essential private and
  public services (including creditworthiness and health/life
  insurance risk assessment), law enforcement, migration/asylum,
  administration of justice/democratic processes? → **High-risk**.
- Is the system covered by the **transparency obligations of
  Article 50** (interaction with individuals, generation of
  synthetic content, deepfakes, emotion recognition, biometric
  categorization not otherwise prohibited)? → **Limited-risk**.
- Otherwise → **Minimal-risk**.

Aurora's own systems that predominantly land as high-risk under
this decision tree:

- Underwriting risk assessment (life-and-health) — Annex III
  point on insurance risk assessment.
- Claims fraud scoring and triage — insurance-adjacent, may be
  high-risk if the decision material to the claimant is not
  independently reviewed.
- Group-benefits worker-management tooling — Annex III point on
  employment and worker management.

### 6.2 Sectoral overlays

- **Insurance-regulated** — subject to the NAIC Model Bulletin
  (US, state adoption); to EIOPA supervisory expectations
  (EU/EEA); to national supervisor guidance (PRA/FCA, etc.).
- **Employment/worker-management** — subject to Aurora-jurisdiction
  employment law and to specific state or national laws such as
  NYC Local Law 144 and Illinois HB 3773.
- **Consumer-credit-adjacent** — subject to relevant credit-
  discrimination law (US ECOA and Regulation B, UK Consumer
  Duty framing, etc.) where the decision materially affects
  credit access.

Overlays are additive. A system that is Annex III high-risk *and*
insurance-regulated *and* Colorado-scope carries all three sets
of obligations.

## 7. Bias and explainability standards

### 7.1 Fairness metric selection guidance

Fairness definitions are not interchangeable. The framework does
not standardize on one — several are mathematically incompatible.
The framework requires the model owner to choose and argue.

The choice guidance:

- **Decisions with a binary label and a policy interest in equal
  error rates across groups** (e.g., claims fraud triage where a
  false-positive imposes a burden on the claimant and a
  false-negative imposes cost on Aurora) — typically an
  **equalized-odds** or **error-rate-balance** framing.
- **Decisions where the payoff scale is continuous and calibration
  matters** (e.g., underwriting risk score contribution) —
  typically a **calibration-within-groups** framing, with
  awareness of the trade-off against equalized odds.
- **Decisions where the acceptance/rejection outcome is what the
  affected individual experiences** and where policy interest is
  in equal outcomes — typically a **demographic-parity** or
  **conditional-demographic-parity** framing, with awareness of
  the calibration trade-off.

The model owner declares the framing and the rationale in the
registry. MRM challenges the choice in review. Ethics Board
reviews the challenged case where MRM and the model owner do not
converge.

**Where analysis of protected attributes is restricted by law**
(e.g., US insurance-sector rules on the use of certain
attributes for pricing), the framework requires the model owner
to document how the analysis is done consistently with the
restriction (e.g., audit-only analysis, aggregate-level
monitoring, proxy-analysis with disclosed error).

### 7.2 Fairness monitoring

- **Pre-deployment evaluation** produces the fairness evidence
  artifact declared in the registry.
- **Post-deployment monitoring** runs the same metric on
  in-production data at the declared cadence.
- **Drift response** — three-tier:
  - **Watch** — metric trends toward threshold. Model owner
    documents observation; no action.
  - **Warning** — threshold breached once. Model owner triggers
    investigation; MRM notified; Ethics Board notified at next
    meeting.
  - **Action** — threshold breached repeatedly, or breach is
    material. Defined action fires (pause, retrain, escalate,
    notify). Ethics Board interim notification if warranted;
    Board Risk Committee interim notification if warranted.

### 7.3 Explainability standards

Explanations are designed per audience:

- **Individual affected**. The primary audience. Explanation
  meets the applicable legal standard (GDPR Article 22
  meaningful information about the logic; sectoral disclosure
  requirements; state-law requirements in scope). Written in
  the language of the affected individual; delivered on the
  channel the individual reached Aurora on; retained for the
  applicable statutory period.
- **Reviewer / accountable person**. The explanation the human
  oversight role uses to review or override. More technical
  than the individual-facing explanation; persisted in the
  case-management system.
- **Regulator / auditor**. On request, the system-level
  documentation from the registry evidence bundle; where the
  regulator asks for record-level detail, retrievable from
  the case-management system.
- **Internal governance (MRM, Ethics Board)**. Aggregate
  explainability quality metrics; incident-level drill-down on
  request.

**Explanation quality itself is monitored.** The framework
requires the model owner to declare an explanation-quality signal
and to monitor it — a low-fidelity or degenerate explanation is a
control failure, not a documentation quirk.

## 8. Post-market monitoring

Every high-risk system runs a post-market monitoring plan against
the following categories at minimum:

- **Performance drift** — the primary predictive-performance
  metric on live data, against the pre-deployment baseline.
- **Fairness drift** — the declared fairness metric.
- **Data drift** — the distribution of inputs, against the
  training distribution.
- **Explanation drift** — the explanation-quality signal, where
  applicable.
- **Incident signal** — any Aurora-side or external report
  associated with the system.

Monitoring signals feed the corporate incident-management system
with defined severity mapping. Ethics Board receives an aggregate
monitoring summary at each meeting; Board Risk Committee receives
a quarterly monitoring summary in the standing pack.

## 9. Ethics Board interaction with the framework

The AI Ethics Board is chartered in
`../governance/ethics-board-charter.md`. The framework's touchpoints
with the Board are:

- **Registration of borderline cases** (scope in/out; classification
  contested).
- **Promotion of high-risk systems** (binding; the Board's decision
  is a registered artifact).
- **Overrides of fairness / explainability gates** (binding).
- **Emerging capability without existing taxonomy entry** (binding
  interim classification pending policy update).
- **Transparency-report exceptions** (binding).
- **Monitoring alerts at Warning tier or above** (advisory; the
  Board's advice is registered).
- **Post-incident review** on any high-severity RAI incident
  (advisory).

Every Board interaction is recorded to the registry. Board
dissent is recorded. Board's own composition and effectiveness
are reviewed annually.

## 10. Regulatory landscape and roadmap

### 10.1 Currently tracked regulations

The framework tracks the following as of the reference version.
Updates are policy-engine changes, not framework rewrites.

- EU AI Act (Regulation 2024/1689) — phased application through
  2027.
- GDPR (Regulation 2016/679) — Article 22 and Recitals 71–72.
- LGPD (Brazil) — Article 20.
- DPDP Act (India, 2023).
- UK DPA 2018; UK GDPR; ICO AI guidance; UK Equality Act 2010.
- US state privacy laws (California, Colorado, Connecticut,
  Virginia, Utah, and others as they land).
- NAIC Model Bulletin on the use of AI by insurers, and state
  adoptions.
- Colorado SB 21-169 (algorithmic underwriting) and CDOI rules.
- NYC Local Law 144 (automated employment decision tools).
- Illinois HB 3773 (AI in employment, effective 2026).
- EIOPA opinion on AI governance and risk management.
- Council of Europe Framework Convention on AI (2024).

The tracking list is maintained by the Head of Responsible AI
with Legal input, and is reviewed at least quarterly by the
Ethics Board.

### 10.2 EU AI Act compliance roadmap

Aurora's roadmap for EU AI Act compliance is the
inventory-classify-remediate-conform sequence:

**Inventory (Phase 0, Months 0-3)**. Register every AI system.
Provisional classification. Evidence-gap register.

**Classify (Phase 1, Months 3-6)**. Ethics Board confirms
classification for each system, with Legal sign-off on high-risk
cases. Prohibited-category refusals recorded.

**Remediate (Phase 2, Months 6-18)**. For each high-risk system,
close the evidence gaps: data-governance record, technical
documentation, transparency information, human-oversight design,
fairness declaration and evaluation, explanation strategy,
post-market monitoring plan. Systems that cannot close in time
are frozen from material change until they do.

**Conform (Phase 3, Months 18-24)**. Conformity assessment
completed for each high-risk system; self-assessment where the
Act permits; notified-body assessment where required. External
review of the RAI programme's own operation.

**Operate (Phase 4, Months 24+)**. Post-market monitoring becomes
the routine mode. New systems enter through the same intake.
Regulatory drift (Act guidance updates, sectoral supervisor
communications, state-law landings) is absorbed as policy-engine
changes.

Phase gates are the Ethics Board sign-off at Phase 1 completion;
the MRM sign-off at Phase 2 per-system completion; the external
review at Phase 3; and the annual review at Phase 4.

## 11. Public transparency reporting

### 11.1 Cadence and content

- **Annual public transparency report** — full report as specified
  in SOLUTION §2.7.
- **Quarterly update** — delta since the annual report; material
  events; pointer to the annual report.
- **Ad-hoc disclosures** — as required by regulatory-notification
  obligation or as advised by Chief Communications Officer with
  Ethics Board input.

### 11.2 Production pipeline

The transparency-report generator is a scheduled job with the
following steps:

1. Read the registry: system count by classification, purpose
   statements (public field), fairness posture summary,
   oversight posture summary.
2. Read the monitoring stack: incident summary, alert counts.
3. Read the Ethics Board records: meetings held, decisions,
   dissent counts, external-review status.
4. Produce report draft against the versioned template.
5. Route to Legal, Communications, and CRO for review.
6. Publish.

Manual intervention between step 1 and step 5 is a control
smell. Reviewers may edit language and remove details that
Legal or Communications determine should not be public — that
is what the review is for — but reviewers should not have to
compute numbers or reconcile records.

### 11.3 Exceptions policy

The framework distinguishes:

- **Never-public content**: security-sensitive detail
  (adversarial hardening, red-team findings); model-specific
  technical detail that materially aids gaming.
- **Case-by-case-public content**: incident detail beyond the
  regulatory-notification obligation; specific system detail
  where confidentiality is warranted.
- **Default-public content**: everything else.

Case-by-case decisions are Ethics-Board-binding and recorded.

## 12. Board oversight and reporting

### 12.1 Board Risk Committee — quarterly standing pack

Automatically produced fields:

- Inventory count by classification, delta since last cycle.
- Exception counts (Ethics Board overrides, monitoring alerts
  at Warning tier or above, policy waivers).
- High-risk system incident summary.
- Regulatory landscape update.

Manually authored fields (with template):

- Rotating deep-dive on one high-risk system or one control.
- Any material Ethics-Board finding.
- Any external-audit finding.

### 12.2 Audit Committee — semi-annual standing pack

Automatically produced fields:

- Internal audit findings on the RAI programme, with status.
- Ethics Board effectiveness review (annual, in the pack that
  cycle).

Manually authored fields:

- Remediation status commentary.
- Forward look on the next audit cycle.

### 12.3 Escalation thresholds

- Any high-risk system with a fairness metric drifted past the
  declared threshold → Ethics Board next meeting; Board Risk
  Committee next cycle (or interim ad-hoc trigger if severity
  warrants).
- Any promotion override by the Ethics Board → Board Risk
  Committee next cycle.
- Any prohibited-category registration attempt → Board Risk
  Committee immediate notification.
- Any regulator inquiry naming an Aurora AI system → Board Chair
  and Ethics Board Chair same-day notification.

## 13. Operations

### 13.1 Reference sizing (steady state, post-Phase 3)

| Function | Global HQ | Per major business unit | Notes |
|---|---|---|---|
| **Responsible AI programme office** | ~6 | — | Head of RAI + programme staff |
| **AI Ethics Board secretariat** | ~2 | — | Meeting logistics, minutes, records |
| **MRM — AI-specialist reviewers** | ~4 | ~2 | Second-line challenge |
| **First-line RAI liaison** | — | ~2 | Business-unit-embedded |
| **Registry / policy-engine platform engineering** | ~4 | — | Shared with the platform team from Project 402 where present |
| **Compliance / legal support** | ~2 | — | Not headcount unique to RAI; sliver of Compliance and Legal |

Actual sizing depends on system count. The above is the "below
this, the framework is not honestly operable" floor. A design
that assumes less needs to name what it trades off (typically:
challenge depth, or classification decision speed).

### 13.2 Incident response

- Regional / business-unit incident response owns first response.
- RAI-classified incidents (fairness breach, explanation quality
  breach, regulatory inquiry) invoke the RAI incident path:
  RAI programme office informed; Ethics Board Chair informed at
  Warning tier; Board Risk Committee informed at Action tier or
  above.
- Cross-jurisdictional RAI incidents (an EU AI Act
  post-market-monitoring event with US-state-law implications)
  are handled by the RAI programme office with Legal and
  Compliance at the bridge.

### 13.3 Change management

- Framework changes flow through the same policy-as-code path as
  the platform. Ethics Board approves material changes; the
  Head of RAI approves minor operational changes.
- Registry schema changes require a versioned migration and a
  policy-engine dry-run.
- Regulatory-change absorption: a landed regulation becomes a
  policy update (new classification rule, new evidence field,
  new report field). It is not a framework rewrite unless it
  fundamentally changes one of the five principles.

## 14. ADRs (index)

Reference decision records that a framework review should be
able to trace. In an actual submission, each ADR is a short
document (title, context, decision, consequences).

- **ADR-001** — Five principles, mapped one-to-one to controls.
- **ADR-002** — Registry as source of truth for RAI governance.
- **ADR-003** — Ethics Board as advisory-with-teeth; binding
  scope specifically named.
- **ADR-004** — Fairness definition chosen per system; framework
  does not mandate a single definition.
- **ADR-005** — Explanation strategy declared per audience.
- **ADR-006** — Post-market monitoring on five categories
  minimum.
- **ADR-007** — Transparency report generated from records; not
  drafted from slides.
- **ADR-008** — Board packs generated on schedule; escalation
  thresholds stated.
- **ADR-009** — Roadmap sequenced by reversibility; inventory
  first, backfill last.
- **ADR-010** — Named-role dependencies only; no named-person
  dependencies.

## 15. Known open items

Items marked `needs-research` in the SOLUTION and here are the
ones that would be researched during a real programme stand-up
and that do not change the shape of the framework:

<!-- needs-research: notified-body vs. self-assessment path for
each Aurora high-risk system under EU AI Act Article 43 modules
— requires Legal per-system determination at Phase 3 promotion
time. Tracked as FOLLOWUP-EUAI-CA-01. -->

<!-- needs-research: US-state-law-specific evidence templates
under NAIC Model Bulletin state adoptions — the state-by-state
implementation of the Model Bulletin is not uniform and specific
evidence templates will be Legal-per-state at the point Aurora
is subject to each. Tracked as FOLLOWUP-US-STATE-EV-01. -->

<!-- needs-research: sectoral-supervisor-specific commitments —
EIOPA opinion, PRA and FCA thematic-review expectations, MAS
technology-risk-management guidance, and equivalents. Framework
cites these as supervisory expectations; the specific bilateral
commitments Aurora makes are a business decision the framework
informs but does not itself contain. Tracked as
FOLLOWUP-SEC-SUPER-01. -->

None of these change the shape of the framework. All would
change specific numeric commitments or template contents at
build-out.
