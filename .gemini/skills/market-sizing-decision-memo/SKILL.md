---
name: market-sizing-decision-memo
description: Turns desk research into a one-page market decision memo with bottom-up TAM, SAM, and SOM in low, base, and high cases, a top-down cross-check, and a scored beachhead. Use for choosing a first segment, a go or no-go on a market, or the market slide of a pitch deck.
---

# Market sizing decision memo

## When to use

- A decision waits on market size: which segment to enter first, whether to continue, or what to tell investors.
- You have reports, statistics, and competitor numbers saved under `06_data/research/` and no single view of them.
- Your only market number is one top-down figure from one report.

## Steps

1. Read [`INDEX.md`](../../../.productmap/INDEX.md), [`segmentation.md`](../../../.productmap/01_strategy/segmentation/segmentation.md), [`opportunity-assessment.md`](../../../.productmap/01_strategy/product-market-fit/opportunity-assessment.md), [`product-market-fit.md`](../../../.productmap/01_strategy/product-market-fit/product-market-fit.md), and every file in [`06_data/research/`](../../../.productmap/06_data/research/).
2. Name the decision and its kill criterion first. Then size the market bottom-up with low, base, and high cases, and cross-check it top-down.
3. Score 3 to 5 segments, pick a beachhead, and list the forces to watch. Log every source with its date.
4. Save the memo as `.productmap/01_strategy/product-market-fit/market-sizing-YYYY-MM-DD.md` and write a summary row into the Opportunity Assessment Table.

## Delegation

Use [subagent-prompt.md](subagent-prompt.md) for a sub-agent that reads the full research folder and returns the memo with its sizing tables.

## Related on Product Map

- Agent: **[Run market research](https://app.productmap.io/agents/market-research)** — size the market, pick a segment, scan the forces.
- Workflow: **[Market research to positioning](https://app.productmap.io/workflows/market-research-to-positioning)** — run market research, run competitor analysis, then build a unique value proposition.

More AI PM agents from Product Map: https://www.productmap.io/
