---
name: startup-context-bootstrap
description: Fills the .productmap context templates from website text, a pitch deck, and founder notes in dependency order, labeling every field evidence or assumption. Use for a new repo with empty templates, bringing an existing startup into the context tree, or refreshing stale context after a pivot.
---

# Startup context bootstrap

## When to use

- The context files still hold `[Fill in` placeholders and you have a website, a deck, or notes to fill them from.
- You changed direction and the one-pager, ICP, and business model no longer match what you say in the deck.
- You want to know which facts about your startup are written down nowhere.

## Steps

1. Read [`INDEX.md`](../../../.productmap/INDEX.md) and collect the sources. Save pasted text under [`06_data/research/`](../../../.productmap/06_data/research/) with a dated name before you use it.
2. Fill in dependency order: [`onepager.md`](../../../.productmap/00_company/product/onepager.md), [`product-vision.md`](../../../.productmap/00_company/product/product-vision.md), [`value-proposition.md`](../../../.productmap/00_company/product/value-proposition.md), one ICP file, [`business-model.md`](../../../.productmap/01_strategy/business-model/business-model.md), [`roadmap.md`](../../../.productmap/01_strategy/mvp-roadmap/roadmap.md), then the rest.
3. Keep every template heading. Label each filled field evidence or assumption, and leave unknown fields as placeholders.
4. Write the fill report to `.productmap/00_company/product/context-bootstrap-YYYY-MM-DD.md`: files touched, coverage, and the top open questions.

## Delegation

Use [subagent-prompt.md](subagent-prompt.md) for a sub-agent that reads all sources at once and fills the tree in one consistent pass.

## Related on Product Map

- Agent: **[Define strategy and roadmap](https://app.productmap.io/agents/product-strategy-roadmap)** — improve your product strategy and roadmap.
- Workflow: **[Product idea to MVP scope](https://app.productmap.io/workflows/product-idea-to-mvp-scope)** — validate the product idea, define strategy and roadmap, then scope and challenge the MVP.

More AI PM agents from Product Map: https://www.productmap.io/
