# Gemini agent assets

- **`settings.json`** — Gemini CLI context (`GEMINI.md`, `AGENTS.md`).
- **`skills/`** (under `.gemini/`) — Founder PM workflows tuned for Gemini (each folder: `SKILL.md` + optional `subagent-prompt.md`). Knowledge and worksheets live under [`.productmap/`](../.productmap/).
- The repository root [`skills.sh.json`](../skills.sh.json) adds `.gemini/skills/` to the search paths of the open `npx skills` CLI, so these skills install from the files in this folder (see root `README.md`).

## Skills

Each skill reads a lot at once (the whole context tree, many transcripts, long pages) and returns one structured document. Every skill cites paths in this repo's startup tree and ends with a link to the matching agent on Product Map.

| Skill | What it does | Product Map agent |
| --- | --- | --- |
| [`startup-launch-readiness-review`](skills/startup-launch-readiness-review/SKILL.md) | Reads the whole context tree and scores a 12-step launch checklist | [Track startup launch](https://app.productmap.io/agents/startup-launch-tracker) |
| [`startup-context-bootstrap`](skills/startup-context-bootstrap/SKILL.md) | Turns a site, deck and raw notes into filled context files | [Define strategy and roadmap](https://app.productmap.io/agents/product-strategy-roadmap) |
| [`market-sizing-decision-memo`](skills/market-sizing-decision-memo/SKILL.md) | Bottom-up TAM/SAM/SOM and a one-page decision memo | [Run market research](https://app.productmap.io/agents/market-research) |
| [`competitor-teardown-matrix`](skills/competitor-teardown-matrix/SKILL.md) | Public pages into a 0–3 matrix and match, ignore or differentiate calls | [Run competitor analysis](https://app.productmap.io/agents/competitor-analysis) |
| [`pivot-or-persevere-review`](skills/pivot-or-persevere-review/SKILL.md) | Evidence against kill criteria, a verdict per assumption, and a decision memo | [Validate startup idea](https://app.productmap.io/agents/startup-idea-validation) |
| [`investor-update-memo`](skills/investor-update-memo/SKILL.md) | Monthly investor update from metrics and notes | [Prepare early stage pitch](https://app.productmap.io/agents/preseed-investor-pitch) |
| [`launch-retro-synthesis`](skills/launch-retro-synthesis/SKILL.md) | 30-day post-launch retro across channels, funnel and feedback | [Build go-to-market strategy](https://app.productmap.io/agents/go-to-market-strategy) |
| [`pricing-research-synthesis`](skills/pricing-research-synthesis/SKILL.md) | Willingness-to-pay research and competitor pricing into a recommendation | [Define monetization strategy](https://app.productmap.io/agents/monetization-pricing) |
| [`mvp-scope-cut-review`](skills/mvp-scope-cut-review/SKILL.md) | Challenges the backlog against the riskiest assumption, then keep, cut or defer | [Scope and challenge MVP](https://app.productmap.io/agents/mvp-scope-decision) |
| [`founder-weekly-review`](skills/founder-weekly-review/SKILL.md) | One-page weekly review of metrics, runway, experiments and priorities | [Make data-driven decisions](https://app.productmap.io/agents/data-driven-product-decisions) |

See the root [`GEMINI.md`](../GEMINI.md) for full agent instructions.
