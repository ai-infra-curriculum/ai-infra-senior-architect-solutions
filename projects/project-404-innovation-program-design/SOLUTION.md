# SOLUTION — AI Innovation Programme Design

> Read this *after* you have drafted your own AI innovation programme.
> This is the reasoning the reference design is defending, not a scoring
> key. A different programme that defends the same properties is a valid
> answer.

## 1. Solution overview

A senior architect answers three questions in an AI innovation
programme design review:

1. **What bets is the programme placing, and why those?** — the
   portfolio question. Every downstream failure of an innovation
   programme traces back to a portfolio that is a wish list rather
   than a defended thesis. If the programme cannot say what it is
   *not* funding, it is not a portfolio.
2. **What happens between the demo and the shipping product?** —
   the transfer question. R&D that never leaves the Lab is worse
   than no R&D at all: it consumes runway, occupies senior
   engineers, and quietly demoralises the product organisation
   that keeps receiving impressive slide decks and no artifacts.
3. **How does the programme measure itself without lying to
   itself?** — the metrics question. Publications, patents-filed,
   and PoC counts are trivially gameable and drift from business
   value within a quarter. The reference programme instruments
   itself against value transferred and options created, and
   deliberately refuses to headline the easily-gamed metrics.

The reference target state is a **three-horizon, thesis-anchored
AI R&D portfolio** governed by an Innovation Portfolio Board with
scoped decision rights, funded on a stage-gated basis, evaluated
against a written protocol adapted from the DARPA Heilmeier
Catechism, and instrumented against a small scorecard whose
top-line metric is *value transferred to a receiving team*.

The **key trade-off accepted** is the same one Halcyon's product
organisation would recognise from its own hardware R&D: an honest
innovation programme kills more projects than it graduates, tells
the Board so, and defends the ratio. A programme that ships every
project it starts is a programme that stopped taking real bets.

## 2. Worked answer (the reference programme)

### 2.1 The programme thesis (three sentences, then arguments)

The reference programme opens with a written thesis at three
sentences, no more:

> *Halcyon competes in a market where mechanical differentiation
> is necessary but no longer sufficient. Over the next decade the
> defensible margin in industrial automation will belong to
> vendors whose products embed better perception, better control,
> and better on-device learning — not vendors with better AI in
> the cloud. The AI Innovation Programme's role is to give
> Halcyon's product organisation the option to place those bets
> on time, not the responsibility to place them itself.*

That thesis does three things a wish-list cannot:

- It states which market the programme is playing in
  (industrial automation, on-device, perception+control+learning)
  and by exclusion which markets it is not chasing (consumer AI
  applications, cloud-only AI services, generic foundation-model
  training).
- It states who the programme is *for* (Halcyon's product
  organisation) and what it owes them (options placed on time).
  This is the transfer contract in one sentence.
- It gives the CFO and the Board Strategy Committee a criterion
  against which to test proposed spending: does this project
  produce an option Halcyon's product organisation will plausibly
  want to exercise, or does it produce a paper?

**Why a written thesis and not a mission statement.** Mission
statements accumulate consensus adjectives ("responsible,
innovative, world-class, customer-centric") and enforce nothing.
A thesis is falsifiable: it can be argued with, and the argument
is where the portfolio decisions get made. If the Board wants to
change the programme, the thesis is what changes; the machinery
does not.

### 2.2 The horizon model — three horizons, budgeted, defended

The reference programme organises the portfolio on a three-horizon
model. The horizons are a well-known frame (Baghai/Coley/White,
"The Alchemy of Growth", 1999) adapted to R&D rather than to
business unit portfolios.

- **Horizon 1 — Near-term product enablement.** Applied research
  the shipping product organisation has committed to consume,
  usually inside twelve months, and would fund itself if it were
  not a shared capability across business units. Examples of the
  *class* (not specific projects): drop-in replacement of a
  legacy vision model with a domain-adapted variant, quality-
  inspection foundation-model fine-tuning against Halcyon's own
  labelled data, evaluation harness for on-device model
  regression. Success criterion: transferred, in production,
  measured. **Target share of programme spend: 40%.**
- **Horizon 2 — Adjacent-market options.** Research that produces
  a capability Halcyon *could* use in a plausible adjacent
  product line inside three years, contingent on business
  decision. Examples of the class: physics-informed learning for
  drive-loop control on a new hardware platform, edge-inference
  compiler work targeting a next-generation accelerator, on-
  device continual-learning schemes. Success criterion: transfer-
  ready capability, characterised, with a documented product-
  line hypothesis. **Target share: 40%.**
- **Horizon 3 — Frontier bets and defensive scans.** Research on
  emerging capabilities whose usefulness to Halcyon is genuinely
  uncertain but whose absence would be a strategic embarrassment
  if the capability turned out to matter. Examples of the class:
  quantum simulation for materials work upstream of drive design,
  neuromorphic inference for very-low-power sensor edges, world-
  model / physical-AI approaches for control-loop training,
  formal-methods-plus-learning approaches for safety-critical
  loops. Success criterion: written verdict — pursue, park, or
  abandon — with argument. **Target share: 20%.**

**Why the 40/40/20 split.** The split is a reference default,
not a law. The rule the programme actually enforces is that
Horizon 3 is capped, not floored: a programme cannot let its
horizon-3 spend quietly grow to dominate ("just one more
exploration"), because that is the failure mode innovation
programmes are famous for and the mode a CFO cannot tell from
lab entertainment. The Board Strategy Committee resets the
horizon shares annually against thesis review.

**Why not more horizons.** Programmes that publish five, seven,
or nine horizons produce categorisation debates rather than
funding decisions. Three is enough to distinguish *committed*,
*optioned*, and *speculative*, and few enough that a Board member
can hold the split in their head.

### 2.3 Emerging-technology evaluation — the written protocol

Emerging capabilities enter the portfolio through a documented
evaluation protocol, not through vendor demos and not through
personal enthusiasm. The reference protocol adapts the DARPA
Heilmeier Catechism (nine questions attributed to George Heilmeier,
formerly DARPA Director) to Halcyon's context.

Every candidate technology gets a written response, one page or
less, to:

1. **What is the capability, in Halcyon's own vocabulary?** Not
   the vendor's marketing category — the phenomenon in terms
   Halcyon's engineers would use. If the answer requires a
   glossary, the capability is not yet ready for evaluation.
2. **How is the corresponding problem addressed today at Halcyon,
   and what are the limits?** The problem-side, not the tech-side.
   If the answer is "we don't have a problem here", the
   evaluation ends.
3. **What is new about this approach?** In particular: is the
   novelty in the *capability* or in the *marketing package*?
   Distinguish new physics from new packaging.
4. **Who at Halcyon would use it?** Named receiving team, at a
   role level. If no product organisation would use this even in
   principle, the technology may still be worth watching — that
   is a defensive scan — but it does not enter the active portfolio.
5. **What is the difference in outcome if we adopt it, at what
   scale?** A quantified expected effect on a Halcyon KPI, with
   the assumption stack.
6. **What are the risks and the payoffs?** Both sides. A no-risk
   pitch is a low-payoff pitch mis-labelled.
7. **What does it cost to run a real evaluation** — not the demo,
   the evaluation? Compute, headcount, calendar, and dependencies.
8. **How long does the evaluation take before we can call it?**
   Bounded. Six months is the reference maximum for horizon-2
   entries; twelve months for horizon-3.
9. **What are the checkpoints and what does "declared" success or
   failure look like?** Written now, so the retrospective can
   compare it to what actually happened.

**Why written and not verbal.** Verbal evaluations do not survive
the champion leaving. Written evaluations are read by successors
and by the Board — they are the evaluation, not documentation *of*
the evaluation.

**Output of evaluation.** Each evaluation produces one of four
verdicts:

- **Enter horizon 1.** Product organisation has committed. Transfer
  contract signed.
- **Enter horizon 2 or 3.** Portfolio funds a bounded project;
  next gate defined; stopping criterion defined.
- **Park under defensive scan.** No project funded; the programme
  refreshes the read at a stated cadence (annual by default). A
  parked technology is not free — the cost is a stated fraction
  of an analyst's time.
- **Do not pursue.** Written argument on file. Same technology
  cannot re-enter under the same argument for a stated period
  (typically twelve months); it can re-enter if the argument
  changes.

**Why four verdicts and not five stars.** A five-star system
invites averaging; averaging invites rounding-up to "yes, but
scoped". Four categorical verdicts force a decision and a defence.

### 2.4 Stage gates — the funding cadence

Once a project is in the portfolio, it runs on stage gates, not
on discretion. The reference programme uses four gates.

- **G0 — Entry.** Written Heilmeier response accepted by the
  Innovation Portfolio Board. Budget committed to G1.
- **G1 — Concept validation.** Six to twelve weeks. Demonstrates
  the phenomenon on Halcyon-realistic conditions or acknowledges
  it does not. Deliverable: written concept report and go/no-go
  recommendation from the project lead.
- **G2 — Capability build.** Three to nine months depending on
  horizon. Produces a characterised capability against a
  scenario the receiving team recognises. Deliverable:
  characterisation report, receiving-team review, transfer plan
  or explicit horizon-3 continuation argument.
- **G3 — Transfer or park.** Handover artifact accepted by a
  named receiving team, or park-with-review. Horizon-3 projects
  that survive G3 without a receiving team enter a defensive-
  scan register and are reviewed annually against the thesis.

The Innovation Portfolio Board approves each gate. Gates that
default (nobody makes a decision) close as no-go — the default
is stop, not continue. Innovation programmes drift because gates
default the other way: "nobody said stop" quietly becomes
"nobody said stop for six years."

**Why stage-gated and not milestone-tracked.** Milestone tracking
is a project-management artifact; stage gating is a portfolio-
management artifact. The distinction matters because stage gates
give the Portfolio Board a place to *rebalance* — pull a project
back to the pool without insulting the team — that milestones do
not.

### 2.5 The transfer contract — where the programme lives or dies

Every horizon-1 project and every horizon-2 project that reaches
G3 exits the programme through a **transfer contract** between
the R&D team and a receiving product or platform team. The
contract is the definition of done.

The reference transfer contract is a written agreement, signed
by the R&D lead and the receiving team lead, covering:

- **The artifact.** What the receiving team is accepting — a
  model, a training pipeline, an evaluation harness, a control
  scheme, a compiler pass, a piece of documentation. Named.
- **The characterisation.** What the artifact has been measured
  against, on what data, at what confidence. This is the
  Project 403 evidence bundle, produced during R&D so the
  transfer boundary does not become an evidence bottleneck.
- **The interface.** Where the artifact plugs in — the exact
  point in the product pipeline, the exact function signature or
  service contract, the exact runtime constraints.
- **The residual risk owned by the receiving team.** Named risks
  the R&D team could not fully characterise, and the receiving
  team's plan for owning them post-transfer.
- **The support obligation.** How long, on what terms, does the
  R&D team remain on the hook to answer questions and to fix
  identified defects? Reference default: 90 days of first-call
  support with named on-call, plus a bug-triage relationship
  for a further 90 days.
- **The transfer date and the transfer test.** A defined test
  the receiving team runs at handover, and a defined date at
  which the receiving team either accepts or refuses transfer.

**Why the contract is signed.** Signed contracts survive
personnel change. A verbal handover between the current AI Lab
lead and the current product-engineering director evaporates when
either one leaves. The signed transfer contract is the artifact
that lives on both sides afterwards.

**Why the receiving team can refuse.** A receiving team that
cannot refuse a transfer is a receiving team that will silently
never adopt anything the Lab produces. Refusal is the mechanism
by which the R&D programme learns what the product organisation
actually needs, versus what the Lab thought it needed.

### 2.6 Academic-and-external partnerships — durable, contractual, exitable

The reference partnership model treats every external partnership
as an instrument with a defined purpose, defined term, and
defined exit.

**Structural templates.** The programme uses four structural
templates rather than negotiating each partnership from scratch:

- **University research contract.** A time-boxed research
  contract with a named principal investigator (PI) at a
  named institution, delivering named artifacts against a
  named scope, at commercial IP terms Halcyon can live with.
  Not a sponsorship. Not a gift. The contract explicitly names
  the successor PI if the named PI leaves, and the fallback
  path if no successor is named.
- **National-lab / consortium participation.** Participation in
  a consortium (Fraunhofer, imec, EPRI, EMBL, etc., where topical),
  a public research programme (Horizon Europe calls,
  Chips Act-funded consortia, US DOE / NIST-adjacent research
  vehicles), or an industry consortium. Value flow is defined
  ex ante — access to shared instrumentation, shared data, or
  pre-competitive research — and Halcyon's contribution
  (money, engineer time, in-kind) is budgeted.
- **Start-up engagement.** Deal-flow tracking on a defined watch
  list, evaluation of specific start-ups against the Heilmeier
  protocol before any commercial engagement, and one of three
  outcomes: no engagement, commercial pilot on Halcyon's normal
  procurement terms, or corporate-development referral to the
  M&A function. Investment via a corporate venture arm is out
  of scope of this programme by design; investment is a
  finance function.
- **Talent partnership.** Structured internship, industrial-PhD,
  and visiting-researcher instruments whose primary value is
  talent flow into Halcyon and secondary value is research
  output. Recorded as such — a talent partnership that is
  scored on publications will be run to publish, not to hire.

**Contracting posture.** Halcyon's default posture:

- Halcyon owns foreground IP created substantially with Halcyon
  funding on Halcyon-specific problems, with a defined licence
  back to the academic partner for non-commercial research and
  publication.
- Background IP each side brings remains that side's; each side
  licences background IP to the other only as needed to execute
  the contracted work.
- Publication is permitted after a review window (typically 30
  to 60 days) for patent-filing decisions, and after a
  confidentiality review for Halcyon trade secret content.
- Data flowing from Halcyon to the partner is contractually
  governed against Halcyon's data-classification policy and
  the applicable data protection law (GDPR, LGPD, DPDP,
  US state privacy laws) at rest inside the partner.

**Exit.** Every partnership contract names its exit — expiry
date, notice period for early termination, wind-down obligations
(data destruction / return, IP settlement, publication
completion). A partnership without an exit is a de-facto
open-ended commitment the CFO cannot forecast.

**Why templates and not bespoke.** Bespoke partnership contracts
consume Legal's time and produce a portfolio nobody can compare.
Four templates give the Board a compact view of what the
programme is committed to.

### 2.7 IP portfolio strategy — filings backed by argument

The reference IP strategy has two commitments and one refusal.

**Commitment 1 — Every filing has a written strategic argument.**
Attached to every invention disclosure that reaches a filing
decision is a written argument on one page addressing:

- **What is the defensive perimeter this filing extends?** Which
  product surface does it protect, and against which competitor
  or freedom-to-operate challenge?
- **What is the offensive value?** Is this filing part of a
  cross-licensing pool, a standards-essential-patent position,
  or a specific competitive-blocking case? If none, the filing
  is defensive-only, and the argument states so.
- **What is the trade-secret alternative and why was it rejected?**
  Some inventions are better kept as trade secrets — inspection
  reveals nothing, replication is hard, patent life is short
  compared to competitive advantage. Filings that could have been
  trade secrets are marked and the choice defended.

Patents filed without an argument are not filed at Halcyon. The
argument is reviewed at the Innovation Portfolio Board and
approved as a batch on a defined cadence (quarterly by default).

**Commitment 2 — Freedom-to-operate is a continuous cadence, not
a fire drill.** Halcyon's IP counsel maintains a freedom-to-
operate landscape review per product line at a stated cadence
(annual for mature product lines, semi-annual for lines
undergoing significant AI adoption). Findings feed the portfolio:
a hard freedom-to-operate constraint may create a horizon-1
project (design around) or may drive a licensing decision.

**Refusal — Patent count is not a programme metric.** The
programme deliberately does not headline patents-filed or
patents-granted as a top-line metric. Patents are an instrument;
they are counted, but the top-line scorecard is protected against
them (see section 2.8). The reference programme reports patents
filed as a footnote, not a headline.

**Open-source posture.** Where the programme's work touches
open-source code, the posture is:

- Consume open-source software subject to Halcyon's existing
  software-licence compliance process (this programme does not
  redesign that).
- Contribute back to open source where the strategic argument
  is that the contribution accelerates a capability Halcyon
  wants standardised — for example, a contribution to an
  evaluation harness the industry can share raises the floor
  Halcyon competes above. Contributions with strategic value
  are approved individually against the same one-page
  argument as a filing.
- Do not open-source the specific product-differentiating
  capability. Do not open-source anything until the freedom-
  to-operate analysis for the touched surface is current.

**Why arguments not counts.** Patent-count metrics are the
canonical example of a metric that degrades under Goodhart's law
in R&D programmes: teams file worse patents faster to hit the
number. Arguments are harder to fake, easier to audit, and lead
to a portfolio the general counsel can defend on its merits.

### 2.8 Metrics — a small scorecard, gaming-resistant by design

The reference programme instruments itself against a scorecard of
five headline metrics and a small set of hygiene metrics. The
scorecard is deliberately small; a fifteen-metric scorecard
optimises for the average of things nobody cares about most.

**Headline metrics (reported to the Board Strategy Committee
quarterly):**

1. **Transfer volume.** Number of artifacts transferred to a
   named receiving team in the period, and the aggregate value
   the receiving teams estimate those artifacts produced in
   their own P&L or roadmap terms. The receiving teams are the
   authoritative source of value; the Lab does not score itself.
2. **Transfer acceptance rate.** Of transfers offered in the
   period, the proportion the receiving team accepted at G3
   without material change to the contract. Low acceptance is
   diagnostic — either the R&D team is proposing artifacts the
   product organisation does not need, or the receiving teams
   are not prepared to receive. The Board looks at both.
3. **Option value created.** Horizon-2 and horizon-3 verdicts
   produced in the period — enter, park, do-not-pursue — with
   the count of parked-with-review capabilities and their
   review cadence. This is the option book the programme is
   building; a programme that produces zero verdicts is
   entertaining itself.
4. **Capability built.** Named capabilities (data assets,
   evaluation harnesses, tooling, methodology) that outlive the
   individual projects that produced them. This is a stock
   metric, not a flow metric; the programme reports what it has
   accumulated, not what it produced this quarter.
5. **Horizon adherence.** Actual spend by horizon versus target
   share (40/40/20 by default), with variance and explanation.
   The Board redirects, not the Lab.

**Hygiene metrics (reported semi-annually or on request):**

- Gate cycle time and gate-decision distribution (approved,
  redirected, stopped).
- Portfolio ageing — median time a project has been open, by
  horizon.
- Talent flow — hires from partnerships, internal transfers
  in and out of the programme, attrition.
- Publication and patent counts, reported as hygiene rather
  than as top-line — noted, not headlined.

**Metrics deliberately not counted at the headline:**

- Number of PoCs run. Trivially gameable, does not distinguish
  a serious evaluation from a slide.
- Papers published or citations. Gameable, drifts fast from
  business value, and creates a perverse incentive to run the
  programme as an academic department.
- Patents filed per scientist per year. See section 2.7.
- Media mentions, keynote invitations, industry-award
  submissions. These may be side-effects of a good programme;
  they are not what the programme is being funded to produce.

**How the metrics are protected against Goodhart drift.**

- The receiving team estimates value, not the Lab. The Lab
  cannot inflate its own scoreboard.
- Transfer acceptance rate is reported both ways: if the Lab
  is producing artifacts no team will accept, that is a
  Lab-side finding; if teams are refusing transferable
  artifacts, that is a receiving-side finding. The Portfolio
  Board reads both.
- The Board Strategy Committee reviews the scorecard
  definition annually and reserves the right to change it.
  The definition change itself is a governance artifact.

### 2.9 Governance — the Innovation Portfolio Board

The Innovation Portfolio Board is chartered in
`governance/innovation-portfolio-charter.md`. Key properties:

- **Composition.** Fixed-role, including the Group CTO or delegate
  (chair), Chief Product Officer or delegate, Chief Financial
  Officer or delegate, general counsel or delegate for IP,
  the AI Lab director, at least one product-business-unit
  engineering leader on a rotating seat, and at least two
  external members (typically one industry, one academic) with
  independence tested annually.
- **Authority.** Binding on: entry to and exit from the
  portfolio, gate decisions at G0–G3, budget allocation across
  horizons within the Board Strategy Committee envelope,
  approval of partnership templates and specific partnerships
  above a threshold, and approval of IP-filing arguments in
  batch. Advisory on: individual project technical direction
  (that stays with the R&D team lead), receiving-team readiness
  (that stays with the receiving team's own governance),
  responsible-AI evidence (that stays under the Project 403
  framework).
- **Cadence.** Monthly standing meeting for gate decisions and
  portfolio review; quarterly review with the Board Strategy
  Committee; annual thesis review.
- **Dissent recording.** Board decisions record dissent
  explicitly. Dissent above a threshold triggers escalation to
  the Board Strategy Committee.

**Why Portfolio Board and not "steering committee".** Steering
committees advise; portfolios are governed. The distinction is
whether anyone actually has the authority to close a project the
team is emotionally invested in. The Portfolio Board is designed
to have that authority.

### 2.10 Roadmap — twenty-four months, sequenced by reversibility

**Phase 0 (Months 0–3) — Thesis and portfolio inventory.**
Programme thesis drafted, reviewed with the Board Strategy
Committee, ratified. Existing AI Lab work inventoried against
the horizon model and the transfer contract requirement.
Portfolio Board chartered and seated. **Highly reversible.** No
new projects entered under new governance yet; existing projects
continue under existing terms.

**Phase 1 (Months 3–9) — Governance and evaluation live.**
Portfolio Board authoritative for all new project entries.
Heilmeier evaluation protocol published and used. Transfer
contract template published; first three horizon-1 projects
converted to transfer contracts as a proof of the machinery.
Stage-gate cadence live. Partnership templates published and
in use for new partnerships. **Medium reversibility.**

**Phase 2 (Months 9–18) — Backfill and steady state.** Existing
projects reclassified under the horizon model and either brought
under transfer contract, redirected, or closed. IP argument
process authoritative for new filings. Metrics scorecard reported
quarterly to the Board Strategy Committee. **Low reversibility
per project** — closing a project is expensive in trust — but
the reference approach front-loads the honesty rather than
carrying dead weight for years.

**Phase 3 (Months 18–24) — External review and thesis refresh.**
First external programme review, informed by comparators
(Halcyon's public peers' publicly stated R&D disciplines,
national research-programme benchmarks, ISO 56002-adjacent
management-system review). Thesis reviewed against results;
Board Strategy Committee approves the next horizon-share
allocation and any thesis update.

**Beyond month 24.** The programme runs on an annual thesis
review, semi-annual portfolio deep-dive, and continuous stage-
gated portfolio management. There is no "phase 4"; the
programme is now steady state, and steady state is the point.

**Why sequenced by reversibility.** Same reasoning as Projects
402 and 403. Chartering an evaluation protocol is a cheap Phase 0
mistake; closing a live project the wrong way in Phase 2 is an
expensive one. The reference sequences the cheap decisions early
so the expensive ones can be defended.

### 2.11 What is deferred, and why

Some items are deliberately deferred beyond the reference:

- **Specific compute-procurement decisions for research access
  (frontier model APIs, sovereign compute, on-prem research
  cluster sizing).** The programme names the categories it
  requires; the sizing and vendor mix are a platform-and-
  procurement decision informed by Phase 1 evaluation results.
  Tracked as **FOLLOWUP-COMPUTE-01**.
- **Specific standards-body engagement.** The programme's
  contribution posture toward ISO/IEC JTC 1/SC 42 (AI standards),
  IEEE working groups, and industrial-automation-adjacent bodies
  (IEC 61508 safety-critical, IEC 62443 industrial security,
  OPC UA) is decided per body in Phase 1, once the initial
  Heilmeier evaluations have surfaced which bodies the
  programme has substantive contributions for. Tracked as
  **FOLLOWUP-STANDARDS-01**.
- **Corporate development / M&A interface.** The programme's
  interface with Halcyon's M&A function (which targets qualify
  for referral, on what basis, with what non-conflict
  protections) requires a specific governance conversation
  between the CTO, CFO, and General Counsel. Tracked as
  **FOLLOWUP-CORPDEV-01**.

Deferrals are scoped, time-bound, and tracked. They are not open
research questions blocking the reference programme.

## Implementation

The implementation approach is defined by the roadmap in
Section 2.10, the stage gates and transfer contract in Sections
2.4–2.5, and the metrics in Section 2.8. Rather than repeat those,
this section names the invariants an implementation team must
hold:

- **Thesis-first.** No portfolio decision is defensible in the
  absence of the thesis. If the thesis is not written and
  ratified in Phase 0, every downstream argument becomes a
  personality contest.
- **Transfer contract is the definition of done.** A gate-3
  claim without an accepted transfer contract is a demo. If
  the programme accumulates demos without transfers for two
  consecutive quarters, the programme is failing and the
  Portfolio Board says so.
- **Heilmeier verdicts are archived.** Written evaluations are
  the programme's institutional memory. Losing them means
  future evaluations reinvent conclusions the programme has
  already reached. The archive is a first-class artifact.
- **Portfolio Board authority is scoped.** The Board is binding
  on entries, exits, gates, budgets, partnership templates,
  and IP arguments; it is advisory on technical direction and
  on receiving-team readiness. Preserving that split is what
  keeps the Board out of engineering micromanagement and
  keeps engineering out of portfolio politics.
- **Metrics read from records.** The transfer scorecard is
  produced from the transfer-contract registry and the
  receiving-team estimates, not from a Lab-authored slide
  deck. If a metric needs manual assembly, the underlying
  record is missing a field — fix the record.
- **Sponsor-neutral operating cadence.** Gate cadence,
  quarterly Board Strategy Committee review, and annual
  thesis review run on schedule regardless of leadership
  transitions. The design does not depend on the current
  Group CTO being in seat.

Sizing, team topology, and per-artifact build ownership are
captured in `program/innovation-program-design.md`; that
document is the operational companion to this SOLUTION.

## 3. Validation steps

A senior architect validates the programme against the following.
If any check fails, the design is not yet ready for the Board
Strategy Committee.

**Structural checks:**

1. Pick a random project the programme funds. Can you produce
   its Heilmeier response, its current horizon assignment, its
   next gate date, its stopping criterion, and (if horizon 1
   or advanced horizon 2) its transfer contract? All in under
   fifteen minutes? If not, the portfolio is a spreadsheet.
2. For a horizon-1 project that has transferred in the last
   twelve months, name the receiving team, the accepted
   artifact, the value the receiving team estimated, and the
   date the support obligation expired. Can any of these be
   resolved from a slide instead of from the contract? If yes,
   the transfer machinery is aspirational.
3. Show the last three Portfolio Board decisions. For each,
   name the vote, the dissent recorded, the follow-up
   committed, and the artifact where the decision is stored.
   If any is irretrievable, the Board is a meeting, not a
   governance body.

**Portfolio dry-runs:**

4. The CFO asks "why is our horizon-3 spend up 40% year-on-year
   when our thesis says 20% cap?" What is the source-of-truth
   artifact? How long to produce it? What is the Board's
   argued response?
5. The Group CTO proposes moving a substantial engineering
   effort onto a quantum-simulation collaboration. Walk
   through Heilmeier evaluation, horizon assignment, gate
   plan, partnership template, IP terms, and stopping
   criterion. At which points is the proposal blocked, and
   by what?
6. A horizon-2 project fails its G2 characterisation gate.
   Walk through the response path: Portfolio Board review,
   options (redirect / continue with tighter scope / stop),
   communication to the R&D team, redirection of budget.
   Which of these are automated, which are human, and which
   are on a clock?

**Transfer and IP dry-runs:**

7. A receiving product team refuses a G3 transfer. What
   happens next? Where is the refusal recorded, and what
   does the Portfolio Board do with it?
8. Halcyon's General Counsel asks for the strategic argument
   behind a specific patent filing five years old. Where is
   the argument, and can it be produced?
9. An academic partner's named principal investigator moves
   to a different university mid-contract. What breaks in
   the programme? (Correct answer: not the programme; possibly
   the partnership; the named-successor clause in the
   contract governs the transition.)

If steps 1–9 can be walked through without hand-waving, the
programme is review-ready. If any require "we would need to
build that," the programme is not yet complete.

## 4. Rubric — quick reference

The full rubric lives at `rubric/evaluation-rubric.md`. The six
weighted dimensions are:

1. **Portfolio thesis defensibility** (weight: 20%). Is there
   a written thesis, and does it exclude as much as it includes?
2. **Transfer contract enforceability** (weight: 20%). Is
   "transferred to a receiving team" the definition of done,
   with a signed artifact and a receiving-team estimate?
3. **Emerging-technology evaluation** (weight: 15%). Does the
   programme evaluate against a written protocol producing
   written verdicts, or against demos?
4. **Portfolio governance** (weight: 15%). Is the Portfolio
   Board's authority scoped, binding on the classes named,
   with dissent recorded?
5. **Metrics resistance to gaming** (weight: 15%). Do the
   headline metrics reward value transferred and options
   created, and is the receiving team (not the Lab) the value
   source?
6. **Partnership and IP strategy** (weight: 15%). Do
   partnerships have written contracts with defined exits, and
   are IP filings backed by written strategic arguments?

A submission scoring below 60 on Dimension 1 (thesis) or
Dimension 2 (transfer) is non-passing regardless of other scores.
A senior architect who cannot show either "what we are placing
bets on" or "how the bets exit the Lab" has not demonstrated
the level.

## 5. Common mistakes

**1. A lab charter instead of a portfolio thesis.** A charter
says what the Lab is; a thesis says what the Lab is *for*, in
a way that can be argued with. Charters accumulate; theses
decide.

**2. No transfer contract.** The most common failure mode.
Projects "graduate" through hand-shakes, receiving teams never
truly own them, the Lab drifts into a permanent zoo of
half-adopted capabilities. The reference programme requires a
signed contract or the project has not exited.

**3. Horizon 3 quietly dominates.** Every innovation programme
that fails failed here: exploratory work grew because it was
more exciting and less accountable, until the horizon-1
committed work was starved. The reference programme caps
horizon 3, not floors it.

**4. Emerging tech chased on vendor timeline.** If the
programme's evaluation cadence is set by when the next vendor
briefing lands, the vendors are running the portfolio. The
reference programme runs evaluation on the programme's cadence
against a written protocol, and files vendor briefings as
inputs.

**5. Partnerships as photographs.** A partnership announced in
a press release with no scope, no PI-successor clause, no exit,
and no IP flow is a photograph. Halcyon needs partnerships that
outlive the champion who set them up.

**6. IP filed by count.** Filing decisions driven by a target
number produce worse patents, faster, at high cost, with no
strategic position. The reference programme files against
written strategic arguments and lets the count be a residual.

**7. Metrics that measure the Lab, not the business.** Patent
count, publication count, headcount, PoC count — all of these
measure the *Lab's activity*. The reference scorecard measures
what the business receives, and lets Lab activity be a hygiene
metric.

**8. "Innovation theatre".** The moral equivalent of a hackathon
without production consequences: media event, demo, keynote,
no artifact accepted anywhere in the product organisation. The
reference programme does not fund theatre; if the programme
wants a public voice, that is a Communications decision on top
of real programme output, not a substitute for it.

**9. Portfolio Board as steering committee.** A body that
advises but does not decide leaves the Lab director as the
decision-maker by default, which is the failure mode the
programme was set up to avoid. The reference Board is binding
on the listed classes.

**10. Named-person dependencies.** If the programme only works
while the current Group CTO or the current Lab director is in
seat, the programme is a personal project, not an enterprise
capability. Every role in the reference programme is a role,
not a name.

## 6. References

Standards, frameworks, and canonical sources cited or relied
upon by this solution:

- **ISO 56000:2020** — Innovation management — Fundamentals and
  vocabulary. Sets the definitional frame the programme uses
  when it says "innovation portfolio", "innovation partnership",
  etc.
  <https://www.iso.org/standard/69315.html>
- **ISO 56002:2019** — Innovation management — Innovation
  management system — Guidance. The management-system frame the
  reference programme aligns to for portfolio governance,
  partnership handling, and IP integration.
  <https://www.iso.org/standard/68221.html>
- **ISO 56003:2019** — Innovation management — Tools and methods
  for innovation partnership — Guidance. The partnership-model
  frame Section 2.6 aligns to.
  <https://www.iso.org/standard/68197.html>
- **ISO 56005:2020** — Innovation management — Tools and methods
  for intellectual property management — Guidance. The IP-
  strategy frame Section 2.7 aligns to.
  <https://www.iso.org/standard/72761.html>
- **OECD Frascati Manual (2015)** — Guidelines for Collecting and
  Reporting Data on Research and Experimental Development. The
  reference for what counts as R&D versus adjacent activity.
  <https://www.oecd.org/publications/frascati-manual-2015-9789264239012-en.htm>
- **OECD Oslo Manual (2018)** — Guidelines for Collecting,
  Reporting and Using Data on Innovation. Complementary to
  Frascati; the reference for measuring innovation output.
  <https://www.oecd.org/science/oslo-manual-2018-9789264304604-en.htm>
- **DARPA Heilmeier Catechism** — the nine questions attributed
  to George Heilmeier (former DARPA Director) that the
  evaluation protocol in Section 2.3 adapts.
  <https://www.darpa.mil/about-us/heilmeier-catechism>
- **NASA Technology Readiness Level (TRL) definitions** — the
  TRL 1–9 scale used across US and EU public research programmes.
  Cited as the maturity framing horizon-2/horizon-3 verdicts
  reference.
  <https://www.nasa.gov/directorates/somd/space-communications-navigation-program/technology-readiness-levels/>
- **European Commission — Horizon Europe (2021–2027)** — the EU
  framework programme for research and innovation. Cited as an
  example public-research vehicle the partnership model
  contemplates.
  <https://research-and-innovation.ec.europa.eu/funding/funding-opportunities/funding-programmes-and-open-calls/horizon-europe_en>
- **WIPO — Patent Cooperation Treaty (PCT)** — the international
  patent-filing frame Halcyon's IP strategy operates within.
  <https://www.wipo.int/pct/en/>
- **European Patent Office / EPC** — the European patent
  system Halcyon's EU filings target.
  <https://www.epo.org/law-practice/legal-texts/epc.html>
- **United States Patent and Trademark Office (USPTO) —
  Manual of Patent Examining Procedure (MPEP)** — the US
  patent-prosecution frame.
  <https://www.uspto.gov/web/offices/pac/mpep/>
- **EU Artificial Intelligence Act** — Regulation (EU) 2024/1689.
  Cited because prototypes that ship into customer factories are
  still in scope. Where R&D produces high-risk AI systems, the
  Project 403 evidence bundle is what the transfer contract must
  satisfy.
  <https://eur-lex.europa.eu/eli/reg/2024/1689/oj>
- **ISO/IEC 42001:2023** — AI management system. The
  management-system standard the Responsible AI framework
  (Project 403) is anchored on and that this programme inherits
  at the transfer boundary.
  <https://www.iso.org/standard/81230.html>
- **NIST AI Risk Management Framework (AI 100-1)** — cited as
  the risk-management frame the evaluation protocol carries
  into Heilmeier question 6 (risks and payoffs) and the
  transfer contract carries at handover.
  <https://www.nist.gov/itl/ai-risk-management-framework>
- **OECD AI Principles** — cited as international policy frame
  for Halcyon's programme boundaries.
  <https://oecd.ai/en/ai-principles>
- **Council of Europe Framework Convention on AI (2024)** —
  cited as an emerging international-treaty signal for the
  regulatory-drift argument.
  <https://www.coe.int/en/web/artificial-intelligence>
- **Baghai, Coley, White — "The Alchemy of Growth" (1999)** —
  the canonical source for the three-horizons portfolio frame
  Section 2.2 adapts to R&D.
- **Cooper, Robert G. — Stage-Gate methodology** — the widely-
  used stage-gated portfolio-management frame the gate cadence
  in Section 2.4 draws on. "Stage-Gate" is a registered mark of
  Stage-Gate International; the reference programme uses the
  category, not the branded methodology.
  <https://www.stage-gate.com/>
- **Christensen, Clayton M. — "The Innovator's Dilemma" (1997)** —
  cited as the canonical argument for the horizon-3 defensive-
  scan register (the sustaining-versus-disruptive distinction).

Related solutions in this repository:

- `projects/project-401-transformation-strategy/SOLUTION.md` —
  the transformation-strategy view that sits above and funds
  a programme like this.
- `projects/project-402-global-ai-platform-architecture/SOLUTION.md`
  — the platform the programme's transfer contracts ship onto.
- `projects/project-403-responsible-ai-framework/SOLUTION.md` —
  the Responsible AI framework the transfer contract inherits
  at the boundary between R&D and production.
- `modules/mod-405-responsible-ai/SOLUTION.md` and
  `modules/mod-403-enterprise-governance/SOLUTION.md` — the
  module-level views this programme composes with.

## Time budget

- **Review-time read**: 45 minutes to read this SOLUTION plus
  `program/innovation-program-design.md`. This is the minimum
  to participate in a programme review.
- **Full deliverable read**: 4–5 hours to read all artifacts
  (SOLUTION, programme, portfolio charter, rubric) with the
  referenced standards open in a second tab.
- **Learner-side build**: a strong learner produces a defensible
  first draft in 25–35 hours of focused work, plus a further
  10–15 hours iterating after CFO and internal-audit review.

## Status

**Version**: 1.0
**Status**: Reference solution
**Owner**: Senior Architect curriculum track
