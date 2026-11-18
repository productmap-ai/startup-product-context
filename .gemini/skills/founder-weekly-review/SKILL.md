---
name: founder-weekly-review
description: Builds a one-page weekly review from the metrics, runway, experiment, and backlog files and flags numbers that disagree across files. Use for a Monday founder review, a weekly cofounder sync, or keeping a decision trail between investor updates.
---

# Founder weekly review

## When to use

- You want one page each week showing where the company stands and what you will do next.
- Metrics, runway, and experiment results live in separate files and nobody reads them together.
- You suspect the same number is written differently in two places.

## Steps

1. Read [`INDEX.md`](../../../.productmap/INDEX.md), [`metrics-tracking.md`](../../../.productmap/03_analysis/kpis-metrics/metrics-tracking.md), [`kpis-metrics.md`](../../../.productmap/03_analysis/kpis-metrics/kpis-metrics.md), [`runway-burn.md`](../../../.productmap/05_operations/finance/runway-burn.md), [`experiments.md`](../../../.productmap/02_discovery/experiments/experiments.md), [`backlog.md`](../../../.productmap/04_delivery/backlog-requirements/backlog.md), and last week's review.
2. Fill the scorecard: north star and 3 to 5 KPIs against last week, plus runway. Leave a missing number blank and name its source.
3. List experiments run and their results, name the current bottleneck, and record decisions, the top three priorities, and blockers.
4. Flag every number that disagrees across files, then save the page as `.productmap/03_analysis/kpis-metrics/weekly-review-YYYY-MM-DD.md`.

## Delegation

Use [subagent-prompt.md](subagent-prompt.md) for a sub-agent that reads the files and past reviews together and returns the one-page review.

## Related on Product Map

- Agent: **[Make data-driven decisions](https://app.productmap.io/agents/data-driven-product-decisions)** — use KPIs, analytics, and finance to drive product.

More AI PM agents from Product Map: https://www.productmap.io/
