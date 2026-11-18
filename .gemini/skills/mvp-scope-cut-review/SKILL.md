---
name: mvp-scope-cut-review
description: Reviews the backlog against the one claim the MVP must prove and marks every item keep, cut, or defer with a one-line reason. Use for a backlog that keeps growing, a build that slipped past its window, or a scope check before the first week of building.
---

# MVP scope cut review

## When to use

- The backlog has more items than a small team can ship in six weeks.
- You can't say which assumption each planned feature tests.
- The build has slipped and you need to decide what leaves the first release.

## Steps

1. Read [`INDEX.md`](../../../.productmap/INDEX.md), [`backlog.md`](../../../.productmap/04_delivery/backlog-requirements/backlog.md), [`prioritization.md`](../../../.productmap/04_delivery/backlog-requirements/prioritization.md), [`roadmap.md`](../../../.productmap/01_strategy/mvp-roadmap/roadmap.md), [`onepager.md`](../../../.productmap/00_company/product/onepager.md), the ICP files, and [`experiments.md`](../../../.productmap/02_discovery/experiments/experiments.md).
2. Write the one claim the MVP must prove, with its metric, threshold, and date.
3. For every backlog item, name the assumption it tests and mark it keep, cut, or defer with a one-line reason. Define the first release slice and a six-week plan.
4. Save the review as `.productmap/04_delivery/backlog-requirements/mvp-scope-review-YYYY-MM-DD.md` and move cut and deferred items to the Ice Box in the backlog.

## Delegation

Use [subagent-prompt.md](subagent-prompt.md) for a sub-agent that reads the backlog next to the strategy files and returns the full item-by-item review.

## Related on Product Map

- Agent: **[Scope and challenge MVP](https://app.productmap.io/agents/mvp-scope-decision)** — cut scope, build the backlog, pick the stack.
- Workflow: **[Product idea to MVP scope](https://app.productmap.io/workflows/product-idea-to-mvp-scope)** — validate the product idea, define strategy and roadmap, then scope and challenge the MVP.

More AI PM agents from Product Map: https://www.productmap.io/
