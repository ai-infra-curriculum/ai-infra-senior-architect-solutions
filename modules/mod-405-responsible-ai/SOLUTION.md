# SOLUTION — Responsible AI

> Read this *after* you have attempted the responsible-AI
> deliverables. This document explains the senior-architect-tier
> view of operationalizing responsible AI.

## What this module is really teaching

Responsible AI moved from "marketing copy" to "regulated
requirement" with the EU AI Act and similar laws. Senior
architects design the operational program that turns principles
into enforced controls.

## What the deliverables should actually look like

### Responsible AI policy (exercise 01)

The organization's principles + the operational program that
implements them. Not just statements of intent — concrete
controls (impact assessments, audits, human oversight
requirements).

### Model risk classification (exercise 02)

Per AI system: risk class (minimal / limited / high /
unacceptable per EU AI Act categories or equivalent). Risk
class drives review depth, monitoring, documentation.

### Fairness assessment framework (exercise 03)

For each high-risk system: which protected attributes apply,
which fairness metrics, what the action protocol is when
disparities exceed thresholds.

### Human oversight pattern (exercise 04)

Per high-risk system: where human review fits in the workflow,
what the override interfaces look like, training for human
reviewers.

### Public reporting (exercise 05)

Annual responsible-AI report. Includes systems deployed, risk
assessments, incidents, mitigations. Builds public trust and
satisfies emerging transparency requirements.

## Trade-offs we deliberately accepted

- Responsible AI controls slow some deployments.
- Public reporting exposes the org to scrutiny.
- Fairness metrics fight each other (you can't optimize all).

## Common mistakes graders see

1. **Responsible AI = a slide deck**: no operational program.
2. **Single fairness metric**: missing trade-offs.
3. **Human oversight without empowerment**: reviewer can't
   actually block.
4. **No incident response for AI failures**.

## When to go beyond this implementation

- Adopt **NIST AI Risk Management Framework**.
- Move toward **algorithmic audit** as a recurring discipline.

## Related curriculum touchpoints

- ``security/projects/project-3-adversarial-defense`` —
  adversarial security.
- ``mlops/07-governance`` — model governance basics.
