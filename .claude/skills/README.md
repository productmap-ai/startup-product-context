# Claude Code skills (repo-local)

Founder practice guides for early-stage startups. Each subdirectory contains a `SKILL.md` with YAML frontmatter (`name`, `description`) and practitioner instructions. Keep `description` as valid YAML: avoid a bare `key: value` segment inside an unquoted line (for example use `Triggers —` rather than `Triggers:` in the one-line description). Claude matches skills by description; you can also invoke `/skill-name` when supported.

**Knowledge base entrypoint:** [.productmap/INDEX.md](../../.productmap/INDEX.md) — navigate topics and worksheets before drafting artifacts. Every skill cites paths in this repo's startup tree and ends with a link to the matching agent on Product Map.

## Skills

| Skill | What it does | Product Map agent |
| --- | --- | --- |
| [`startup-idea-validation`](startup-idea-validation/SKILL.md) | Stress-test the problem, audience, fit and market; choose what to validate first | [Validate startup idea](https://app.productmap.io/agents/startup-idea-validation) |
| [`pre-seed-pitch-narrative`](pre-seed-pitch-narrative/SKILL.md) | Build the investor story in eight beats, from problem to ask | [Prepare early stage pitch](https://app.productmap.io/agents/preseed-investor-pitch) |
| [`fundraising-strategy`](fundraising-strategy/SKILL.md) | Decide whether, when and how much to raise, and from whom | [Prepare early stage pitch](https://app.productmap.io/agents/preseed-investor-pitch) |
| [`value-proposition-positioning`](value-proposition-positioning/SKILL.md) | Value Proposition Canvas, fit check and a positioning statement to test | [Build unique value proposition](https://app.productmap.io/agents/value-proposition-positioning) |
| [`monetization-pricing`](monetization-pricing/SKILL.md) | Pick the pricing model, value metric and tiers; check willingness to pay | [Define monetization strategy](https://app.productmap.io/agents/monetization-pricing) |
| [`founder-led-sales`](founder-led-sales/SKILL.md) | Go from ICP to first paying customers through outreach, discovery calls and closing | [Define ICP and segments](https://app.productmap.io/agents/ideal-customer-profile-icp) |
| [`growth-loops-engine`](growth-loops-engine/SKILL.md) | Find the bottleneck, pick the growth engine and design growth loops | [Build product growth strategy](https://app.productmap.io/agents/growth-marketing) |
| [`digital-marketing-campaigns`](digital-marketing-campaigns/SKILL.md) | Growth brief, channel choice and ranked campaign ideas | [Create digital marketing ideas](https://app.productmap.io/agents/digital-product-marketing) |
| [`runway-burn-planning`](runway-burn-planning/SKILL.md) | Burn, runway, scenarios, and cut or raise triggers | [Calculate unit economics](https://app.productmap.io/agents/unit-economics) |
| [`cofounder-alignment`](cofounder-alignment/SKILL.md) | Roles, equity, vesting, decision rights and working norms | [Enable team collaboration](https://app.productmap.io/agents/team-collaboration-leadership) |

**Codex artifact runbooks:** see [.codex/skills/README.md](../../.codex/skills/README.md). **Gemini long-context synthesis skills:** see [.gemini/README.md](../../.gemini/README.md).

See root [CLAUDE.md](../../CLAUDE.md) for repository conventions.
