# Thought Leadership Programme Design — Halcyon Industrial Group

> Operational companion to
> `projects/project-405-industry-thought-leadership/SOLUTION.md`.
> The SOLUTION document defends *why* the programme is shaped
> this way; this document specifies *how* it runs. A senior
> architect submits both.

## 0. How to use this document

Section 1 restates the thesis and the audience map as anchors.
Section 2 specifies the surfaces map and voice catalogue.
Sections 3–6 specify the four operating models (standards,
analyst relations, executive briefings, community and open
source). Section 7 specifies the review workflow. Section 8
specifies the metrics scorecard. Section 9 specifies roles,
staffing, and budget. Section 10 specifies the risk register.
Appendices carry the reusable templates: standards-membership
argument, community-contribution argument, executive-briefing
intake form, and paid-research authorisation.

## 1. Thesis and audience map

### 1.1 Thesis

Restated from SOLUTION §2.1:

> *Halcyon's external voice on AI exists to make the standards,
> analyst categorisations, and hiring pipelines that will shape
> industrial-AI competition over the next decade line up with
> Halcyon's engineering positions. The programme spends its
> scarce assets — named spokespeople, standards seats, and
> executive-briefing time — where Halcyon has substantive
> engineering positions that other actors do not, and stays
> silent where it does not. The programme's audience is
> technical decision-makers at Halcyon's customers, standards
> participants who influence Halcyon's cost of compliance, and
> senior applied-AI engineers Halcyon needs to hire — not the
> general public and not the consumer-AI press.*

### 1.2 Audience map

| Audience | Primary surfaces | Rationale |
|---|---|---|
| Technical decision-makers at Halcyon's customers (engineering VPs, chief plant engineers, industrial-AI leads at Fortune 2000 industrials) | Executive briefings, technical publications, industry-conference keynotes, customer advisory boards | Direct-revenue-adjacent; buyers who move on argued technical positions, not press headlines |
| Standards participants (working-group members at ISO/IEC JTC 1/SC 42, IEC TC 65, IEEE AI working groups) | Standards positions, working-group participation, public consultation responses | Cost-of-compliance-adjacent; positions here shape how Halcyon operates for years |
| Industrial-AI analyst firms (Tier 1 and Tier 2 named list) | Analyst briefings, paid research (bounded), analyst-attended events | Buyer-influence-adjacent; analyst-report placements shape customer shortlists |
| Senior applied-AI engineers Halcyon wants to hire | Technical publications, refereed conferences, open-source contributions, engineering-manager technical talks | Hiring-signal-adjacent; the labour market is thin and heavily influenced by public technical reputation |
| Regulators and policy actors (EU Commission, national regulators in operating regions) | Public consultation responses, invited testimony, position papers | Regulatory-cost-adjacent; Halcyon's positions here interact with Project 403 |
| Deliberately not primary audiences | General AI press, consumer-AI social platforms, retail-investor audiences | Off-thesis; content that reaches these audiences is a side-effect, not a target |

## 2. Surfaces map and voice catalogue

### 2.1 Surfaces map (operational form)

| Surface | Content class examples | Primary review tier | IP posture | Archive location |
|---|---|---|---|---|
| Standards positions | Draft position papers, working-group meeting inputs, public consultation responses | C (new positions); B (revisions) | Section 5 IP posture per body | Standards archive; delegate-owned |
| Analyst briefings | Prepared briefing narrative, briefing hand-outs | B (new narrative); A (reused narrative) | Standard IR posture; no unpublished-product-roadmap content unless under analyst NDA | Analyst-Relations archive; AR-manager-owned |
| Analyst paid research | Commissioned research narrative, review comments | C | Case-by-case; disclosed sponsorship | Analyst-Relations archive; AR-manager-owned + Legal-owned copy |
| Executive briefings | Executive Briefing Centre curriculum modules, session decks, session hand-outs | B (new modules); A (reused modules); C (curriculum updates) | Customer-attributable content requires customer sign-off | Executive Briefing Centre archive; EBC-manager-owned |
| Technical publications | Refereed papers, industrial-track workshop papers, technical blog posts | B (new); A (reused with attribution) | Section 6 IP posture; publication window per Project 404 IP strategy | Technical Publications archive; Editorial-lead-owned |
| Third-party conference talks | Invited keynotes, panel appearances, workshop talks | B (new content); A (reused content) | Section 6 IP posture; unreleased-product content prohibited | Speaker-Programme archive; Programme-manager-owned |
| Community and open source | Above-threshold contributions, maintainer decisions, community-consortium participation | B (above threshold); A (below threshold); C (new project engagement or maintainer commitment) | Section 6 IP posture; per-project licence audit | Open-Source Programme Office archive; OSPO-lead-owned |
| Executive communications | CEO/CTO/CPO interviews, press statements, investor-day AI content, keynote presentations to non-technical audiences | C | Investor-Relations posture where applicable | Communications archive; VP-Communications-owned |

### 2.2 Voice catalogue (operational form)

Halcyon maintains a named catalogue of voices in a controlled
document reviewed at the annual thesis-review cycle. The
catalogue records for each voice: name, role, surfaces
authorised, standards-body delegate seats held (if any),
executive-sponsor rotation involvement (if any), community-
steward roles held (if any), and named successor(s) where
applicable.

The catalogue is scoped to voices operating on programme
surfaces at Halcyon expense. Personal channels are covered by
the Employee External Communications Conduct Policy (see §7.6),
not the catalogue.

**Named-role classes:**

| Class | Surfaces authorised | Preparation time budget | Rotation cadence |
|---|---|---|---|
| Executive voice (CEO, CTO, CPO, CFO, CISO, CMO) | Executive communications, press, executive briefings, keynote by invitation | Up to 15% of time on programme content annually; per-event preparation with Communications | 24 months per executive-sponsor rotation for Executive Briefing Centre |
| Distinguished / Principal technical voice | Standards, technical publications, keynote by invitation, community stewardship above threshold | Up to 20% of time on programme content annually; standards-delegate role budgets to 25% | 36 months per standards-body delegate rotation (with delegate handover) |
| Engineering-manager / staff engineer voice | Technical publications, community contribution below threshold, standards working-group member roles (supporting a Principal delegate), analyst briefings by nomination | Up to 10% of time on programme content annually | 24 months in any given standing role |
| Individual-contributor engineer voice | Technical publications (co-author), community contribution in defined categories, technical-conference presentation by nomination | Up to 8% of time on programme content annually | 12 months in any given standing role |
| Communications / analyst-relations professional voice | Analyst-relations coordination, press coordination, executive-communications preparation | Full-time on programme; no rotation | n/a |

## 3. Standards-participation model (operational)

### 3.1 Active membership list

The reference active membership list for Halcyon:

| Body | Working groups | Delegate class | Named delegate (role) | Argued reason (see Appendix A) | Exit criterion |
|---|---|---|---|---|---|
| ISO/IEC JTC 1/SC 42 | WG 1 (foundational), WG 2 (data), WG 3 (trustworthiness), WG 4 (use cases and applications) as topical | Distinguished / Principal | Chief AI Scientist (with named successor: Principal Research Engineer, Trustworthy AI) | Non-negotiable: 42001, 23894, 42005 shape Halcyon's cost of compliance | Standards suite completes and enters maintenance-only cadence |
| IEC TC 65 / SC 65A | Functional-safety subgroups relevant to AI components in safety-critical loops | Distinguished / Principal | Chief Safety Engineer (with named successor: Principal Systems Engineer, Safety-Critical Controls) | Non-negotiable: Halcyon's control-loop safety positions are here | Halcyon exits safety-critical product surfaces (does not) |
| IEC TC 65 / SC 65E | Industrial-cybersecurity subgroups relevant to AI-adjacent industrial systems | Principal | Principal Security Engineer, Industrial Cyber (with named successor: CISO delegate) | Non-negotiable: IEC 62443 family binds Halcyon | See above |
| ISO/IEC JTC 1/SC 27 | Selective participation on AI-security-overlap topics | Principal | CISO delegate (rotating principal) | Argued: participation only where AI overlap is substantive | Overlap topics no longer active in the standard |
| IEEE Standards Association | Ethically-aligned design working groups where Halcyon has an engineering position; industrial-AI audit-standard efforts | Distinguished / Principal, per WG | Named per working group | Argued: participate only where Halcyon carries a substantive engineering contribution | Working-group scope drifts off Halcyon interest |

**Deliberate non-membership** (with archived arguments):

- Consumer-facing AI content-moderation standards bodies.
- General-purpose AI-governance forums whose output is
  political declarations rather than technical standards.
- Marketing-driven industry consortia without a working-group
  deliverable programme.
- Regional industry consortia in markets Halcyon does not
  operate in.

### 3.2 Delegate policy

- Every standards-body delegate is named in writing with a
  named successor.
- Delegates prepare positions in writing before the meeting,
  reviewed at Tier B or C per position criticality.
- Delegates archive meeting minutes and positions taken within
  five business days of the meeting.
- Delegate rotation runs on a 36-month cadence unless the
  delegate-in-seat requests continuation for a specific working-
  group cycle (approved by External Voice Review Board).
- Delegate exit from Halcyon triggers the named-successor
  clause; the successor takes seat within thirty days.

### 3.3 IP posture per body

Each body's IP posture is defined in a controlled document
maintained jointly by the External Voice Review Board's Legal
delegate and the Project 404 IP portfolio owner. Standard
elements per body:

- RAND / FRAND declaration posture for standards-essential
  patents.
- Declaration cadence and reviewer.
- Non-assertion covenant posture for reference implementations
  Halcyon publishes.
- Cross-licensing posture for standards-essential patents
  Halcyon holds.

Changes to the IP posture are Tier C and require Board Strategy
Committee liaison notification.

## 4. Analyst-relations model (operational)

### 4.1 Analyst tiering

Analysts are tiered by their influence on Halcyon's buyer
population. Tiering is reviewed annually.

| Tier | Cadence | Content pipeline | Reviewer |
|---|---|---|---|
| Tier 1 (2–5 named analysts covering industrial-AI intersection at tier-one firms) | Quarterly briefing | Prepared narrative refreshed quarterly; reviewed at Tier B | AR manager + Distinguished technical voice |
| Tier 2 (5–10 named analysts covering adjacent markets) | Semi-annual briefing | Prepared narrative refreshed semi-annually; reviewed at Tier B | AR manager + engineering-manager voice |
| Tier 3 (5–15 named analysts covering peripheral markets) | Annual briefing | Prepared narrative refreshed annually; reviewed at Tier A | AR manager |
| Unlisted analysts | Response-only; no outbound briefing | Standard AR intake | AR manager decides case-by-case |

### 4.2 Briefing operating model

- Each briefing runs against a Halcyon-prepared narrative, not
  against analyst-supplied questions.
- The narrative is delivered by a technical voice (Distinguished,
  Principal, or engineering-manager) with an AR-manager
  facilitator.
- Executive voices deliver briefings selectively for Tier 1
  strategic narratives once per cycle.
- Briefings are logged in the AR archive with attendees, date,
  narrative version, and any commitments made.
- Analyst-quoted Halcyon language is monitored via the AR
  archive against briefings-of-record.

### 4.3 Paid-research authorisation

Paid research is authorised in a quarterly batch by the
External Voice Review Board. Each proposal is presented with
the Appendix D template:

- Research question / audience-decision the research informs.
- Chosen analyst firm; disclosed sponsorship posture.
- Halcyon-owned content contribution; analyst-owned
  independence.
- Publication timing and target audience.
- Budget and cost-comparison alternatives.
- Cannibalisation / conflict check against other Halcyon-paid
  research in flight.

Paid-research artifacts carry disclosed-sponsorship badges per
the analyst firm's ethics policy.

### 4.4 Rules the AR programme does not blur

- Briefings, paid research, and speaking / consulting
  engagements are separate instruments with separate contracts
  and separate disclosures.
- Halcyon does not offer commercial incentives to influence a
  briefing outcome.
- Halcyon does not attribute paid-research quotes as unbiased
  third-party statements in Halcyon-produced marketing.

## 5. Executive-briefing model (operational)

### 5.1 Executive Briefing Centre curriculum

The Executive Briefing Centre operates against a curriculum of
between five and nine modules at any time. Reference modules:

| Module | Owner | Target duration | Review cadence |
|---|---|---|---|
| Industrial-AI market context and Halcyon's thesis | Chief Product Officer + CTO delegate | 60 minutes | Semi-annual |
| Halcyon platform overview and AI-in-product roadmap (public content only) | CPO delegate | 60 minutes | Quarterly |
| Responsible AI at Halcyon (Project 403 narrative) | Chief AI Ethics Officer | 45 minutes | Semi-annual |
| Standards, compliance, and audit posture | General Counsel delegate + Standards delegate | 45 minutes | Semi-annual |
| Customer-adoption playbook (Halcyon platform on-boarding) | Chief Customer Officer delegate | 60 minutes | Quarterly |
| Technical deep-dives per platform capability (rotating) | Distinguished technical voice per topic | 30–60 minutes | Semi-annual per module |
| Innovation programme narrative (Project 404 posture) | Chief AI Scientist | 30 minutes | Annual |

### 5.2 Intake criteria

The Executive Briefing Centre programme manager accepts intake
against three criteria (weighted; two of three required):

- **Customer strategic importance.** Named on the Chief
  Customer Officer's strategic-accounts list, or plausible
  member of it within twelve months.
- **AI adoption horizon.** Customer has a named AI adoption
  initiative in their published roadmap or in a documented
  sales-qualified opportunity.
- **Specific question.** The customer asks for one of the
  curriculum modules or a documented variant.

Declined intakes receive: (a) a briefing handout drawn from
the relevant module; (b) an invitation to a scheduled Halcyon
webinar; or (c) a referral to a technical-conference talk
Halcyon has delivered on the topic.

### 5.3 Executive sponsor rotation

- The Executive Briefing Centre executive-sponsor role rotates
  on an 18-month cadence.
- Rotation is between CTO, CPO, CFO (for AI-financial
  briefings), and CISO (for security-audience briefings), on
  a schedule approved annually.
- The prior sponsor participates in the incoming sponsor's
  first three sessions as a briefing-continuity handover.

### 5.4 Post-briefing artifact hand-off

Every completed briefing produces:

- A briefing-of-record entry: attendees, curriculum modules
  used, technical voices delivering, specific customer
  questions and answers, any commitments made.
- A hand-off to the sales team with the briefing-of-record and
  a next-action recommendation.
- A hand-off to the AR archive of any analyst-attended or
  analyst-adjacent content used, so the AR programme can
  reconcile against briefing narratives.

The programme's obligation ends at hand-off. The sales
conversation is sales' scope.

## 6. Community and open-source model (operational)

### 6.1 Contribution registry

Halcyon operates a Community and Open-Source Programme Office
(OSPO) that maintains a registry of Halcyon contributions
above threshold. Each registry entry:

- Project name and licence.
- Contribution category (Infrastructure, Benchmark and
  Evaluation, Standards-Reference-Implementation, Community-
  Good).
- Named contributor(s); Halcyon-time vs. personal-time.
- Argued case (Appendix B).
- IP interaction assessment (Project 404 IP portfolio).
- Named maintainer commitment (if applicable).
- Community-steward role (if applicable).

Contributions below threshold (small bug fixes, documentation
patches, community-good contributions to approved projects) do
not require registry entries but are covered by the standing
Tier A review workflow.

### 6.2 Above-threshold definitions

A contribution is above threshold if any of the following are
true:

- The contribution creates a maintainer commitment for Halcyon.
- The contribution touches Halcyon IP that has been declared
  standards-essential or defensively-filed.
- The contribution creates a new engagement with a project
  Halcyon has not previously contributed to.
- The contribution exceeds a per-project effort threshold set
  by OSPO (typical default: 40 engineer-hours in a rolling 90-
  day window on one project).

### 6.3 Approved-project list

OSPO maintains an approved-project list. Projects on the list
have already been evaluated against the argued-case criteria at
a category level. Contributions to approved projects run at
Tier A (below-threshold) or Tier B (above-threshold) without
requiring a fresh new-project argument.

Projects not on the list require a new-project argument
(Appendix B) approved at Tier B or C depending on strategic
weight.

### 6.4 Community-steward role model

Halcyon employees serving as maintainers, technical steering
committee members, or programme committee members on external
community projects:

- Are named in the voice catalogue.
- Have their community-steward role time budgeted (typical
  default: 10–20% of role time).
- Serve at Halcyon expense on approved projects only.
- Have named successors on high-consequence stewardship
  roles (e.g., a technical steering committee seat on an ML
  compiler Halcyon depends on).

### 6.5 Employee personal-time contribution policy

- Employees may contribute to open-source projects on personal
  time subject to the Employee External Communications Conduct
  Policy.
- Personal contributions are not covered by Halcyon IP
  indemnification.
- Contributions to Halcyon-competitive projects on personal
  time follow Halcyon's standard employment terms.

## 7. Review workflow (operational)

### 7.1 Tier definitions (operational form)

Restated from SOLUTION §2.4 with operational specifics.

| Tier | Target latency | Standing reviewers | Required sign-offs |
|---|---|---|---|
| A — Standing | 24–72 hours | Rotating technical lead + Communications designee | Technical lead + Communications designee |
| B — Substantive | 3–10 business days | Review Board subset: relevant technical voice, Communications, Legal, Security | All four |
| C — Full board | 5–15 business days | Full Review Board convenes; Board Strategy Committee liaison informed | All Board members + Board Strategy Committee liaison acknowledgement |
| D — Emergency | Same business day (typ.) | Review Board on-call rota + General Counsel + Communications lead | On-call reviewer + General Counsel |

### 7.2 Submission process

Content submitters use a single intake portal with:

- Artifact type (surface + content class).
- Content itself (draft, with prior-versions history for
  revisions).
- Proposed publication surface and date.
- Reused-material flag (identifies re-use of previously-
  approved content, which drops the review to Tier A).
- Confidential-material flag (unreleased-product references,
  customer-attributable material, security-sensitive
  material, standards-body internal deliberations).

Confidential-material flag triggers automatic escalation to
Tier B minimum regardless of content class.

### 7.3 Reviewer assignment

- Tier A: automatic assignment to rotating on-call reviewers.
- Tier B: automatic assignment to Communications, Legal,
  Security, and the relevant Halcyon business-unit voice, with
  rotation for load balancing.
- Tier C: Review Board convenes at the next standing meeting
  or emergency session per criticality.
- Tier D: Review Board on-call rota takes the review; General
  Counsel and Communications lead engage in real time.

### 7.4 Reviewer criteria

Each Tier B/C review captures:

- Reviewer identity and role.
- Time spent on review.
- Comments and their disposition (resolved / rejected /
  deferred with reason).
- Approval / rejection / conditional-approval with conditions.
- Archival version of the approved content.

Reviews with unresolved comments do not close.

### 7.5 Archive

The review archive is the source of truth for what was
published. Archive is:

- Retained for a defined retention window (default: seven
  years from publication).
- Auditable by the Review Board, Board Strategy Committee, and
  external audit on request.
- Structured so that a published artifact can be resolved to
  its approved version, its reviewers, and its conditions in
  under fifteen minutes.

### 7.6 Employee External Communications Conduct Policy interaction

The Employee External Communications Conduct Policy is a
standing HR / Legal / CISO artifact covering:

- What Halcyon-attributable information may not appear on
  personal channels (unreleased-product roadmaps, customer
  attribution, security-sensitive material, standards-body
  internal deliberations).
- How to represent employment relationship on personal
  channels.
- How to disclose Halcyon employment when contributing to
  external forums outside the programme.

The Review Board does not adjudicate personal-channel content.
Alleged conduct-policy violations follow HR / Legal / CISO
process; the Review Board is a stakeholder in remediation
where the incident touches a programme surface.

## 8. Metrics scorecard (operational)

### 8.1 Headline metrics — definitions and sources

| Metric | Definition | Source | Reporting frequency |
|---|---|---|---|
| Standards positions adopted | Count of Halcyon-contributed positions adopted (in whole or substantive part) into standards drafts or final standards in the period | Standards-body meeting minutes; delegate reports validated against archive | Quarterly to Board Strategy Committee |
| Analyst-report placement outcomes | Movement of Halcyon in named analyst-report positioning in the period | Analyst firm published reports | Quarterly |
| Hiring signal attributable to programme output | Applicants / offers-accepted citing named Halcyon programme output as their reason for applying | HR structured intake data | Semi-annual |
| Executive briefing conversion | Customers who completed EBC in the period and progressed on a named platform-adoption path within two quarters | Sales-operations attribution | Semi-annual |
| Review-workflow adherence | Proportion of external artifacts published in the period that went through the correct review tier with reviewer sign-offs on file | Review archive audit | Quarterly |

### 8.2 Hygiene metrics — definitions and sources

| Metric | Definition | Source | Reporting frequency |
|---|---|---|---|
| Content-pipeline volume | Counts per surface (standards positions, briefings, publications, community contributions, executive briefings) | Programme registries | Semi-annual |
| Review cycle time | Distribution per tier; % meeting target latency | Review archive | Semi-annual |
| Voice-catalogue distribution | Named voices appearing on programme surfaces in the period | Programme registries | Annual |
| Incident count | External artifacts requiring correction / retraction / embargo revision, with root cause | Incident log | Semi-annual |

### 8.3 Metrics not counted (headline)

Explicitly excluded from headline reporting:

- Impressions, followers, social-media reach.
- Keynote count, conference-attendance count.
- Open-source pull-request count.
- Press mentions (raw count including negative and irrelevant).

These metrics may appear in hygiene or diagnostic form but do
not appear on the Board scorecard.

## 9. Roles, staffing, and budget

### 9.1 Reference staffing model

For a Halcyon-scale organisation:

| Role | FTE (reference) | Reporting line | Notes |
|---|---|---|---|
| Programme Director | 1.0 | CMO | Convenes the Review Board; owns the operating cadence |
| Communications operator (Review Board seat) | 1.0 | Programme Director | Executes the workflow; does not vote on technical positions |
| Analyst Relations Manager | 1.0 | Programme Director | Owns analyst list, briefing cadence, paid-research proposals |
| Executive Briefing Centre Manager | 1.0 | Programme Director | Owns curriculum, intake, sponsor rotation |
| Open-Source Programme Office (OSPO) Lead | 1.0 | Programme Director (dotted line to CTO) | Owns contribution registry, above-threshold review |
| Technical Publications Editorial Lead | 0.5–1.0 | Programme Director | Owns technical-publication pipeline |
| Standards Programme Coordinator | 0.5 | Programme Director (dotted line to General Counsel for IP posture) | Owns the standards-body register and delegate policy |
| Legal delegate (Review Board seat) | 0.25 | General Counsel | Review Board Legal voice |
| Security delegate (Review Board seat) | 0.25 | CISO | Review Board Security voice |
| IP delegate | 0.25 | General Counsel / Chief IP Counsel | IP posture per body; interacts with Project 404 IP strategy |
| Distinguished / Principal technical voices | 0.15–0.25 per named voice | Their engineering line-manager | Time on programme content per §2.2 |
| Executive voices | 0.10–0.15 per named executive | n/a | Time on programme content per §2.2 |

### 9.2 Reference budget breakdown

Programme budget is expressed as a percentage of the AI
Innovation Programme budget (Project 404) plus incremental
line items. Reference default:

- Staffing (§9.1) — 55%.
- Standards-body membership fees, delegate travel, position
  drafting — 10%.
- Analyst-relations paid research (bounded per §4.3) — 10%.
- Executive Briefing Centre operations (venue, hospitality,
  content production) — 10%.
- Community and open-source programme (sponsorships,
  conference booths where the programme is speaker-first
  and booth-second) — 5%.
- Content production and archival tooling — 5%.
- Contingency (Tier D response, unanticipated regulatory
  consultation) — 5%.

Approved annually by CFO; variance above 15% requires re-
approval.

## 10. Risk register (top ten)

| # | Risk | Probability | Impact | Mitigation | Residual |
|---|---|---|---|---|---|
| 1 | Uncontrolled disclosure of unreleased-product roadmap on programme surface | Medium | High | Confidential-material flag in intake auto-escalates to Tier B+; Legal review non-optional at Tier B/C | Low |
| 2 | Standards-body capture — a Halcyon delegate advocates a position not aligned with the argued Halcyon posture | Low | High | Delegate policy requires written prepared positions; review at Tier B/C prior to meeting; post-meeting minutes reviewed | Low-Medium |
| 3 | Analyst-report backfire — a paid-research artifact positions Halcyon poorly against the strategic argument | Medium | Medium | Paid-research authorisation quarterly with argued case; analyst independence recognised; publication timing checked against sensitive Halcyon events | Medium |
| 4 | Community-project abandonment — Halcyon merges an above-threshold contribution and then de-staffs the maintainer commitment | Medium | Medium | Named maintainer commitment required; OSPO monitors ongoing commitments; commitment de-scoping requires Tier B review | Low |
| 5 | Executive-sponsor departure mid-cycle from Executive Briefing Centre | Medium | Medium | Rotation model with named successor; prior sponsor's first-three-session handover; curriculum ownership at role level, not sponsor level | Low |
| 6 | Goodhart-style optimisation of vanity metrics displacing thesis-aligned activity | Medium | Medium | Vanity metrics not in headline scorecard; annual scorecard review; headline metrics sourced outside programme | Low |
| 7 | Named-person dependency — Halcyon's external voice on AI becomes one Distinguished engineer's persona | Medium | High | Voice catalogue distribution monitored; standards-delegate rotation on 36-month cadence; multiple voices trained per surface | Medium |
| 8 | Review workflow overhead drives around-the-workflow publishing on personal channels | Medium | Medium | Tier A latency defended; personal channels governed by conduct policy not workflow; friction complaints escalated to Programme Director for tier-appropriate response | Medium |
| 9 | Regulatory-consultation deadline exceeds Tier C latency | Low | High | Regulatory-consultation intake flagged with deadline; Tier D can be invoked for deadline reasons; standing calendar of expected consultations | Low |
| 10 | IP leakage through community contribution to a project that later relicenses or forks in a way that captures Halcyon-strategic material | Low | High | OSPO categorises contributions with IP interaction assessment; contributions to projects with known governance instability are declined; contributions with strategic IP interaction require Tier C new-project argument | Low |

## Appendix A — Standards-membership argument template

```
Body: <standards body / working group>
Named delegate: <role> (named successor: <role>)
Substantive engineering position Halcyon carries into this body:
  - <one paragraph, defensible under cross-examination>
Cost-of-compliance impact if the standard is written against
  Halcyon's constraints:
  - <named product lines, ordered by magnitude>
IP posture:
  - <RAND/FRAND declaration posture; non-assertion covenants;
    cross-licensing posture>
Membership term:
  - <initial commitment; renewal cadence; exit criterion>
Prior positions on file:
  - <archived positions, delegate reports, meeting minutes>
```

## Appendix B — Community-contribution argument template

```
Project name and licence:
  <name; SPDX identifier>
Contribution category:
  <Infrastructure | Benchmark & Evaluation |
   Standards-Reference-Implementation | Community-Good>
Strategic effect on Halcyon:
  <direct or externality; magnitude estimate>
Licence exposure and IP interaction:
  <interaction with Project 404 IP strategy; audit sign-off>
Named maintainer commitment:
  <if applicable: named engineer, time budget, term>
Community-steward role:
  <if applicable: role held, term, named successor>
Below-threshold contribution note (if applicable):
  <why below threshold; approved-project reference>
```

## Appendix C — Executive Briefing Centre intake form

```
Requesting sales-account owner:
  <name; account>
Customer entity:
  <named customer>
Customer strategic-account status:
  <Tier 1 | Tier 2 | Tier 3 | not on list>
Customer AI adoption horizon:
  <named roadmap item; SQO reference>
Requested curriculum module(s):
  <module name(s); custom deep-dive request if any>
Requested date range:
  <two-week window preferred>
Confidential material anticipated:
  <yes/no; if yes, list>
Post-briefing action expected:
  <RFP participation; commercial pilot; adoption decision>
```

## Appendix D — Paid-research authorisation template

```
Research question / audience-decision informed:
  <one paragraph>
Chosen analyst firm and disclosed sponsorship posture:
  <firm; disclosure form>
Halcyon-owned content contribution:
  <named content; author(s)>
Analyst-owned independence:
  <how analyst independence is preserved; editorial control>
Publication timing:
  <expected publication date; embargo window>
Target audience:
  <analyst firm's audience; Halcyon distribution posture>
Budget and cost-comparison alternatives:
  <cost; alternatives considered; why paid research is the
  right instrument>
Cannibalisation / conflict check:
  <other Halcyon-paid research in flight; conflict assessment>
```

## Status

**Version**: 1.0
**Status**: Reference programme design
**Owner**: Senior Architect curriculum track
