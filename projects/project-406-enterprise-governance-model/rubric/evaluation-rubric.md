# Evaluation Rubric — Enterprise AI Governance Model

> Grading rubric for learner submissions to Project 406. The
> rubric weights **defensibility of the scope definition** and
> **enforceability of the decision-authority model (RACI)**
> above **breadth of governance-body coverage**. A learner
> who submits a governance chart with fifteen bodies and no
> defended decision-authority model will score below a learner
> who submits five bodies with defended scopes and a working
> RACI.

**Scoring model.** Six weighted dimensions, 0–100 within each,
then weighted-summed to a final 0–100 governance-model score.
Two dimensions are non-passing thresholds: a submission
scoring below 60 on either Dimension 1 (scope) or Dimension
2 (RACI) is non-passing regardless of other scores.

**Grader posture.** The rubric is written for a reviewer who
would sit on the Board Strategy Committee, the Board Audit
Committee, or the AI Governance Committee — someone who is
testing whether they could sign this model out to the Board
this quarter and defend it in a Caremark-line inquiry, not
whether the submission looks impressive.

---

## Dimension 1 — Scope-definition defensibility (weight: 20%)

**What the grader is testing.** Are the scope tests functional
and published; do they exclude decisions as much as they
include them; does the ambiguity rule route the failure mode
governance is designed to prevent (in-scope items mis-routed
out) rather than the reverse; can a specific system be
walked through the tests by an auditor from the artifact?

### 1.1 Scoring bands

| Band | Description |
|---|---|
| **90–100** | Scope is defined through functional tests (data, autonomy, regulatory, reputation) with argued reasoning per test. Exclusive test lists three or more argued conditions. Ambiguity rule is explicit: ambiguous items are treated as in-scope until argued out with a documented case; recurring rulings escalate to the enterprise governance body. The submission takes a position on named vocabulary traps (rule-based systems whose rules were fitted to historical data, systems where "AI" does not appear in project documentation) and defends it. An auditor could walk any Halcyon-shaped system through the tests in under fifteen minutes from the published artifact. |
| **75–89** | Scope tests are functional and mostly complete. Ambiguity rule is present but under-specified. Exclusive test is written but does not fully argue the conditions. One or two vocabulary traps not addressed. |
| **60–74** | Scope is present as a definition ("AI is...") with example lists. Ambiguity rule is informal ("we'll discuss ambiguous cases"). Exclusive test is missing or fragmentary. |
| **40–59** | Scope is aspirational — the submission asserts that scope exists but the reader cannot apply it to a novel system. |
| **0–39** | No written scope definition, or the definition is a mission statement about "AI at Halcyon" with no tests. |

### 1.2 Grader questions

- Can the grader take a novel Halcyon-shaped system and walk
  it through the scope tests in under fifteen minutes?
- Is the ambiguity rule biased toward the failure mode
  governance is designed to prevent (in-scope items routed
  out)?
- Are the exclusive-test conditions defended, or hand-waved?
- Does the submission address vocabulary traps (relabelled
  work, non-obvious statistical-inference systems)?
- Where does the framework re-examine scope on a defined
  cadence?

### 1.3 Common down-marks

- Definition of "AI" rather than functional tests (down-mark
  to at most 65) — the definition invites arguments about
  whether a system is "really AI" rather than about whether
  a specific test is triggered.
- No exclusive test (down-mark to at most 65) — an inclusive
  test without an exclusive test routes half of Halcyon's IT
  through AI governance.
- Ambiguity rule biased toward out-of-scope (down-mark to at
  most 60) — this is the failure mode the framework is
  designed to prevent.
- Vocabulary-based tests ("if 'AI' appears in project
  documentation") (down-mark to at most 60) — trivially
  gameable and creates perverse incentives.
- No cadence for scope-tests review (down-mark to at most
  75).

**Non-passing threshold: below 60 fails this dimension and
the overall submission regardless of other scores.**

---

## Dimension 2 — Decision-authority enforceability (RACI) (weight: 20%)

**What the grader is testing.** Is decision authority
enumerated by class and by role, not by seniority; are
escalation paths defined and archival discipline consistent
across the classes; can the Chief Financial Officer, the
Head of Internal Audit, and a first-line engineering manager
each read the same class assignment the same way?

### 2.1 Scoring bands

| Band | Description |
|---|---|
| **90–100** | Decision classes are enumerated (typically eight to twelve; more than fifteen invites down-marks). Each class has: named R, exactly one A per decision, C roles (with veto-C distinguished from C), and I roles (with ack-I distinguished from I). Thresholds are named where a class has a threshold. Escalation paths are defined per class. Fallback rules exist for unfilled roles (successor register referenced). Amendment procedure is named. Worked examples illustrate the RACI in practice for at least two class-3-analogue decisions. |
| **75–89** | Decision classes and RACI cells are largely complete. Thresholds mostly present. Escalation defined. One or two fallback or veto-C distinctions missing. |
| **60–74** | Decision classes exist in prose. R/A/C/I assignments are informal. Thresholds not named. Escalation described as "the appropriate authority." |
| **40–59** | RACI is a table of committee names against decision types. R/A/C/I are not distinguished; A appears in multiple cells. Escalation is not defined. |
| **0–39** | No RACI, or decision authority is described as "senior leadership approves big decisions." |

### 2.2 Grader questions

- Can the RACI be read the same way by three different
  Halcyon officers?
- Is there exactly one A per decision (or a defined
  co-A discipline)?
- Are veto-C roles distinguished from consultative C roles?
- Are thresholds named or is "big" the threshold?
- Where does an unfilled role escalate to, and is the
  successor register linked?
- Do the worked examples show the RACI in practice for a
  Class 3 deployment, a Class 4 allocation, and a Class 2
  regulatory classification?

### 2.3 Common down-marks

- Seniority-based RACI ("executives approve big AI
  decisions") (down-mark to at most 55) — this is the
  failure mode the framework is designed to prevent.
- Multiple A per class without a defined co-A discipline
  (down-mark to at most 65) — invites accountability drift.
- No veto-C distinction (down-mark to at most 75) —
  General Counsel and CISO participation is not equivalent
  to substantive consultation on regulatory-adjacent items.
- No thresholds named (down-mark to at most 70) — "large
  spend" is not a threshold.
- No fallback for unfilled roles (down-mark to at most 70).
- No worked examples (down-mark to at most 75) — the RACI
  reads as aspirational without a practice pass.

**Non-passing threshold: below 60 fails this dimension and
the overall submission regardless of other scores.**

---

## Dimension 3 — Governance-body topology (weight: 15%)

**What the grader is testing.** Do the operational bodies
retain scoped authority, with defined interfaces and no
gaps between; does the enterprise-level body coordinate
without collapsing into the operational bodies; is the
Board-committee interface split by substance (Strategy /
Audit / Risk)?

### 3.1 Scoring bands

| Band | Description |
|---|---|
| **90–100** | Existing operational bodies (ARB, RAIB, IPB, EVRB) preserved with defined scopes. Enterprise coordinating body (AIGC or equivalent) exists with authority scoped to framework, interface, portfolio-category, and regulatory-classification classes. Advisory-only classes named. Explicitly out-of-scope classes named. Inter-body interfaces enumerated (ARB↔RAIB, ARB↔IPB, RAIB↔IPB, EVRB↔RAIB, EVRB↔ARB). Board-committee interfaces split by substance (Strategy for framework, Audit for compliance-and-audit, Risk for appetite where present). No decision requires two operational bodies to agree without a named interface; no decision falls between. |
| **75–89** | Operational bodies preserved and enterprise body chartered. Interfaces mostly enumerated. Board-committee split defined. One or two interface gaps or overlaps. |
| **60–74** | Operational bodies are named; enterprise body is present but its authority is under-specified. Interfaces are prose. |
| **40–59** | Operational bodies exist, but the enterprise body overrides them or is absent. Interfaces are ad hoc. |
| **0–39** | Governance is one new body ("AI Council") that centralises everything, or four bodies with no coordination. |

### 3.2 Grader questions

- Are the four existing operational bodies preserved?
- Is the coordinating body scoped so it does not
  individually decide architecture, RAI posture,
  innovation-portfolio allocation, or external-
  communication?
- Are the interfaces between operational bodies enumerated
  with a defined escalation path?
- Where does a strategic-posture change route: Strategy or
  Audit or Risk?
- Where does a director on more than one Board committee
  know which hat is on for a specific AI-oversight
  question?

### 3.3 Common down-marks

- Single centralised AI decision body ("AI Council")
  (down-mark to at most 55) — collapses the operational
  bodies' scoped expertise.
- Coordinating body with individual-system architecture,
  posture, or portfolio-allocation authority (down-mark
  to at most 65) — merges the operational bodies into the
  coordinating body over two quarters.
- Missing inter-body interfaces (down-mark to at most 70).
- Board-committee split not defined (down-mark to at most
  75) — creates the "director on two committees does not
  know which hat" failure.
- All AI oversight in one Board committee (down-mark to
  at most 75).

---

## Dimension 4 — Investment-portfolio and prioritisation model (weight: 15%)

**What the grader is testing.** Is the AI portfolio
categorised with argued criteria; does the CFO consent to
the criteria (not just the aggregate); is the review
cadence named; does the model resist the "loudest
business-unit voice wins" failure?

### 4.1 Scoring bands

| Band | Description |
|---|---|
| **90–100** | AI-adjacent spend is categorised (typically four to six categories: Core-platform, Business-line-AI, Responsible-AI-operations, Innovation-portfolio, External-programme, or defensible equivalents). Categories have ceilings within a CFO-approved aggregate envelope. Prioritisation criteria are named (three to five) and include criteria beyond NPV (strategic-option value, regulatory-exposure reduction, platform-multiplier, defensibility of alternatives). Weighting is per category, not a single formula. Review cadence named (quarterly by AIGC, semi-annually by CFO, annually by BAC). Off-cadence review is scoped and rare. Category-owner authority within category is delegated. |
| **75–89** | Portfolio categories exist with ceilings. Criteria beyond NPV are named. Cadence defined. One or two elements (weighting-per-category, off-cadence rules) partial. |
| **60–74** | Portfolio has categories but ceilings are informal. Criteria are NPV-plus. Cadence is described in prose. |
| **40–59** | Portfolio is an approval queue against a threshold; criteria are NPV alone. |
| **0–39** | No portfolio model; approvals are project-by-project against threshold. |

### 4.2 Grader questions

- Can the CFO defend the portfolio composition to the BAC
  as a portfolio composition, not as a sum of individual
  project cases?
- What criteria beyond NPV are named?
- Does the CFO consent to the criteria, or only to the
  aggregate?
- What happens when a category exceeds its ceiling?
- Does the model resist "loudest business-unit voice" by
  bounding competition within category?

### 4.3 Common down-marks

- Portfolio reduces to single-NPV rank (down-mark to at
  most 55) — de-funds Responsible-AI-operations and
  Core-platform systematically.
- No category ceilings (down-mark to at most 70).
- No criteria beyond NPV named (down-mark to at most 65).
- No review cadence (down-mark to at most 70).
- Categories renamed quarterly to preserve project-team
  budget (down-mark to at most 60) — this is the failure
  mode explicit categorisation is designed to prevent.
- CFO consents only to aggregate, not criteria (down-mark
  to at most 75).

---

## Dimension 5 — Board-oversight instrumentation (weight: 15%)

**What the grader is testing.** Is Board reporting a
dashboard from records outside management curation; are
deep-dive triggers published; is Board-committee AI
oversight scoped by substance and not by convenience;
does the design defend under a Caremark-line fiduciary-
duty inquiry?

### 5.1 Scoring bands

| Band | Description |
|---|---|
| **90–100** | AIGC (or equivalent) dashboard defined with named panels (portfolio composition, decision-authority activity, regulatory posture, incident record, audit posture, framework health). Each panel's data source is outside AI-programme management curation (CFO records, Internal Audit, CISO, HR). Delivered as data plus one-page commentary; the Board reads the data first. Deep-dive triggers enumerated (Critical incident, High/Critical audit finding, regulator notice, category drift, missed dashboard reporting, framework amendment with material impact). Board-committee AI-oversight scope split (Strategy / Audit / Risk). Cadence named (quarterly to committees, semi-annually to full Board via committee reports). |
| **75–89** | Dashboard exists with most panels defined. Deep-dive triggers named. Board-committee split defined. One or two data sources unclear. |
| **60–74** | Board reporting is described as "a report to the Board on AI" without enumerated panels or sources. Deep-dive triggers not named. |
| **40–59** | Board reporting is a narrative from the CTO or CIO. |
| **0–39** | No Board-oversight design; Board is briefed ad hoc. |

### 5.2 Grader questions

- Can the grader trace one data point per dashboard panel
  back to a source record outside management curation?
- What triggers a deep dive without the Board Chair's
  discretion?
- Does the design survive a Caremark-line inquiry?
- What does the Board Strategy Committee own; what does
  the Board Audit Committee own; what does the Board Risk
  Committee (or its equivalent) own?
- What is the cadence, and what escalates outside cadence?

### 5.3 Common down-marks

- Narrative-only Board briefing (down-mark to at most 55) —
  this is the failure mode Board-instrumentation is
  designed to prevent.
- Panels defined but sources are AI-programme management
  (down-mark to at most 65) — the report becomes management's
  presentation of itself.
- No deep-dive triggers (down-mark to at most 65) —
  discretion-only convocation never happens for the
  difficult topics.
- All AI oversight in one Board committee (down-mark to
  at most 70).
- Cadence undefined (down-mark to at most 75).

---

## Dimension 6 — Compliance-and-audit by-product posture (weight: 15%)

**What the grader is testing.** Is compliance a by-product
of the ordinary workflow, not a retroactive project; are
regulatory obligations mapped to workflow steps; is
Internal Audit's programme designed against the archives
the ordinary workflow generates; does external-audit
readiness require zero additional data-gathering?

### 6.1 Scoring bands

| Band | Description |
|---|---|
| **90–100** | Regulatory-obligation register defined: for each applicable regulation (EU AI Act, NIST AI RMF, ISO/IEC 42001, sector-specific), obligations enumerated and each mapped to a workflow step that produces the evidence. New obligations enter the register before their effective date. Every workflow producing a governance artifact produces it in audit-retrievable form (named submitter, reviewers, decision, conditions, dissent). Retention, access control, chain of custody named. Internal Audit maintains a rolling three-year AI-audit programme covering framework adherence, register completeness, portfolio integrity, dashboard provenance, incident response, RACI adherence. External audit served from the same archives; no separate "audit preparation" programme. |
| **75–89** | Register defined; obligations mostly mapped. Evidence-by-workflow explicit for most artifact types. Internal Audit programme named. External-audit posture defined. |
| **60–74** | Register described but mapping is prose. Evidence handling is inconsistent. Internal Audit runs a periodic AI review, not a rolling programme. External audit triggers a data-gathering exercise. |
| **40–59** | Compliance is described as intention. Evidence exists in project archives but has no framework-level discipline. |
| **0–39** | No compliance-and-audit design. Audits trigger project-mode responses. |

### 6.2 Grader questions

- Can the grader pick a random applicable regulation,
  identify an obligation, and trace it to a workflow step
  that generates evidence?
- Is evidence generated in the ordinary workflow, or
  assembled after audit demand?
- What is the Internal Audit programme's rolling cycle?
- If a regulator serves an audit notice today, what is
  the target time to serve the audit from the existing
  archive?
- Where is the retention policy?

### 6.3 Common down-marks

- Compliance as project (down-mark to at most 55) — the
  failure mode the by-product posture is designed to
  prevent.
- Register named but not mapped to workflow steps
  (down-mark to at most 65) — this is compliance-as-slogan.
- Internal Audit runs periodic reviews, not a rolling
  programme (down-mark to at most 70).
- External audit triggers a data-gathering exercise
  (down-mark to at most 65).
- Retention undefined or inconsistent (down-mark to at
  most 70).
- No archive access rules for external audit (down-mark
  to at most 75).

---

## Dimension weights and aggregation

| # | Dimension | Weight |
|---|---|---|
| 1 | Scope-definition defensibility | 20% |
| 2 | Decision-authority enforceability (RACI) | 20% |
| 3 | Governance-body topology | 15% |
| 4 | Investment-portfolio model | 15% |
| 5 | Board-oversight instrumentation | 15% |
| 6 | Compliance-and-audit by-product | 15% |
| **Total** | | **100%** |

**Aggregation.** Weighted sum of the six dimension scores.

**Overall bands.**

| Overall score | Interpretation |
|---|---|
| **90–100** | Ready for Board Strategy Committee ratification as-is. |
| **80–89** | Ready with minor edits; a senior architect would sign it out after one review pass. |
| **70–79** | Solid draft; a second review pass required. Named gaps but no structural failures. |
| **60–69** | Directional but structurally incomplete. Requires a rewrite of one or two dimensions. |
| **Below 60** | Fundamentally not ready. Rework required. |

**Non-passing thresholds.** A submission scoring below 60
on either Dimension 1 (scope) or Dimension 2 (RACI) fails
the assessment overall, regardless of scores on the other
dimensions. A senior architect who cannot show either "what
is in scope" or "who decides" has not demonstrated the
level.

---

## Reading the rubric alongside the framework

The rubric is not a scoring key with a single right answer.
It is a set of properties the framework must defend. A
submission that structures its framework differently but
defends the same properties can score at the top band.
Examples of legitimate variation:

- **A submission with eight decision classes rather than
  ten** can score full marks on Dimension 2 if the class
  set covers the ten reference concerns without collapsing
  natural authority boundaries.
- **A submission that adds a Chief AI Officer role** can
  score full marks on Dimension 3 if the CAIO's authority
  is scoped so it does not collapse the operational bodies,
  and if the personality-dependency risk (framework
  §12) is defended in the successor register.
- **A submission with four portfolio categories rather than
  five** can score full marks on Dimension 4 if the four
  categories cover the argued concerns and the CFO consents
  to the criteria weightings.
- **A submission with the Board Strategy Committee as sole
  Board-level oversight (no separate Board Audit / Risk
  Committee involvement)** cannot score above 75 on
  Dimension 5, because concentrating AI oversight in one
  Board committee is the failure mode Dimension 5 is
  designed to detect. Where the submission argues that
  Halcyon does not have a separate BAC or BRC (e.g., a
  smaller subsidiary), the grader accepts the argument
  provided the composition of the Strategy Committee
  covers the audit and risk substance.

Submissions that reproduce the reference framework verbatim
without argued adaptation to the specific scenario score
lower than submissions that adapt sensibly.

---

## Grader notes

### What the rubric is not

- **It is not a scoring key.** A submission that structures
  its framework differently but defends the same properties
  can score at the top band.
- **It is not a checklist for the reference framework.** A
  submission that reproduces the reference framework
  verbatim, without argued adaptation, scores lower than
  one that adapts sensibly.
- **It is not a preference for length.** Concise frameworks
  that answer the six dimensions score above verbose
  frameworks that hedge on all six.

### Reviewer discipline

- Grade against the rubric, not against personal preference
  for a specific governance-methodology (COBIT, NIST AI RMF,
  ISO/IEC 38500). The rubric asks whether the properties
  are defended, not which framework was cited.
- Distinguish "I would have done this differently" from
  "this is wrong". The former is a note; the latter is a
  down-mark.
- Where a submission adapts a reference component to its
  scenario, credit the adaptation.
- Where a submission omits a component the scenario would
  require (for example, a regulatory-obligation register
  at a company with EU AI Act exposure), down-mark rather
  than making the case for the learner.
- Weight the two non-passing thresholds seriously: a
  submission that solves the four "second-tier" dimensions
  brilliantly but leaves scope or RACI unspecified is not
  a passing submission.

### What to write in the review

- One paragraph per dimension: score, one sentence
  explaining the score, one to two sentences on the
  strongest and weakest points.
- Explicit call-out of any non-passing threshold hit.
- Named recommended next-review items in priority order.
- Do not rewrite the learner's framework in the review;
  the review is grader feedback, not co-authoring.

### Common integration failures to look for

Beyond the per-dimension down-marks, three integration
failures recur across submissions:

- **Scope tests inconsistent with RACI classes.** The
  submission's scope tests admit systems that the RACI
  has no class for; the mismatch is left unaddressed. This
  is a Dimension 1 and Dimension 2 joint failure.
- **Bodies preserved but interfaces absent.** The
  submission names the four operational bodies but does
  not enumerate ARB↔RAIB, ARB↔IPB, RAIB↔IPB, EVRB↔RAIB
  interfaces; the "no decision falls between bodies"
  guarantee is unenforced. This is a Dimension 3 failure
  that also erodes Dimension 2.
- **Portfolio-model criteria present but Board-oversight
  panel undefined.** The submission has categories and
  criteria but the Board dashboard does not report against
  them, so the CFO's argued composition is invisible to
  the Board. This is a Dimension 4 and Dimension 5 joint
  failure.

Where you detect an integration failure, name the
dimensions it touches and down-mark each accordingly.

---

## Version

**Version**: 1.0
**Status**: Reference rubric
**Owner**: Senior Architect curriculum track
