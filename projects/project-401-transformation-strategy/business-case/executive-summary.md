# Executive Summary — Enterprise AI Infrastructure Transformation

> Project 401 — Business case companion. Audience: CFO, COO, board, investment committee.
>
> One-page version on page 1. Detailed financial model in `../financial-model/` (planned). Risk analysis in `../risk-analysis/` (planned).

---

## The one-page version

**The problem.** Enterprise A's current AI/ML infrastructure is a portfolio of bespoke environments: 14 teams operate 11 different MLOps stacks, training jobs queue for an average of 9 hours, and the security audit identified 7 high-severity exceptions across the estate. Cost has grown 73% YoY while throughput (production model deployments) has grown 12%. Three product launches in the last fiscal year were delayed by infrastructure constraints; estimated revenue impact $42M.

**The proposal.** Consolidate to a single AI Infrastructure Platform over 24 months. Run as a Platform-as-a-Product organization (PaaP): central team owns the platform; product teams self-serve via paved roads. Outcomes:

| Outcome | Year 1 target | Year 2 target |
|---|---|---|
| Annual compute spend | -18% vs current | -34% vs current |
| Mean training queue time | < 1 hour | < 15 min |
| Time from model commit → production | < 2 days | < 4 hours |
| Production deployments / quarter | 2x current | 4x current |
| Security audit findings | 3 high (-57%) | 0 high |

**The investment.** $14.7M over 24 months: $9.2M Year 1 (build), $5.5M Year 2 (operate + scale). Breakdown: 58% personnel, 24% software/SaaS, 11% cloud infrastructure, 7% one-time professional services for migration.

**The return.** Steady-state savings of $11.8M/year by end of Year 2 (compute consolidation, eliminated bespoke tool licenses, reduced operational toil). Revenue protection of ~$30M/year from avoided launch delays. Net 24-month NPV (10% discount): $23.4M positive. Payback: 16 months.

**The risk.** Two risks rated high: (1) executive sponsorship change during the 24-month horizon would jeopardize completion; (2) reluctance from established teams to migrate could stall consolidation. Mitigations: 18-month sponsor commitment in writing, quarterly steering committee, and an opt-out gate at Month 12 that exits the program with $4.1M sunk if outcomes are not on track.

**The ask.** Approve $9.2M Year 1 funding and the staffing plan (28 net new FTEs across 4 quarters). Approve the program governance structure (steering committee, biweekly stakeholder review, monthly board update). Confirm executive sponsor commitment through Q4 next fiscal year.

---

## Strategic context

The transformation is justified by three converging forces:

1. **AI is becoming a primary product capability**, not a research function. Every major product line now ships ML-driven features; latency-to-market for new ML capabilities is a competitive variable.

2. **The current infrastructure is at scaling limits.** Linear cost growth at this rate is unsustainable; compute-spend trajectory crosses the AI gross-margin line in Q3 of FY+2 if unchanged.

3. **Regulatory pressure (EU AI Act, US executive orders, sector-specific guidance)** raises the bar for documentation, governance, and reproducibility. Bespoke stacks make compliance audits 6-10x more expensive than a consolidated platform.

Doing nothing is not a neutral position. It compounds technical debt, accelerates cost growth, and accumulates regulatory exposure.

---

## Financial model summary

### Investment profile

```text
$M (negative = outflow)
                Q1    Q2    Q3    Q4    Q5    Q6    Q7    Q8
Personnel      -1.4  -1.6  -1.7  -1.8  -1.6  -1.5  -1.4  -1.4
Software       -0.5  -0.6  -0.6  -0.7  -0.3  -0.3  -0.3  -0.3
Infra          -0.3  -0.3  -0.4  -0.4  -0.3  -0.3  -0.3  -0.3
Prof Services  -0.3  -0.2  -0.1  -0.0   0.0   0.0   0.0   0.0
─────────────────────────────────────────────────────────────
Subtotal       -2.5  -2.7  -2.8  -2.9  -2.2  -2.1  -2.0  -2.0
              ────────────────────────  ────────────────────
              Year 1 Build: $10.9M     Year 2 Operate: $8.3M
              (offset by Y2 retirements: $2.8M → net $5.5M)
```

### Return profile

```text
$M (positive = savings vs. baseline)
                Q1    Q2    Q3    Q4    Q5    Q6    Q7    Q8
Compute saved   0.0   0.2   0.5   0.9   1.6   2.3   2.9   3.5
Tool license    0.0   0.1   0.3   0.6   0.8   0.8   0.8   0.8
Toil reduction  0.0   0.0   0.1   0.3   0.6   0.9   1.2   1.4
Revenue protect 0.0   0.0   1.5   3.0   5.0   7.0   9.0  11.0
─────────────────────────────────────────────────────────────
Subtotal        0.0   0.3   2.4   4.8   8.0  11.0  13.9  16.7
```

NPV at 10% discount rate: **+$23.4M over 24 months**.

### Sensitivities

| Variable | Base case | Pessimistic | Optimistic |
|---|---|---|---|
| Compute saving rate | 18% / 34% | 12% / 22% | 25% / 45% |
| Migration velocity | 6 teams/qtr | 3 teams/qtr | 8 teams/qtr |
| Revenue protection | $30M/yr | $15M/yr | $50M/yr |
| 24-mo NPV | $23.4M | -$1.2M | $51.0M |

The pessimistic case (migration slower than planned, lower compute savings) still pays back within the 24-month horizon when revenue protection is conservatively modeled. The program survives reasonable execution misses; it does not survive abandoning the executive sponsorship.

---

## Why a platform-as-a-product model

Two alternatives were considered and rejected:

| Alternative | Why rejected |
|---|---|
| **Continue current federation** | Trajectory is exactly the problem we're trying to solve. No structural change → no structural improvement. |
| **Mandate centralization with a top-down compliance team** | Historically yields shelfware. Teams will work around a platform they don't believe in. Compliance-led programs produce the lowest adoption rates in the industry benchmarks. |

The platform-as-a-product model treats internal engineers as customers. The platform team competes for adoption by providing better paved roads than what teams would build themselves. Adoption is measured (% of workloads on the platform, NPS, time-to-first-successful-run, golden-path coverage). Where the platform falls short, the platform team prioritizes the gap. Where teams have idiosyncratic needs that don't generalize, the platform offers an "escape hatch" rather than forcing centralization.

The downside: this model takes longer to start producing value than a mandate. The advantage: the value compounds because each successful migration creates a reference customer who advocates for the next.

---

## Talent plan

28 net new FTEs over 4 quarters:

```text
Quarter  Roles added                              Cumulative
Q1       6 platform engineers (4 senior, 2 PE)   6
         2 product managers                       8
         1 engineering manager                    9
Q2       4 platform engineers                    13
         1 program manager                       14
         1 security architect                    15
Q3       4 platform engineers                    19
         2 developer advocates                   21
         1 data-governance lead                  22
Q4       3 platform engineers                    25
         2 site reliability engineers            27
         1 finance partner (FinOps)              28
```

Hiring concentration in Q1-Q3 to front-load capacity. By Q5 the team is steady-state; backfill replaces attrition only. All offers carry an explicit 18-month "complete the transformation" expectation; we accept turnover after Year 2 as expected.

External recruiting partners on retainer for senior platform-engineer hires (the bottleneck role). Internal mobility pathway for current MLOps engineers in product teams; estimated 4-6 internal transfers.

---

## Governance

- **Executive sponsor:** [name TBD — must be SVP+ with bandwidth for biweekly review]
- **Steering committee:** Sponsor + CFO + CISO + 3 product-org leaders. Meets monthly. Approves major scope changes.
- **Working group:** Platform leadership + 1 representative from each migrating team. Weekly. Coordinates execution.
- **Risk register:** Owned by program manager. Reviewed weekly with steering committee summary monthly.
- **Decision log:** Architecture decisions captured as ADRs in `architecture/decisions/`. Sponsor reviews quarterly for pattern compliance.

Three explicit go/no-go gates:

| Gate | Date | Criteria |
|---|---|---|
| M3 — Build start | End Q1 | Team hired, sponsor confirmed, first golden path scoped |
| M6 — First migration | End Q2 | 1 product team migrated, learnings captured, no critical defects |
| M12 — Continue/exit | End Q4 | 6+ teams migrated, compute savings on track (≥ 12%), team NPS ≥ +20 |

Failure at any gate triggers a steering committee review. M12 specifically includes an exit option that limits sunk cost to $4.1M while preserving learnings.

---

## What we need from the board today

1. **Approve $9.2M Year 1 funding** (with the explicit understanding that Year 2 funding ($5.5M) requires a successful M12 gate).
2. **Approve the 28-FTE hiring plan** including the senior platform-engineer comp band (P75 of market for the targeted cities).
3. **Confirm executive sponsor commitment** through Q4 FY+2 (or designate a backup with equal seniority).
4. **Endorse the platform-as-a-product operating model** as the program's strategic shape, with the understanding that this means rejecting a top-down mandate approach even when individual teams resist migration.

The full project specification is at `../README.md`. The detailed financial model lives at `../financial-model/` (workbooks). The transformation playbook is at the parent repo's `guides/transformation-leadership.md`.
