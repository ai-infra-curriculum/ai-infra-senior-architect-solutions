# SOLUTION — Global Infrastructure

> Read this *after* you have designed the reference global
> infrastructure. This document explains the senior-architect-tier
> view of running infrastructure across continents.

## What this module is really teaching

Global infrastructure adds dimensions beyond regional:
- Data residency and sovereignty.
- Latency budgets for global users.
- Currency, billing, vendor relationships per region.
- Local compliance regimes (China, EU, US, India).

## What the deliverables should actually look like

### Region strategy (exercise 01)

Which regions does the org operate in, why, on which clouds?
The deliverable distinguishes serving regions from data
regions from training regions.

### Data residency policy (exercise 02)

Per data class: where it can live, where it can transit, where
it cannot. Tied to regulatory requirements.

### Cross-region network design (exercise 03)

Backbone topology, CDN strategy, private interconnects, public
internet fallbacks.

### Local-vendor strategy (exercise 04)

In some markets (China, Russia), local cloud providers are
mandated. The deliverable identifies which markets require
which patterns.

### Carbon-footprint optimization (exercise 05)

Region selection that balances cost, latency, and carbon
footprint. Some regions are dramatically greener (Iceland,
Quebec).

## Trade-offs we deliberately accepted

- Global operations multiply ops complexity.
- Data residency conflicts with cost optimization.
- Some markets require local partners.

## Common mistakes graders see

1. **Global-by-default**: paying global costs for regional
   traffic.
2. **Data residency ignored**: regulatory exposure.
3. **No CDN strategy**: latency disasters for far-from-origin
   users.
4. **Carbon footprint ignored**: increasingly a board concern.

## When to go beyond this implementation

- Adopt **edge computing** for latency-sensitive global users.
- Move to **sovereign cloud** offerings where mandated.

## Related curriculum touchpoints

- ``architect/mod-302-multicloud-hybrid``.
- ``senior-engineer/mod-205-multi-cloud``.
