---
name: competitor-teardown-matrix
description: Reads competitor product, pricing, docs, and review pages and builds typed and tiered teardowns, a 0 to 3 scored matrix, and match, ignore, or differentiate decisions. Use for a first competitive picture, the competition slide before a raise, or a quarterly matrix refresh.
---

# Competitor teardown matrix

## When to use

- You have competitor pages saved or pasted and need them turned into one comparable view.
- Buyers keep naming an alternative and you can't say where you win or lose against it.
- The matrix in the repo is checkmarks only, or older than a quarter.

## Steps

1. Read [`INDEX.md`](../../../.productmap/INDEX.md), [`competitor-matrix.md`](../../../.productmap/01_strategy/competitors/competitor-matrix.md), [`value-proposition.md`](../../../.productmap/00_company/product/value-proposition.md), and every competitor page under [`06_data/research/`](../../../.productmap/06_data/research/).
2. List the alternatives buyers consider by type and tier, including the status quo. Write a teardown for each primary competitor with facts kept apart from interpretation.
3. Score 8 to 12 buyer-relevant dimensions from 0 to 3, with `?` for unknowns. Turn the gaps into match, ignore, or differentiate decisions and a battlecard.
4. Write the result into `.productmap/01_strategy/competitors/competitor-matrix.md`, keeping its headings, and set the monitoring cadence.

## Delegation

Use [subagent-prompt.md](subagent-prompt.md) for a sub-agent that reads all saved pages in one pass and fills the matrix file.

## Related on Product Map

- Agent: **[Run competitor analysis](https://app.productmap.io/agents/competitor-analysis)** — map competitors, score the matrix, find your edge.
- Workflow: **[Market research to positioning](https://app.productmap.io/workflows/market-research-to-positioning)** — run market research, run competitor analysis, then build a unique value proposition.

More AI PM agents from Product Map: https://www.productmap.io/
