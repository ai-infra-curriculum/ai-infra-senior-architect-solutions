# Halcyon AI Innovation Programme — Reference Design

> Operational companion to `SOLUTION.md`. This artifact is the
> programme design a senior architect would submit to Halcyon's
> Board Strategy Committee for ratification. It restates the
> reasoning from SOLUTION in the form a Portfolio Board member
> would actually work from.

**Version**: 1.0
**Status**: Reference programme design
**Owner**: Group CTO office (programme owner); Innovation Portfolio Board (governance)
**Review cadence**: Annual thesis review; semi-annual portfolio deep-dive

---

## 1. Programme thesis

Halcyon competes in a market where mechanical differentiation is
necessary but no longer sufficient. Over the next decade the
defensible margin in industrial automation will belong to vendors
whose products embed better perception, better control, and
better on-device learning — not vendors with better AI in the
cloud. The AI Innovation Programme's role is to give Halcyon's
product organisation the option to place those bets on time, not
the responsibility to place them itself.

### What the thesis excludes (deliberately)

- **Consumer-AI applications.** Halcyon does not compete for
  consumer attention. Consumer-AI benchmarks are not on the
  programme's scoreboard.
- **Cloud-only AI services.** The margin available to Halcyon
  from cloud-hosted AI services is captured through the CIO
  organisation's applied-AI portfolio (see Section 2 of the
  programme's coverage map). The Innovation Programme's
  differentiation is on-device and control-loop.
- **Foundation-model pre-training as an end in itself.** The
  programme uses foundation models where they earn their keep
  as capability primitives; it does not fund pre-training runs
  whose only defence is "so Halcyon has one".
- **General-purpose academic research.** Halcyon funds research
  Halcyon has a plausible use for. The programme does not fund
  research whose value proposition is "advances the field".
  That work belongs in universities, and Halcyon supports it
  through the partnership templates in Section 4 rather than
  through the direct portfolio.

### Thesis review

The thesis is reviewed by the Innovation Portfolio Board and
ratified by the Board Strategy Committee annually. Between
reviews, the thesis is treated as fixed. Requests to change the
thesis mid-year are handled by the Board Strategy Committee as
a governance item, not by the Portfolio Board as a tactical
adjustment.

---

## 2. Portfolio structure

### 2.1 Three horizons

The programme organises its portfolio on three horizons adapted
from the Baghai/Coley/White three-horizon frame to R&D:

| Horizon | Meaning | Success criterion | Target share |
|---|---|---|---|
| **H1 — Near-term product enablement** | Applied research the shipping product organisation has committed to consume, typically within 12 months | Transferred, in production, measured | 40% |
| **H2 — Adjacent-market options** | Research producing a capability Halcyon could use in a plausible adjacent product line within ~3 years, contingent on product decision | Transfer-ready capability characterised against a receiving-team scenario, with a documented product-line hypothesis | 40% |
| **H3 — Frontier bets and defensive scans** | Research on emerging capabilities whose usefulness to Halcyon is genuinely uncertain but whose absence would be strategically costly if the capability matters | Written verdict (pursue / park / abandon) with argument | 20% |

Shares are targets, not caps at the top or floors at the bottom.
The operational rule is that H3 spend is capped at the ratified
target; H1 is floored. H2 absorbs the variance.

### 2.2 Coverage map

The programme's active coverage is presented to the Board
Strategy Committee as a coverage map — a two-dimensional grid of
*capability class* against *product-line applicability*. The
map is maintained by the Portfolio Board and reviewed each
quarter. Cells with active projects are colour-coded by horizon;
empty cells surface consciously — the Board is asked whether
absence is deliberate coverage refusal or coverage drift.

Illustrative capability classes on the map (not exhaustive):

- Perception (vision, vibration, thermal, acoustic)
- Control (drive-loop tuning, model-predictive control,
  physics-informed learning)
- On-device inference (model compression, compiler work,
  next-generation accelerator support)
- On-device learning (continual-learning schemes, federated
  approaches at the factory edge)
- Simulation and digital twins for design and validation
- Foundation-model applications inside engineering workflows
  (design assistance, code, documentation, service literature)
- Safety and formal-methods integration

Illustrative product-line columns:

- Vision-inspection products
- Servo and induction drives
- Vibration and process sensing
- Programmable controllers and factory-floor middleware
- Grid-scale storage control

Cells the programme deliberately does not cover today are
documented as *out-of-scope-by-thesis* with the argument. This is
what "the programme knows what it does not do" looks like on the
wall.

### 2.3 Non-portfolio classes

Two classes of AI-adjacent activity at Halcyon are *not* part of
this programme by design:

- **Applied AI in shipping products.** Owned by the product
  business units and their own engineering roadmap. The
  programme is the *option supplier* to these teams via
  transfer contracts.
- **Applied AI in operations (demand forecasting, supplier
  risk, warranty analytics).** Owned by the CIO organisation
  under standard line-of-business ROI governance.

Both are noted so the Board and the CFO have a clear view of
what is being reported where, and so the Innovation Programme
scoreboard cannot be inflated by pulling operations metrics
into it.

---

## 3. Emerging-technology evaluation protocol

The programme evaluates emerging technologies through a written
protocol adapted from the DARPA Heilmeier Catechism.

### 3.1 The nine-question response

Every candidate technology is entered into the evaluation register
with a one-page written response to:

1. What is the capability, in Halcyon's own vocabulary?
2. How is the corresponding problem addressed today at Halcyon,
   and what are the limits?
3. What is new about this approach — capability, or packaging?
4. Who at Halcyon would use it, at a role level?
5. What is the difference in outcome if we adopt it, at what
   scale?
6. What are the risks and the payoffs?
7. What does a real evaluation cost — compute, headcount,
   calendar, dependencies?
8. How long does the evaluation take before we can call it?
9. What are the checkpoints and what does declared success or
   failure look like?

### 3.2 Verdicts

Each evaluation produces one of four verdicts, ratified by the
Portfolio Board:

| Verdict | Meaning | Follow-on |
|---|---|---|
| **Enter H1** | Product organisation committed | Transfer contract initiated at project entry |
| **Enter H2 / H3** | Portfolio funds a bounded project | G0 approved, gate plan set, stopping criterion set |
| **Park** | No project funded; defensive-scan register entry | Reviewed annually against thesis |
| **Do not pursue** | Written argument on file; cannot re-enter under the same argument for 12 months | Refresh window governs re-entry |

### 3.3 Archive

Evaluation responses and verdicts are archived in the programme
knowledge base. The archive is a first-class artifact — losing
it means re-doing evaluations the programme has already reached
a defended answer on. The archive is available to Portfolio
Board members, Board Strategy Committee members, and, on
request, Halcyon Internal Audit.

### 3.4 Refresh cadence

The parked / defensive-scan register is reviewed annually. A
parked technology can re-enter active evaluation if:

- The underlying capability has materially changed (new results
  in the field, new benchmark, new hardware).
- Halcyon's business context has materially changed (new
  product-line commitment, new competitor move, new customer
  requirement).
- The original evaluation's assumptions have been shown to be
  wrong.

Re-entries are logged with the reason for re-entry — that log
is where the programme learns about its own blind spots.

---

## 4. Partnership model

### 4.1 Templates

The programme uses four structural partnership templates:

**Template A — University research contract.** Time-boxed
research contract with a named PI at a named institution.
Contains: scope statement, deliverables, review milestones,
commercial IP terms, publication window for filing review,
named successor PI (or fallback path if none), notice and
wind-down clauses.

**Template B — National-lab / consortium participation.**
Membership or participation contract in a consortium (topically-
appropriate research centre, industry consortium, public
research programme). Contains: value flow both ways, Halcyon
contribution (money, engineer time, in-kind), governance seat if
any, IP background, and exit conditions.

**Template C — Start-up engagement.** Structured as a
capability-tracking relationship rather than an investment.
Contains: capability watch list membership, Heilmeier evaluation
of specific start-ups before commercial engagement, and one of
three outcomes (no engagement, commercial pilot on standard
procurement terms, corporate-development referral). Investment
is not this programme's function.

**Template D — Talent partnership.** Structured internship,
industrial-PhD, and visiting-researcher instruments.
Explicitly scored on talent flow (hires, retention, capability
transfer into Halcyon), with research output as a secondary
outcome. A talent partnership scored on publications will be
run to publish, not to hire, and the scoreboard reflects that
choice.

### 4.2 Contracting posture

Halcyon's default posture on partnership contracting:

- **Foreground IP** created substantially with Halcyon funding
  on Halcyon-specific problems belongs to Halcyon, with a
  royalty-free non-exclusive licence back to the academic partner
  for non-commercial research and publication.
- **Background IP** each side brings remains that side's; each
  side licences background IP to the other only as narrowly as
  needed to execute the contracted work.
- **Publication** is permitted after a review window (default 30
  days, extendable to 60 for complex filings) for patent-filing
  and trade-secret review.
- **Data flowing from Halcyon** to the partner is governed by
  Halcyon's data-classification policy and the applicable data-
  protection law at rest inside the partner (GDPR / LGPD / DPDP
  / US state privacy laws / applicable Chinese and Korean laws
  as scope requires). Data-handling requirements are Annex A of
  every partnership contract.
- **Confidentiality** attaches to specifically-marked material,
  not to the relationship as a whole. Blanket confidentiality
  is refused because it becomes unenforceable and undermines
  publication permissions.

### 4.3 Exit provisions

Every partnership contract states:

- **Expiry date.** The default term is 12 to 36 months depending
  on template; open-ended relationships are refused because they
  cannot be forecast.
- **Notice period** for early termination by either side.
- **Wind-down obligations.** Data return or destruction, IP
  settlement, publication completion, service transitions.
- **Named successor logic** for Template A. If the PI leaves
  mid-contract, either a named successor takes over or the
  contract enters wind-down within a defined window.

### 4.4 Portfolio Board review

Partnerships above a threshold (set by the Board Strategy
Committee — reference default: contracts over €500K committed
annual value, contracts with named strategic partners, or
contracts with unusual IP terms) require Portfolio Board
approval as a standing agenda item. Partnerships below the
threshold are approved by the AI Lab Director under the
programme's delegated authority and reported to the Board in
batch.

---

## 5. Intellectual property strategy

### 5.1 Filing decision — argued, not counted

Every invention disclosure that reaches a filing decision is
accompanied by a written strategic argument on one page.

**Required argument content:**

1. **Defensive perimeter.** Which product surface does this
   filing protect, and against which competitor position or
   freedom-to-operate challenge?
2. **Offensive value.** Cross-licensing pool, standards-essential
   position, competitive-blocking case — or "none, defensive
   only" as an explicit answer.
3. **Trade-secret alternative.** Would this invention be better
   held as trade secret (inspection reveals nothing, replication
   is hard, product-life relative to patent-life)? If yes and
   the filing proceeds anyway, the argument states why.
4. **Cost and jurisdiction.** Which jurisdictions are the
   commercial rationale, and what is the expected filing and
   maintenance cost over the patent life?
5. **Owner.** Who at Halcyon is the accountable business owner
   of this filing? (Role, not name.)

**Batch review cadence.** Filing decisions are batched to a
quarterly Portfolio Board review, so the Board sees the shape
of the filing portfolio and can catch drift (all-defensive, all-
one-product-line, all-one-inventor).

### 5.2 Freedom-to-operate

Freedom-to-operate landscape reviews are maintained per product
line at a stated cadence — annual for mature product lines,
semi-annual for lines undergoing significant AI adoption.
Findings feed the portfolio:

- A hard FTO constraint may create an H1 project (design
  around) or a licensing decision.
- A soft FTO signal may create an H3 defensive-scan entry.
- A cluster of related third-party filings triggers a
  competitive-intelligence brief to the Portfolio Board.

### 5.3 Standards-essential-patent posture

Where Halcyon holds or applies for patents that could become
standards-essential in a body Halcyon participates in (ISO/IEC,
IEEE, OPC Foundation, and topically-relevant automation
standards), the default posture is FRAND (Fair, Reasonable, and
Non-Discriminatory) declaration under the relevant body's IPR
policy, unless the Portfolio Board and Legal expressly decide
otherwise on a specific patent basis.

### 5.4 Open-source posture

Where the programme's work touches open-source software:

- **Consume** open-source dependencies through Halcyon's existing
  software-licence compliance process. This programme does not
  redesign that process.
- **Contribute back** where the strategic argument is that the
  contribution accelerates a capability Halcyon wants
  standardised — for example, an evaluation harness the industry
  can share. Contributions require the same one-page
  strategic argument as a filing decision, and are approved by
  the Portfolio Board.
- **Do not open-source** the specific product-differentiating
  capability without an explicit Board decision.
- **Do not open-source** any surface where the current freedom-
  to-operate analysis is out of date.

### 5.5 Metric refusal

Patent count is not a headline programme metric (see Section
7). Patents filed and patents granted appear in hygiene
reporting; they are not the scoreboard. The programme protects
this refusal explicitly because filing-count metrics have a
well-documented history of producing worse patents faster.

---

## 6. Stage-gated project management

### 6.1 Gates

Every project runs on four gates:

| Gate | Trigger | Deliverable | Default if silent |
|---|---|---|---|
| **G0 — Entry** | Heilmeier response accepted | Budget committed to G1 | Do not enter |
| **G1 — Concept validation** | 6–12 weeks post-G0 | Concept report; go/no-go recommendation | Stop |
| **G2 — Capability build** | 3–9 months post-G1 | Characterisation report; receiving-team review; transfer plan or H3 continuation argument | Stop |
| **G3 — Transfer or park** | Transfer contract accepted, or park-with-review approved | Signed transfer contract or defensive-scan register entry | Stop |

**"Default if silent" is the enforcement mechanism.** Innovation
programmes drift because gates default to *continue*: no one
said stop, so the project rolls into the next quarter. The
reference programme defaults each gate to *stop*. Continuing is
an active decision by the Portfolio Board, recorded.

### 6.2 Gate deliverables

Gate deliverables are stored in the programme knowledge base:

- **G0 packet.** Heilmeier response, horizon assignment,
  Portfolio Board decision, stopping criterion.
- **G1 packet.** Concept report, project lead recommendation,
  Portfolio Board decision.
- **G2 packet.** Characterisation report, receiving-team review,
  transfer plan (H1/H2) or H3 continuation argument, Portfolio
  Board decision.
- **G3 packet.** Signed transfer contract (H1/H2) or defensive-
  scan register entry (H3), Portfolio Board record.

### 6.3 Cycle-time hygiene

Gate cycle time is reported semi-annually as a hygiene metric
(see Section 7.2). Projects that stall at a gate for more than
one review cycle without a Portfolio Board decision to hold
default to stop.

---

## 7. Metrics scorecard

### 7.1 Headline metrics (quarterly to Board Strategy Committee)

| Metric | Definition | Owner of the reading |
|---|---|---|
| **Transfer volume** | Artifacts transferred to a named receiving team, plus receiving-team estimated value | Receiving teams |
| **Transfer acceptance rate** | Transfers offered / transfers accepted at G3 without material change | Receiving teams and programme jointly |
| **Option value created** | Verdicts produced in the period (enter / park / do not pursue), and count of parked-with-review entries | Portfolio Board |
| **Capability built** | Data assets, evaluation harnesses, tooling, methodologies accumulated across projects | Programme (stock, not flow) |
| **Horizon adherence** | Actual spend by horizon versus target share | Portfolio Board and CFO |

### 7.2 Hygiene metrics (semi-annually)

- Gate cycle time (median, distribution).
- Gate-decision distribution (approve / redirect / stop) by
  gate and horizon.
- Portfolio ageing — median time a project has been open, by
  horizon.
- Talent flow — hires from partnerships, internal transfers
  into and out of the programme, attrition.
- Publication count, patent-filing count, patent-grant count —
  reported as hygiene, not headline.

### 7.3 Metrics deliberately not counted at the headline

- **PoC count.** Trivially gameable.
- **Papers published or citations.** Gameable, drifts from
  business value, and creates a perverse incentive.
- **Patents filed per scientist per year.** See Section 5.5.
- **Media mentions and speaking invitations.** Side-effect of
  a good programme, not the objective.

### 7.4 Goodhart protection

- The receiving team estimates value, not the Lab. The Lab
  cannot inflate its own scoreboard.
- The transfer acceptance rate is reported both ways: low
  acceptance is diagnostic and the Portfolio Board looks at
  both sides.
- The Board Strategy Committee reviews the scorecard
  definition annually. Definition changes are a governance
  artifact, not a Lab decision.

---

## 8. Transfer contract template

The transfer contract is the definition of done for horizon-1
and graduating horizon-2 projects. Every transfer uses the
same template. The template is version-controlled; template
changes require Portfolio Board approval.

### 8.1 Contract sections

1. **Parties.** Named R&D team lead; named receiving team lead;
   Portfolio Board representative for record.
2. **Artifact.** Named artifact — model, training pipeline,
   evaluation harness, control scheme, compiler pass, documented
   methodology. Version identifier. Hash of the delivered
   artifact where applicable.
3. **Characterisation.** Datasets used, measurements taken,
   confidence bounds, known failure modes. This is the Project
   403 evidence bundle for artifacts intended to ship into
   production; it is generated during R&D so the transfer
   boundary is not the evidence bottleneck.
4. **Interface.** Named integration point in the receiving
   team's product or platform. Function signature, service
   contract, runtime constraints, deployment target.
5. **Residual risk.** Named risks the R&D team could not fully
   characterise. Receiving-team plan for owning them post-
   transfer, or explicit acceptance.
6. **Support obligation.** Reference default: 90 days of first-
   call support with named on-call engineer, followed by 90
   days of bug-triage relationship. Longer or shorter windows
   defensible on a per-artifact basis.
7. **Transfer test.** Defined test the receiving team runs at
   handover.
8. **Transfer date.** Date at which the receiving team accepts
   or refuses.
9. **Signatures.** R&D team lead; receiving team lead;
   Portfolio Board representative for record.

### 8.2 Refusal

The receiving team may refuse a transfer at the transfer date.
Refusal is recorded in the transfer register with the receiving-
team-stated reason. The Portfolio Board reviews refusals at the
next monthly meeting; patterns of refusal (from the same
receiving team, or on the same class of artifact) are treated
as portfolio-level signals, not as individual-project
disappointments.

### 8.3 Post-transfer

Post-transfer, the artifact is on the receiving team's roadmap.
The programme's involvement is limited to the support obligation
and, on the receiving team's request, defect fixes to work the
programme delivered. Additional feature work is not the
programme's job unless a new transfer contract is signed.

---

## 9. Governance

The Innovation Portfolio Board is chartered in
`../governance/innovation-portfolio-charter.md`. Summary of
authority and cadence:

- **Composition.** Group CTO or delegate (chair); Chief Product
  Officer or delegate; Chief Financial Officer or delegate;
  General Counsel or delegate; AI Lab Director; product-BU
  engineering leader on a rotating seat; at least two external
  members (one industry, one academic).
- **Binding authority.** Portfolio entries and exits, gate
  decisions G0–G3, budget allocation across horizons within
  the Board Strategy Committee envelope, partnership templates
  and specific partnerships above the delegated threshold, IP
  filing arguments in batch.
- **Advisory authority.** Individual project technical
  direction; receiving-team readiness; Responsible AI evidence
  (which sits under Project 403's governance).
- **Cadence.** Monthly standing meeting; quarterly review with
  Board Strategy Committee; annual thesis review.
- **Dissent recording.** Dissent recorded explicitly. Above a
  threshold, escalated to the Board Strategy Committee.

Escalation to the Board Strategy Committee happens on:

- Any change to the thesis.
- Any change to horizon-share targets.
- Any partnership above the reference partnership-value
  threshold or with unusual IP terms.
- Any project stopped after G3 with material sunk cost.
- Any Portfolio Board dissent above the recorded threshold.

Escalation to the Board Audit Committee happens on:

- Programme spend variance above threshold.
- Programme-level IP or FTO risk.
- Any external inquiry (regulator, standards body, litigation)
  naming programme output.

---

## 10. Roadmap

### Phase 0 (Months 0–3) — Thesis and portfolio inventory

- Draft and ratify the programme thesis.
- Charter and seat the Innovation Portfolio Board.
- Inventory existing AI Lab projects against the horizon
  model. Classify provisionally.
- Identify projects that must be under transfer contract in
  Phase 1 (three reference projects, drawn from the existing
  horizon-1 candidates).
- Publish the Heilmeier evaluation protocol and the transfer
  contract template.

**Reversibility.** Highly reversible. Existing work continues
under existing terms. Nothing new enters under new governance
yet.

### Phase 1 (Months 3–9) — Governance and evaluation live

- Portfolio Board authoritative for all new project entries.
- Heilmeier protocol used for every new candidate.
- First three horizon-1 projects transferred under signed
  transfer contracts. This is the proof of the machinery, not
  a metric.
- Stage-gate cadence live for all new projects.
- Partnership templates published; new partnerships use the
  templates.
- IP argument process live for new filings.

**Reversibility.** Medium. New machinery is doing new work, but
existing work has not yet been reclassified.

### Phase 2 (Months 9–18) — Backfill and steady state

- Existing projects reclassified under the horizon model.
- Existing projects that reach a gate under the new cadence
  either transfer, redirect, or close. Projects with no
  receiving-team hypothesis and no horizon-3 verdict argument
  close.
- Metrics scorecard reported quarterly.
- First round of Portfolio Board redirection of horizon
  balance if needed.

**Reversibility.** Low per project. Closing an in-flight project
is expensive in trust; the reference programme front-loads the
honesty.

### Phase 3 (Months 18–24) — External review and thesis refresh

- First external review of the programme (comparators from
  public peer disclosures, national research programme
  benchmarks, ISO 56002-adjacent management-system review).
- Thesis reviewed against results.
- Board Strategy Committee approves the next horizon-share
  allocation and any thesis update.

### Beyond Month 24 — Steady state

Annual thesis review; semi-annual portfolio deep-dive;
continuous stage-gated portfolio management. There is no Phase
4. The programme is now steady state, and steady state is the
point.

---

## 11. Risk register

Top ten programme-level risks, ordered by residual risk after
mitigation.

| # | Risk | Probability | Impact | Mitigation | Residual |
|---|---|---|---|---|---|
| 1 | **Transfer failure.** R&D artifacts do not land in product; programme drifts into a demo shop | High without controls | High | Transfer contract required for H1/H2 exit; receiving-team refusal recorded; acceptance-rate reported to Board | Medium |
| 2 | **Horizon drift (H3 grows).** Exploratory work quietly dominates because it is exciting and unaccountable | High | High | H3 capped, not floored; horizon-share reported quarterly; Board reset annual | Medium |
| 3 | **FOMO capture.** Programme chases every emerging-tech announcement | High without controls | Medium | Heilmeier protocol gates all entries; verdicts archived; do-not-pursue argument holds for 12 months | Low |
| 4 | **Talent flight.** Key R&D engineers leave; programme institutional memory lost | Medium | High | Written thesis; written Heilmeier verdicts; written transfer contracts; role-not-name governance; talent-partnership pipeline | Medium |
| 5 | **Partnership dependency.** A partnership programme depends on a single named PI or Halcyon champion | Medium | Medium | Named-successor clauses; exit provisions; batch review of partnerships at Portfolio Board | Low |
| 6 | **IP leakage through partnership.** Foreground IP created with Halcyon funding leaves under the wrong contractual posture | Medium | High | Standard IP terms in templates; General Counsel review of specific-partnership deviations; publication review window | Low |
| 7 | **IP filing bloat.** Filings proliferate on count-based incentives without strategic argument | Medium | Medium | Written argument required per filing; batch review; count not headlined | Low |
| 8 | **Regulatory drift into R&D.** New obligations (EU AI Act phase-in, ISO 42005) reach R&D unexpectedly | Medium | Medium | Transfer contract inherits Project 403 evidence bundle; programme legal watch on standards drift | Low |
| 9 | **Portfolio Board capture.** Board defaults to approving what the Lab proposes | Medium | High | External members; dissent recording; Board Strategy Committee escalation on dissent above threshold | Medium |
| 10 | **Innovation theatre.** Programme output is media presence, not artifacts | Medium | High | Metrics scorecard headlines transfer volume; media metrics not counted at headline; annual external review | Low |

**Enforcement drift** (the meta-risk that any of the above
controls silently degrades) is monitored through the annual
external review; degradation shows up when the review compares
year-N control adherence to year-N-minus-1.

---

## 12. Interfaces to adjacent programmes

- **Project 401 (Enterprise Transformation).** The Innovation
  Programme is one workstream in the transformation portfolio.
  Sizing and thesis are consistent with the transformation
  strategy; funding sits under the transformation envelope
  where applicable.
- **Project 402 (Global AI Platform).** Transfer contracts
  ship onto the platform architected in Project 402. Where
  R&D produces a shipping artifact, the platform's deployment,
  monitoring, and governance controls apply.
- **Project 403 (Responsible AI Framework).** Transfer
  contracts inherit the Project 403 evidence bundle at the
  transfer boundary. R&D that intends to ship into a high-risk
  use case produces the evidence during characterisation.
- **Project 406 (Enterprise Governance).** Portfolio Board
  authority is scoped consistently with the enterprise
  governance model. Escalation to the Board Strategy Committee
  and Audit Committee runs through Project 406's escalation
  paths.

---

## 13. What this artifact is not

- **A project catalogue.** Specific projects are portfolio
  content, not programme design. The programme design is the
  machinery; a project catalogue changes quarterly.
- **A hiring plan.** Sizing and topology are informed by this
  design; the specific hiring plan is an HR artifact.
- **A compute-procurement plan.** The programme names the
  categories of infrastructure it requires; vendor and sizing
  decisions are a platform and procurement artifact informed
  by this programme (see FOLLOWUP-COMPUTE-01 in `SOLUTION.md`).
- **A financial forecast.** The horizon shares and gate cadence
  give the CFO the structure to build a forecast; the forecast
  itself is a finance artifact.

---

## 14. Version and change control

**Version**: 1.0
**Status**: Reference programme design
**Owner**: Group CTO office (programme); Innovation Portfolio Board (governance)
**Change control**: Programme thesis changes require Board Strategy
Committee approval. Portfolio-structure changes (horizons, gate
cadence, transfer template, metrics scorecard) require Portfolio
Board approval with Board Strategy Committee notification.
Operational changes (evaluation protocol wording, partnership
template clauses that do not affect IP terms, hygiene metric
definitions) are Portfolio Board delegated authority.
