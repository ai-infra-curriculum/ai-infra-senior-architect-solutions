# Project 405: Industry Thought Leadership Programme

> Senior-architect capstone. The learner submits an enterprise
> external-voice programme — thought leadership, standards
> participation, analyst relations, executive briefings, and
> community stewardship — that a Chief Marketing Officer, a
> General Counsel, and a Chief Information Security Officer can
> all sign off on without any one of them silently subsidising
> the risk they carry from the other two.

## Scenario (fictional)

**Halcyon Industrial Group** — the same fictional multinational
industrial-automation and electric-drives manufacturer used in
Projects 401–404 — has, over the last thirty-six months,
accumulated an external presence in AI that nobody at Halcyon
designed. A principal research engineer keynoted an industrial-AI
workshop and the deck circulated widely. The AI Lab director
sits on two standards working groups by personal invitation.
The Chief Product Officer has a monthly analyst call the AI Lab
does not attend. Two engineering directors publish on personal
blogs. Three engineers contribute to open-source projects on
Halcyon time under informal arrangements. A junior researcher
posted a training-data description on a social platform that
Legal is still unwinding. The Chief Marketing Officer's team
issues AI press statements the AI Lab first sees in the press.

None of this is scandalous. All of it is uncoordinated. The Board
Strategy Committee has asked, at the same review that approved
the Project 404 Innovation Programme, whether Halcyon's *external
voice on AI* is being managed as an asset or is drifting.

Three independent events force the design of a real thought-
leadership programme, not just a communications playbook:

- **Regulatory-standards drift.** ISO/IEC JTC 1/SC 42 (the joint
  AI standards committee) is producing standards that Halcyon
  will be audited against for years — 42001 (AI management
  systems, in force), 23894 (risk management), 42005 (impact
  assessment), and others. IEC 61508 and IEC 62443 working
  groups touch Halcyon's safety-critical and industrial-cyber
  surfaces. Halcyon has substantive engineering positions on
  the intersection of AI and safety-critical control loops. If
  those positions are not put in front of the working groups on
  a defensible cadence, the standards will be written against
  Halcyon's practical constraints and Halcyon will implement
  them at higher cost. Standards participation is now a cost-
  of-goods-sold decision, not a public-relations decision.
- **Analyst and buyer influence.** Halcyon's industrial customers
  increasingly ask analyst firms (Gartner, IDC, ARC Advisory
  Group, Forrester, Omdia) to categorise industrial-AI vendors.
  A "Visionary" placement in an analyst quadrant is worth more
  than a keynote. Analyst briefings are a discipline: the
  briefings themselves are unpaid, but analyst inquiries and
  paid research are separate instruments with separate rules.
  The Chief Marketing Officer's team is currently the sole
  interface to analysts; the AI Lab has never briefed one.
- **Contributor and hiring signal.** The AI engineering labour
  market is thin, expensive, and heavily influenced by public
  technical reputation. Halcyon's ability to attract senior
  applied-AI engineers, industrial-PhDs, and post-doctoral
  researchers now depends materially on whether Halcyon looks
  like an interesting place to do the work. Silence is a
  hiring cost.

The Board has asked the AI Infrastructure Senior Architect (the
learner) to produce the programme design, the external-voice
governance charter, the standards-participation model, the
analyst-relations model, the executive-briefing model, and the
community-and-open-source stewardship model. The Chief Marketing
Officer, General Counsel, and Chief Information Security Officer
must all sign the design; the Board Strategy Committee ratifies.

## The problem statement (what a senior architect is being asked to solve)

Design an enterprise industry-thought-leadership programme such
that:

1. **The programme has a written thesis.** Halcyon knows which
   external conversations it is trying to influence, which
   audiences it is trying to reach, and which conversations it
   is deliberately not entering. A Board member can ask "why is
   our chief scientist keynoting X and not Y?" and receive an
   argued answer.
2. **External voice is a governed function, not a discretionary
   one.** The set of Halcyon voices — executive, principal
   engineer, engineering-manager, IC — that speak publicly on
   AI is enumerated; the review path for what each says on
   which surface is defined; the artifacts are archived.
3. **Standards participation is scoped by argument.** Halcyon
   participates in standards bodies where its engineering
   positions are substantive; it does not participate for
   optics. Participation has named delegates, term limits,
   position preparation, dissent recording, and IP posture.
4. **Analyst relations run on a briefing cadence.** Halcyon
   maintains a named list of analysts covering the relevant
   markets, a briefing cadence per analyst, a defined content
   pipeline into briefings, and a clear separation between
   briefings and paid research.
5. **Executive briefings survive personnel change.** The
   Executive Briefing Centre — where Halcyon meets its largest
   customers and prospects on the AI story — runs to a
   published curriculum that outlasts the current executive
   sponsor.
6. **Community and open-source contributions are strategic.**
   Contributions to open-source AI infrastructure, evaluation
   harnesses, safety benchmarks, and industry consortia have
   written strategic arguments; they are not vanity
   contributions and they are not policy-by-manager-preference.
7. **The programme is auditable against legal, security, and
   competitive-intelligence risk.** Every external artifact
   passes a review appropriate to its surface. Confidential
   information, unreleased-product roadmaps, competitor-
   sensitive claims, and customer-attributable content have
   defined guardrails.
8. **The programme measures itself against influence, not
   noise.** Metrics count what actually moves the conversation
   Halcyon is trying to influence: adopted standards positions,
   analyst-report placements, hires attributable to public
   presence, customer-briefing conversion. Metrics do not
   headline vanity numbers (impressions, followers, event count)
   that trivially inflate under Goodhart's law.

## Deliverables the learner submits

1. **Thought-leadership programme design**
   (`program/thought-leadership-program-design.md` or
   equivalent). The reference artifact this repository ships.
   Includes the audience map, the surfaces map, the voice
   catalogue, the review workflow, the standards-participation
   model, the analyst-relations model, the executive-briefing
   model, and the community/open-source model.
2. **External-voice governance charter**
   (`governance/external-voice-charter.md` or equivalent). The
   External Voice Review Board — composition, authority,
   quorum, decision rights, escalation, standing agenda,
   conflicts of interest, and interaction with Legal, Security,
   and Communications.
3. **Standards-participation model.** A section within the
   programme. Which bodies Halcyon is a member of, why, at what
   level, with whom, on which working groups, with what IP
   posture. Includes the argued in/out list.
4. **Analyst-relations model.** A section within the programme.
   Analyst tiering, briefing cadence, content pipeline, paid-
   research posture, and the rules for what is said in a
   briefing versus what appears in a paid-research inquiry.
5. **Executive-briefing model.** A section within the programme.
   The Executive Briefing Centre curriculum, the executive
   sponsor rotation model, the intake criteria, the artifact
   handoff to sales, and the non-disclosure posture.
6. **Community and open-source model.** A section within the
   programme. Contribution categories, review criteria, IP
   posture (interaction with the Project 404 IP strategy),
   individual-contributor policy, and the community-steward
   role model.
7. **Metrics framework.** A section within the programme. What
   is counted, what is deliberately not counted, and how each
   metric is protected against Goodhart-style degradation.
8. **Roadmap and risk register.** Twelve-to-twenty-four-month
   sequenced roadmap and a top-ten risks register with
   probability, impact, mitigation, and residual risk. Must
   include: uncontrolled disclosure, standards-body capture,
   analyst-report backfire, community-project abandonment,
   executive-sponsor departure, and Goodhart-style vanity-
   metric optimisation.

## Explicitly out of scope

- **Product marketing.** How Halcyon markets a specific product
  is the Chief Marketing Officer's operational scope. The
  programme informs product-marketing narratives with technical
  content but does not run product-marketing campaigns.
- **Sales enablement.** Executive briefings interact with sales
  but are not sales meetings. Sales training on AI-content
  positioning is a sales-organisation deliverable that consumes
  programme artifacts.
- **Employer-brand management.** Recruiting-marketing (career
  pages, employer awards, campus-brand budgets) is HR's scope.
  Contribution and public-technical-reputation posture *does*
  interact with hiring signal — the programme names that
  interaction — but does not run recruiting campaigns.
- **Corporate communications crisis response.** The programme's
  guardrails prevent many crisis situations but the crisis
  response itself remains the Chief Communications Officer's
  scope, coordinated with Legal.
- **Corporate reputational-risk insurance.** Insurance instruments
  covering directors-and-officers, media-liability, and cyber-
  liability are the CFO / General Counsel scope.
- **Responsible AI content itself.** What Halcyon says publicly
  about its Responsible AI posture must reflect the actual
  Project 403 framework. The programme owns the *publication
  surfaces* for that content; it does not redesign the
  framework.

## What "senior architect quality" means for this project

A junior submission gives you a content calendar and a list of
conferences. A senior submission gives you an external-voice
programme whose claims a General Counsel could audit, a Chief
Information Security Officer could redirect, and a Chief
Marketing Officer could operate.

- **The programme has a thesis, not a slogan.** The reference
  programme takes a position on which conversations Halcyon
  intends to influence and defends the exclusions.
- **Every external artifact has a review path.** No senior-
  architect submission that says "engineers should feel free
  to publish on their own initiative" reaches Board sign-off.
  Freedom to publish exists; the review path is not optional.
- **Standards participation is argued.** The reference programme
  is a member of a bounded number of bodies for argued reasons
  and is deliberately not a member of others for argued
  reasons. Membership by inertia is not a strategy.
- **Analyst relations are professional, not defensive.** The
  reference programme runs analyst briefings on a cadence, not
  in response to a bad report.
- **Community contributions have strategic arguments.** Every
  contribution above a threshold has a written argument on file,
  reviewed by the External Voice Review Board.
- **Metrics reward influence, not activity.** The reference
  scorecard tracks adopted standards positions, analyst
  placements, technical-hire signal, and executive-briefing
  outcomes; it deliberately does not headline impressions.
- **The programme survives leadership rotation.** If the current
  CMO leaves next quarter, the programme continues. Named-
  person dependencies are a design defect.

The reference solution in `SOLUTION.md` is not a scoring key
with a single right answer. It is a set of trade-offs a senior
architect should be able to defend on their feet in a Board
Strategy Committee session.

## Evaluation

See `rubric/evaluation-rubric.md` for the scoring rubric. The
rubric weights **defensibility of the programme thesis** and
**enforceability of the review workflow** above **breadth of
external activity**. A learner who submits a plan for fifty
speaking engagements per year with no review workflow will score
below a learner who submits ten defended engagements per year
and a working review workflow.

## Reading order

1. `README.md` (this file) — the scenario and the ask.
2. `SOLUTION.md` — the senior-architect reasoning the reference
   programme encodes.
3. `program/thought-leadership-program-design.md` — the reference
   programme artifact.
4. `governance/external-voice-charter.md` — the reference
   External Voice Review Board charter.
5. `rubric/evaluation-rubric.md` — the scoring rubric graders use.

## Version

**Version**: 1.0
**Status**: Reference solution
**Owner**: Senior Architect curriculum track
