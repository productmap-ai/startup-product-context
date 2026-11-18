---
name: startup-launch-readiness-review
description: Reads the whole .productmap tree and scores a 12-step launch checklist as done, partial, or missing, with the file that proves each verdict. Use for a pre-launch gap check, a stage review before planning the next month, or choosing the next 5 to 7 actions.
---

# Startup launch readiness review

## When to use

- You want one honest status of the path from idea to launch, backed by what the context files say today.
- You are about to build, launch, or spend on growth and want to know which earlier step is still unproven.
- The context tree has grown and the files contradict each other.

## Steps

1. Read [`INDEX.md`](../../../.productmap/INDEX.md), then every file under [`.productmap/`](../../../.productmap/), including the raw inputs in `06_data/`.
2. Score each of the 12 checklist steps done, partial, or missing. Name the file and heading behind each verdict, and label every claim evidence or assumption.
3. Apply the three sequencing rules: a validated problem before build, retention before scale, working unit economics before growth spend.
4. Save the review as `.productmap/00_company/product/launch-readiness-YYYY-MM-DD.md` with 5 to 7 next actions, each with a timebox and a target file.

## Delegation

Use [subagent-prompt.md](subagent-prompt.md) to hand the full-tree read and the review document to a sub-agent.

## Related on Product Map

- Agent: **[Track startup launch](https://app.productmap.io/agents/startup-launch-tracker)** — know your stage and what to do next.

More AI PM agents from Product Map: https://www.productmap.io/
