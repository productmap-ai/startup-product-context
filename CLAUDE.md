# Startup Product Context

This repository is a **simplified product context for early-stage startups** — a lean, founder-focused knowledge base. It covers company context, strategy, discovery, analysis, delivery, and operations for teams validating and building before scale.

## Knowledge base entrypoint

- **Start here:** [.productmap/INDEX.md](.productmap/INDEX.md) — topic index, navigation, and links into worksheets across the tree.
- Use it as the **canonical map** before drafting artifacts or answering founder PM questions.

## Repository structure

All content lives under [.productmap/](.productmap/). See [.productmap/INDEX.md](.productmap/INDEX.md) for the full index. Top-level sections:

- `00_company/` — team, resources, product one-pager, vision, fundraising
- `01_strategy/` — business model, PMF, segmentation, competitors, roadmap
- `02_discovery/` — user research, experiments, design/UX, marketing, GTM, founder-led sales
- `03_analysis/` — KPIs, metrics tracking, analytics, unit economics
- `04_delivery/` — backlog, prioritization, development specs
- `05_operations/` — finance (runway, model) and legal (incorporation, IP, privacy)
- `06_data/` — raw interviews, feedback, analytics exports, research notes

## Path mapping (from full PM context)

The skills in this repo cite the startup tree directly. If you also install skills from the full [product-management-context](https://github.com/productmap-ai/product-management-context) repo, map their paths here:

| Full PM context | Startup context |
|-----------------|-----------------|
| `02_generation/` | `02_discovery/` |
| `05_people/` | (not in startup tree) |
| `06_operations/` (product ops) | `05_operations/` |
| `09_templates/` | Worksheets embedded in topic files |
| `08_frameworks/` | Framework notes in relevant files (e.g. RICE in `04_delivery/backlog-requirements/prioritization.md`) |
| `10_data/` | `06_data/` |

## How to work in this repo

- **Read before writing.** When answering a PM question, first consult the relevant file under `.productmap/`. Cite file paths so the user can navigate.
- **Worksheets are the source of truth.** For artifacts like pitch decks, interview guides, or prioritization, use the embedded templates in `.productmap/` rather than inventing structure.
- **Data stays in `06_data/`.** Interviews, analytics dumps, and raw feedback belong there — not scattered through the other sections.

## Skills

- **Claude Code:** founder practice guides live under [.claude/skills/](.claude/skills/). Each skill encodes one founder practice and is invoked via `/skill-name` or auto-matched by description.
- **Codex:** artifact runbooks with a copy-paste prompt live under [.codex/skills/](.codex/skills/); see [.codex/skills/README.md](.codex/skills/README.md).
- **Gemini CLI:** long-context synthesis workflows, each with a sub-agent prompt, live under [.gemini/skills/](.gemini/skills/); see [.gemini/README.md](.gemini/README.md).

Each tool has its own list of ten, built around the startup agents on Product Map. Prefer skills over ad-hoc prompts for recurring founder tasks.

| Skill | Command | Purpose | Product Map agent |
|-------|---------|---------|-------------------|
| startup-idea-validation | `/startup-idea-validation` | Stress-test the problem, audience, fit and market; choose what to validate first | [Validate startup idea](https://app.productmap.io/agents/startup-idea-validation) |
| pre-seed-pitch-narrative | `/pre-seed-pitch-narrative` | Build the investor story in eight beats, from problem to ask | [Prepare early stage pitch](https://app.productmap.io/agents/preseed-investor-pitch) |
| fundraising-strategy | `/fundraising-strategy` | Decide whether, when and how much to raise, and from whom | [Prepare early stage pitch](https://app.productmap.io/agents/preseed-investor-pitch) |
| value-proposition-positioning | `/value-proposition-positioning` | Value Proposition Canvas, fit check and a positioning statement to test | [Build unique value proposition](https://app.productmap.io/agents/value-proposition-positioning) |
| monetization-pricing | `/monetization-pricing` | Pick the pricing model, value metric and tiers; check willingness to pay | [Define monetization strategy](https://app.productmap.io/agents/monetization-pricing) |
| founder-led-sales | `/founder-led-sales` | Go from ICP to first paying customers through outreach, discovery calls and closing | [Define ICP and segments](https://app.productmap.io/agents/ideal-customer-profile-icp) |
| growth-loops-engine | `/growth-loops-engine` | Find the bottleneck, pick the growth engine and design growth loops | [Build product growth strategy](https://app.productmap.io/agents/growth-marketing) |
| digital-marketing-campaigns | `/digital-marketing-campaigns` | Growth brief, channel choice and ranked campaign ideas | [Create digital marketing ideas](https://app.productmap.io/agents/digital-product-marketing) |
| runway-burn-planning | `/runway-burn-planning` | Burn, runway, scenarios, and cut or raise triggers | [Calculate unit economics](https://app.productmap.io/agents/unit-economics) |
| cofounder-alignment | `/cofounder-alignment` | Roles, equity, vesting, decision rights and working norms | [Enable team collaboration](https://app.productmap.io/agents/team-collaboration-leadership) |

## Conventions

- Dates are absolute (`YYYY-MM-DD`), never relative.
- Artifacts for a specific initiative go under `00_company/product/` — reference worksheets instead of duplicating them.
- Fill in `.productmap/` with your startup's facts; treat empty placeholders as prompts to complete.
