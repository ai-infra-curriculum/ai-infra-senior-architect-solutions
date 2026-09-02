# Project 406: Enterprise AI Governance Model

> Senior-architect capstone. The learner submits an enterprise
> AI governance model — the framework, the Architecture Review
> Board charter, the investment-prioritisation and portfolio-
> management model, the RACI for AI decision-making, the Board-
> level oversight model, and the compliance-and-audit framework
> — that a Chief Executive Officer, a General Counsel, a Chief
> Financial Officer, a Chief Information Security Officer, and
> an Internal Audit lead can each rely on without any one of
> them silently subsidising the risk the other four carry.

## Scenario (fictional)

**Halcyon Industrial Group** — the same fictional multinational
industrial-automation and electric-drives manufacturer used in
Projects 401–405 — has, over the last thirty-six months,
approved five discrete AI programme decisions at five different
governance tables using five different decision templates.

- The Project 401 transformation strategy was ratified by the
  Board on a strategy paper reviewed by the Strategy Committee.
- The Project 402 global AI platform architecture was approved
  by an ad-hoc CTO-convened technical review with post-hoc
  Investment Committee sign-off on the platform budget.
- The Project 403 Responsible AI framework was ratified by the
  Board's Risk Committee on a Legal-and-Ethics submission and
  runs its own AI Responsibility Board.
- The Project 404 innovation programme was ratified by the
  Board Strategy Committee on the recommendation of the newly-
  chartered Innovation Portfolio Board.
- The Project 405 industry thought-leadership programme was
  ratified by the Board Strategy Committee on a paper co-signed
  by the Chief Marketing Officer, General Counsel, and Chief
  Information Security Officer and is governed by the External
  Voice Review Board.

None of those five decisions was wrong. All five were made
against different templates, on different cadences, with
different quorum rules, different escalation paths, different
archival practices, and (crucially) different notions of what
counts as an "AI decision" that requires enterprise-level
review at all. Halcyon's Chief Information Officer discovered
during a pre-audit walkthrough that a business-unit AI project
covering safety-critical customer telemetry had been approved
by a divisional steering committee without ever passing through
the Responsible AI Board, the Innovation Portfolio Board, or
any of the platform architecture review paths — because it did
not, on its own reading of the policies, meet the threshold for
any of them.

Three independent events force the design of a coherent
enterprise AI governance model, not five parallel governance
bodies with overlapping mandates and undefended gaps between:

- **Regulatory-audit horizon.** Halcyon operates in
  jurisdictions where the EU AI Act (Regulation (EU) 2024/1689),
  US NIST AI Risk Management Framework alignment, and
  ISO/IEC 42001 AI-management-system certification are moving
  from voluntary to expected within the audit windows external
  auditors are already scoping. An auditor who cannot follow
  Halcyon's "how did this AI system get approved" path in a
  single traversal from the Board minute to the artifact will
  produce a finding that costs Halcyon procurement cycles at
  its largest customers.
- **Board fiduciary exposure.** Halcyon's Board has been
  informed by General Counsel that directors' fiduciary duties
  now extend to AI-system oversight — under the same
  Caremark-line reasoning that produced compliance-programme
  oversight duties in earlier decades and cybersecurity-
  oversight duties in recent ones. Board members individually
  now bear an obligation to be able to demonstrate an
  informed oversight process for AI. "The AI Lab told us it
  was fine" is not an informed oversight process.
- **Investment-portfolio drift.** The AI-adjacent spend across
  Halcyon has grown from a single Project 401 platform budget
  into a portfolio spread across the Project 402 platform,
  Project 403 Responsible AI operations, Project 404
  innovation-programme allocations, Project 405 external-voice
  programme, and dozens of divisional AI-adjacent line items.
  No single body currently sees the total AI-adjacent spend or
  can compare it against a defended prioritisation model. The
  Chief Financial Officer is unwilling to sign the next
  three-year plan without one.

The Board has asked the AI Infrastructure Senior Architect
(the learner) to produce the enterprise AI governance model:
the framework, the Architecture Review Board charter, the
investment-prioritisation model, the enterprise RACI, the
Board-level oversight model, and the compliance-and-audit
framework. The Chief Executive Officer, Chief Financial
Officer, General Counsel, Chief Information Security Officer,
and Head of Internal Audit must each sign the design; the
Board Strategy Committee and the Board Audit Committee both
ratify.

## The problem statement (what a senior architect is being asked to solve)

Design an enterprise AI governance model such that:

1. **A single scope definition tells any observer whether a
   given system is inside AI governance.** No decision falls
   between existing bodies because it meets none of their
   thresholds; no decision routes to three bodies because it
   meets three overlapping thresholds. The definition is
   published, argued, and re-examined at a defined cadence.
2. **Decision authority is enumerated by role and by decision
   class, not by seniority.** An engineering director cannot
   authorise a decision reserved for the Board and does not
   have to escalate a decision inside her own authority. A
   RACI exists that the Chief Financial Officer, the Head of
   Internal Audit, and a first-line engineering manager can
   each read the same way.
3. **The Architecture Review Board is the technical arbiter
   for AI architecture decisions, not an editorial committee.**
   ARB decisions are binding on the classes named. ARB
   composition is designed against capture by any single
   business unit or any single technical faction.
4. **Investment prioritisation runs against a portfolio model,
   not against loudest-voice submissions.** AI-adjacent spend
   is visible in one place, categorised, and prioritised
   against argued strategic criteria. The Chief Financial
   Officer can defend the AI portfolio composition to the
   Board Audit Committee without recourse to individual
   project narratives.
5. **Board-level oversight is instrumented, not narrative.**
   The Board and its committees see a defined AI-oversight
   dashboard, on a defined cadence, drawn from records
   outside the AI programmes themselves. Deep-dive reviews
   are triggered by defined thresholds, not by the Chair's
   discretion alone.
6. **Compliance and audit have a walkable path.** External
   audit and internal audit can trace any AI system from the
   Board oversight minute to the artifact in a bounded number
   of hops. Evidence is generated as a by-product of the
   workflow, not assembled retroactively for the audit.
7. **The five existing governance bodies interoperate without
   conflict.** The Responsible AI Board (Project 403), the
   Innovation Portfolio Board (Project 404), the External
   Voice Review Board (Project 405), the platform Architecture
   Review Board, and the enterprise-level AI Governance
   Committee each have defined authority, defined interfaces,
   and defined escalation paths to the Board.
8. **The model is auditable, defensible, and survives
   personnel change.** No named individual is load-bearing.
   Every role has a named successor. The framework itself is
   reviewed and re-approved on a stated cadence.

## Deliverables the learner submits

1. **Enterprise AI governance framework**
   (`framework/enterprise-ai-governance-framework.md` or
   equivalent). The reference artifact this repository ships.
   Includes the scope definition, the governance principles,
   the governance-body topology, the decision-class model, the
   investment-prioritisation model, the Board-oversight model,
   the compliance-and-audit model, the enterprise policy
   register, and the framework-refresh cadence.
2. **Architecture Review Board charter**
   (`governance/architecture-review-board-charter.md` or
   equivalent). The AI Architecture Review Board — composition,
   authority, quorum, decision rights, escalation, standing
   agenda, conflicts of interest, and interaction with the
   Responsible AI Board, the Innovation Portfolio Board, the
   External Voice Review Board, and the Board Audit and
   Strategy Committees.
3. **Enterprise RACI for AI decisions**
   (`governance/decision-authority-raci.md` or equivalent).
   The decision-class model matrixed against Responsible,
   Accountable, Consulted, Informed roles for each decision
   class. Explicitly names the escalation path and the
   fallback where a role is unfilled.
4. **Investment-prioritisation and portfolio-management
   model.** A section within the framework. The portfolio
   categorisation, the criteria against which spend is
   prioritised, the funding-tier model, the review cadence,
   and the interaction with the Chief Financial Officer's
   capital-planning process.
5. **Board-level oversight model.** A section within the
   framework. The Board and Board-committee-level AI-
   oversight dashboards, the cadence of AI reporting to each
   committee, the deep-dive-trigger thresholds, and the
   escalation-to-Board rules.
6. **Compliance-and-audit framework.** A section within the
   framework. The regulatory-obligation map, the evidence-
   generation model, the internal-audit programme for AI,
   the external-audit readiness posture, and the finding-
   remediation workflow.
7. **Roadmap and risk register.** Twelve-to-twenty-four-month
   sequenced roadmap and a top-ten risks register with
   probability, impact, mitigation, and residual risk. Must
   include: overlapping-body capture, unfilled-decision gap,
   Board-oversight-theatre, prioritisation-by-loudest-voice,
   audit-finding-cascade, framework-inertia, and personnel-
   dependency risks.

## Explicitly out of scope

- **The AI systems themselves.** How Halcyon builds, trains,
  and operates a specific AI system is Project 402 (platform)
  and Project 403 (responsible-AI) scope. This project
  governs the decisions about AI systems, not the systems.
- **General enterprise corporate governance.** Halcyon's
  overall Board committee structure, delegation of authority
  matrix, and financial-approval limits are the Company
  Secretary and CFO scope. This project's decision authority
  and RACI compose with those, not replace them.
- **Domain-specific regulatory compliance.** Halcyon's
  compliance with sector-specific regulation (machinery
  safety, functional safety, industrial cybersecurity,
  environmental) is those functions' scope. The AI-governance
  framework interfaces with them and does not duplicate them.
- **HR governance of individual AI-team performance.**
  Compensation, performance management, and organisational
  design within AI teams are HR and line-management scope.
  The framework names roles; it does not run performance
  reviews.
- **Data governance and privacy programme.** Halcyon's data
  governance and privacy programme (data classification,
  retention, consent, DPIA process) sits under the Chief
  Data Officer and Chief Privacy Officer. The framework
  references them, integrates with them at defined points,
  and does not redesign them.
- **Individual model risk-management practice.** The
  practitioner-level model risk-management workbench, model
  cards, evaluation harness, and monitoring instrumentation
  are engineering practice governed by the Responsible AI
  Board (Project 403) at the framework level and by AI
  platform teams at the operational level. This project
  governs the fact that model risk management exists and is
  audited; it does not redesign the practice.

## What "senior architect quality" means for this project

A junior submission gives you a governance chart with boxes
and arrows and an ARB "committee." A senior submission gives
you an enterprise AI governance model whose scope a Chief
Financial Officer can defend to the Board Audit Committee,
whose decision authority a General Counsel can point to when
a director asks "who approved this," and whose compliance-
and-audit path an external auditor can traverse from Board
minute to artifact in one review pass.

- **Scope is defined and defended.** The reference framework
  takes a position on what counts as "an AI decision inside
  enterprise AI governance" and defends the boundaries. A
  submission that leaves scope to "we'll figure it out" is
  scored below one that gets scope wrong in a defended way.
- **Decision authority is enumerated by class, not by
  seniority.** No senior-architect submission where "the CTO
  approves AI decisions" is a decision-authority statement
  reaches Board sign-off. Decision classes are named; the
  authority for each class is enumerated; the escalation
  path is defined.
- **Bodies compose, they do not overlap.** The reference
  model preserves the four existing bodies (Responsible AI
  Board, Innovation Portfolio Board, External Voice Review
  Board, Architecture Review Board) and defines their
  interfaces. A model that centralises all AI decisions in
  a new single body is scored below one that defends the
  existing bodies' scopes.
- **Investment prioritisation is portfolioed.** The reference
  model runs the AI spend as a portfolio with argued
  categorisation and prioritisation. A model that runs it
  as an approval queue against a threshold is scored lower.
- **Board oversight is instrumented.** The reference model
  gives the Board a defined dashboard fed from records
  outside the AI programmes. A model whose Board reporting
  is narrative-only ("the CTO tells the Board how AI is
  going") is scored below the level.
- **Audit evidence is a by-product.** The reference workflow
  produces the audit evidence as it goes; audit does not
  trigger a data-gathering exercise. Frameworks whose audit
  posture is "we could produce evidence if asked" score
  below those whose evidence is already produced.
- **The framework survives leadership rotation.** If the
  current CIO leaves next quarter, the framework continues.
  Named-person dependencies are a design defect.

The reference solution in `SOLUTION.md` is not a scoring key
with a single right answer. It is a set of trade-offs a
senior architect should be able to defend on their feet in
a Board Audit Committee session.

## Evaluation

See `rubric/evaluation-rubric.md` for the scoring rubric.
The rubric weights **defensibility of the scope definition**
and **enforceability of the decision-authority model** above
**breadth of governance-body coverage**. A learner who
submits a governance chart with fifteen bodies and no
defended decision-authority model will score below a learner
who submits five bodies with defended scopes and a working
RACI.

## Reading order

1. `README.md` (this file) — the scenario and the ask.
2. `SOLUTION.md` — the senior-architect reasoning the
   reference model encodes.
3. `framework/enterprise-ai-governance-framework.md` — the
   reference framework artifact.
4. `governance/architecture-review-board-charter.md` — the
   reference AI Architecture Review Board charter.
5. `governance/decision-authority-raci.md` — the reference
   enterprise RACI.
6. `rubric/evaluation-rubric.md` — the scoring rubric graders
   use.

## Version

**Version**: 1.0
**Status**: Reference solution
**Owner**: Senior Architect curriculum track
