---
name: investor-update-memo
description: Drafts a monthly investor update from the metrics, runway, PMF, roadmap, and pipeline files, with lowlights stated plainly and every number checked against earlier updates. Use for the monthly email to investors, a first update after closing a round, or restarting updates after a gap.
---

# Investor update memo

## When to use

- The month has closed and you owe investors and advisors an update.
- You want asks specific enough for a reader to act on in one reply.
- Numbers in past updates and numbers in the repo have started to drift apart.

## Steps

1. Read [`INDEX.md`](../../../.productmap/INDEX.md), [`metrics-tracking.md`](../../../.productmap/03_analysis/kpis-metrics/metrics-tracking.md), [`runway-burn.md`](../../../.productmap/05_operations/finance/runway-burn.md), [`pmf-signals.md`](../../../.productmap/01_strategy/product-market-fit/pmf-signals.md), [`roadmap.md`](../../../.productmap/01_strategy/mvp-roadmap/roadmap.md), [`investor-pipeline.md`](../../../.productmap/00_company/fundraising/investor-pipeline.md), and earlier updates in [`00_company/fundraising/`](../../../.productmap/00_company/fundraising/).
2. Build the metrics table from the files, with a source path per number. A number the files don't hold stays blank and becomes a question for the founder.
3. Write highlights, lowlights with their numbers, learnings, specific asks, and next-month goals. Check each figure against the previous update.
4. Save the draft as `.productmap/00_company/fundraising/investor-update-YYYY-MM.md`. The founder reviews it before sending.

## Delegation

Use [subagent-prompt.md](subagent-prompt.md) for a sub-agent that reads the current files and all past updates and returns the draft with a consistency check.

## Related on Product Map

- Agent: **[Prepare early stage pitch](https://app.productmap.io/agents/preseed-investor-pitch)** — turn notes into a script for an investor pitch deck.

More AI PM agents from Product Map: https://www.productmap.io/
