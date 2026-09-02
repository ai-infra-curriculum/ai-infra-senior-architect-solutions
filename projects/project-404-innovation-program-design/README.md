# Project 404: AI Innovation Program Design

> Senior-architect capstone. The learner submits an enterprise AI
> innovation programme that a Board Strategy Committee, a Chief
> Financial Officer, and a platform engineering director can all sign
> off on — without any one of them silently subsidising the other two.

## Scenario (fictional)

**Halcyon Industrial Group** is a fictional multinational industrial-
automation and electric-drives manufacturer headquartered in Munich.
The group designs and manufactures programmable controllers, servo
and induction drives, factory-floor vision and vibration sensing,
and the software stack that ties them together. Halcyon sells into
automotive, semiconductor, food-and-beverage, pharmaceutical, and
grid-scale-storage customers across the EU, the United States,
Japan, South Korea, and mainland China. Revenue mix, headcount, and
R&D spend are illustrative only; the scenario exists to force
concrete innovation-programme trade-offs against named external
frameworks and standards.

Halcyon's current AI-adjacent capabilities are split across the
business:

1. **Applied AI in product** — quality-inspection vision models,
   predictive-maintenance models, and drive-loop tuning models
   embedded in shipping products. Owned by the product business
   units. Roadmap-driven, quarterly release cadence.
2. **Applied AI in operations** — demand forecasting, supplier
   risk scoring, warranty analytics. Owned by the CIO organization.
   Line-of-business ROI.
3. **A small central "AI Lab"** — approximately thirty engineers,
   founded three years ago inside the Group CTO's office, currently
   pursuing a mixed portfolio (foundation-model experiments,
   physics-informed learning, one exploratory quantum-simulation
   collaboration, and an internal Copilot-for-engineers project).
   No published portfolio thesis. No transfer contract with the
   product business units.

Three independent events force the design of a real innovation
programme, not just an expansion of the AI Lab:

- **Competitive**. Halcyon's traditional differentiation was
  mechanical (precision, reliability, service life). Peer
  manufacturers are increasingly competing on the *intelligence*
  embedded in the drive, the sensor, and the control loop. A
  three-to-five-year lag in incorporating emerging AI capability
  into the product line is a plausible extinction event for a
  business whose customers plan capital equipment on a
  fifteen-year horizon.
- **Financial**. The current AI Lab spend is material but not
  visible on the segment P&L. The CFO has asked the Group CTO to
  either move the Lab onto a defensible portfolio basis or fold
  it into product engineering. The Board Strategy Committee has
  approved a scoped standing R&D commitment for AI *provided* the
  programme can defend it as a portfolio, not as a line item.
- **Regulatory and standards drift**. The EU AI Act (Regulation
  (EU) 2024/1689) is now in force; the ISO/IEC AI standards suite
  (42001, 23894, and the emerging 42005 impact assessment work)
  is landing over the next twenty-four months; the OECD AI
  Principles and Council of Europe Framework Convention on AI
  are the international policy frame. Halcyon's innovation
  programme cannot pretend those obligations do not apply to R&D.
  Prototype code that ships into a customer factory is still
  in scope.

The Board has approved a standing **AI Innovation Programme** and
asked the AI Infrastructure Senior Architect (the learner) to
produce the programme design, the portfolio governance charter,
the emerging-technology evaluation framework, the academic-and-
external partnership model, the intellectual-property portfolio
approach, and the metrics-and-transfer model. Continued Board
funding for the programme is contingent on the design surviving a
Group Audit review and a Board Strategy Committee review.

## The problem statement (what a senior architect is being asked to solve)

Design an enterprise AI innovation programme such that:

1. **The portfolio is defensible on its own terms.** The programme
   can name every project it funds, the horizon each belongs to
   (near-term product enablement, adjacent-market option, frontier
   / step-change), the budgeted commitment, and the trigger under
   which each project is stopped, transferred, or continued. A
   Board Strategy Committee member can ask "why are we spending on
   X and not on Y?" and get an argued answer.
2. **Emerging technologies are evaluated, not sampled.** New
   external capabilities (frontier model families, next-generation
   accelerator hardware, quantum simulation, neuromorphic edge
   inference, physical AI / world models, whatever comes next)
   pass through a documented evaluation protocol before consuming
   engineering time. The protocol produces a written verdict, not
   a demo.
3. **Academic and external partnerships create durable option
   value.** Every partnership has a stated hypothesis, a defined
   value flow in both directions, a defined exit, and a defined
   IP position. A partnership that outlives its principal
   investigator or its Halcyon champion has been designed for
   institutional continuity, not personal continuity.
4. **The IP portfolio serves the business, not the scoreboard.**
   Filing decisions are made against a written strategy (defensive
   coverage of core product surfaces, offensive coverage of
   strategic options, cross-licensing leverage, freedom-to-operate
   analysis). Patent count is not the objective; strategic
   position is.
5. **Metrics resist gaming.** Innovation-programme metrics count
   what the business actually cares about — technology transferred
   into product, value delivered, options created, capability
   built — and refuse to count what is easy to inflate
   (headline PoC count, publication count without impact,
   patents-filed without a strategic argument, "innovation
   theatre").
6. **There is a transfer contract.** The definition of "done"
   for an R&D project is that a receiving product or platform team
   has accepted a defined artifact against a defined contract.
   R&D projects that never leave the Lab are worse than no R&D
   at all: they consume runway and demoralize the receivers.
7. **The programme survives regulatory and standards drift.** The
   programme's operating obligations under the EU AI Act, ISO/IEC
   42001, and equivalents are handled as ongoing policy items,
   not as one-off legal projects.

## Deliverables the learner submits

1. **Innovation programme design** (`program/innovation-program-design.md`
   or equivalent). The reference artifact this repository ships.
   Includes portfolio structure, horizon model, funding model,
   stage-gate operating model, and transfer contract.
2. **Portfolio governance charter** (`governance/innovation-portfolio-charter.md`
   or equivalent). The Innovation Portfolio Board — composition,
   authority, quorum, decision rights, dissent recording,
   escalation to the Board Strategy Committee, standing agenda,
   external-member policy, conflicts-of-interest handling.
3. **Emerging-technology evaluation framework** (a section within
   the programme, or standalone). The written protocol by which
   an emerging capability moves from "someone read a paper" to
   "the programme committed a budget line." Includes the
   Heilmeier-adjacent question set the programme uses.
4. **Academic-and-external partnership model** (a section within
   the programme). Structural template for university, national-
   lab, industry-consortium, and start-up partnerships;
   contracting posture; IP flow; talent flow; exit provisions.
5. **IP portfolio strategy** (a section within the programme).
   Defensive vs. offensive posture, filing decision criteria,
   freedom-to-operate cadence, standards-essential-patent
   posture, trade-secret vs. patent trade-off, open-source
   contribution posture where it interacts with IP.
6. **Innovation metrics framework** (a section within the
   programme). The scorecard — what is counted, what is
   deliberately not counted, and how each metric is protected
   against Goodhart-style degradation.
7. **Programme roadmap and risk register.** Twelve-to-thirty-
   six-month sequenced roadmap plus a top-ten risks register
   with probability, impact, mitigation, and residual risk.
   Must include: transfer failure (R&D lands nowhere), portfolio
   drift (horizon-3 spend quietly grows to dominate), talent
   flight, emerging-tech FOMO capture (the programme chases
   every announcement), and IP leakage through partnerships.

## Explicitly out of scope

- **Product engineering roadmaps.** The programme funds R&D that
  produces artifacts a product team may adopt; the product
  roadmap remains the product organisation's decision.
- **Detailed vendor selection for compute and tooling.** The
  programme names the categories of infrastructure it needs
  (frontier-model access, research compute, evaluation harnesses,
  IP-management tooling); specific vendor choice is a platform
  procurement decision informed by the programme.
- **Full financial model in dollars.** The programme defends its
  portfolio in structure, allocation rules, and stop-criteria.
  The precise segment-level NPV of each horizon is a CFO artifact
  informed by the programme. (Contrast with Project 401, which
  is the finance workstream.)
- **Responsible AI policy.** Responsible AI obligations that
  apply *once a system is in production* are Project 403's scope.
  This project inherits Project 403 as a constraint — R&D that
  intends to ship must arrive at the transfer boundary with the
  evidence Project 403 requires — but does not redesign it.
- **Non-AI corporate R&D.** Halcyon's mechanical, materials, and
  power-electronics R&D is governed by the group's existing R&D
  process. This programme is the AI-specific overlay.

## What "senior architect quality" means for this project

A junior submission gives you a lab charter and a wish list. A
senior submission gives you a programme whose claims a CFO could
audit and a Board Strategy Committee could redirect:

- **The portfolio has a written thesis.** Not a mission statement —
  a thesis. The reference programme takes a position on which
  bets the group is placing and why, and defends that position
  against alternatives it explicitly did not take.
- **The evaluation protocol produces written verdicts.** The
  reference programme's answer to "should we work on quantum?"
  is a document, not a hunch. That document is preserved.
- **Partnerships have contracts, not photographs.** The
  reference partnership template survives principal-investigator
  rotation and Halcyon champion rotation.
- **The IP position is argued.** Every filing has a written
  strategic argument attached. Patents without an argument are
  not filed at Halcyon.
- **The metrics reward transfer.** The reference scorecard
  weights technology landed in product above technology
  demonstrated in the Lab.
- **The programme survives leadership rotation.** If the current
  Group CTO leaves next quarter, nothing in the programme design
  breaks. Named-person dependencies are a design defect.

The reference solution in `SOLUTION.md` is not a scoring key with a
single right answer. It is a set of trade-offs a senior architect
should be able to defend on their feet in a Board Strategy
Committee session.

## Evaluation

See `rubric/evaluation-rubric.md` for the scoring rubric. The
rubric weights **defensibility of the portfolio** and
**enforceability of the transfer contract** above **breadth of the
idea catalogue**. A learner who submits a lab with fifteen exciting
projects and no transfer contract will score below a learner who
submits five defended bets and a working transfer path.

## Reading order

1. `README.md` (this file) — the scenario and the ask.
2. `SOLUTION.md` — the senior-architect reasoning the reference
   programme encodes.
3. `program/innovation-program-design.md` — the reference
   programme artifact.
4. `governance/innovation-portfolio-charter.md` — the reference
   Innovation Portfolio Board charter.
5. `rubric/evaluation-rubric.md` — the scoring rubric graders use.

## Version

**Version**: 1.0
**Status**: Reference solution
**Owner**: Senior Architect curriculum track
