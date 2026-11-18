# Codex skills (repo-local)

This folder contains **repo-local Codex skills**: artifact runbooks for early-stage founders. Each one produces a single artifact from stated inputs.

For overall Codex agent behavior in this repository, see `.codex/README.md` (mirrors `AGENTS.md`).

## How to use

- Each `SKILL.md` starts with YAML frontmatter (`name`, `description`) so tools like `npx skills` can index and install the skill.
- Treat each skill as a repeatable workflow: open the folder and follow `SKILL.md`.
- Ground outputs in this repository first: start at `.productmap/INDEX.md`, then pull in relevant worksheets under `.productmap/`.
- Every skill cites paths in this repo's startup tree and ends with a link to the matching agent on Product Map.

## Skills included

| Skill | What it does | Product Map agent |
| --- | --- | --- |
| [`startup-one-pager`](startup-one-pager/SKILL.md) | One-pager with ranked riskiest assumptions | [Validate startup idea](https://app.productmap.io/agents/startup-idea-validation) |
| [`investor-qa-prep`](investor-qa-prep/SKILL.md) | Hard investor questions with drafted answers and evidence gaps | [Prepare early stage pitch](https://app.productmap.io/agents/preseed-investor-pitch) |
| [`investor-pipeline-tracker`](investor-pipeline-tracker/SKILL.md) | Investor target list, stages and next actions | [Prepare early stage pitch](https://app.productmap.io/agents/preseed-investor-pitch) |
| [`landing-page-smoke-test`](landing-page-smoke-test/SKILL.md) | Landing copy plus a test card with pass/fail criteria | [Build unique value proposition](https://app.productmap.io/agents/value-proposition-positioning) |
| [`pricing-page-audit`](pricing-page-audit/SKILL.md) | Scored pricing-page audit across six pillars, with fixes | [Define monetization strategy](https://app.productmap.io/agents/monetization-pricing) |
| [`mvp-build-stack-decision`](mvp-build-stack-decision/SKILL.md) | No-code, low-code, AI-assisted or custom, as a decision record | [Scope and challenge MVP](https://app.productmap.io/agents/mvp-scope-decision) |
| [`launch-channel-test-cards`](launch-channel-test-cards/SKILL.md) | First launch plan and channel test cards with kill, iterate or scale rules | [Build go-to-market strategy](https://app.productmap.io/agents/go-to-market-strategy) |
| [`growth-experiment-sprint`](growth-experiment-sprint/SKILL.md) | Four-week growth sprint with three experiment cards | [Build product growth strategy](https://app.productmap.io/agents/growth-marketing) |
| [`design-partner-program`](design-partner-program/SKILL.md) | Design-partner criteria, offer, feedback cadence and path to paid | [Define ICP and segments](https://app.productmap.io/agents/ideal-customer-profile-icp) |
| [`startup-financial-model`](startup-financial-model/SKILL.md) | 18–24 month driver-based model with labeled assumptions | [Calculate unit economics](https://app.productmap.io/agents/unit-economics) |

## Conventions

- Skills are written as prompt templates with clear inputs/outputs and a step-by-step runbook.
- Use absolute dates (`YYYY-MM-DD`) in any artifacts.
