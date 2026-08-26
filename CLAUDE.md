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

Skills may reference paths from the full [product-management-context](https://github.com/productmap-io/product-management-context) repo. Map them here:

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

- **Claude Code:** domain-specific PM skills live under [.claude/skills/](.claude/skills/). Each skill encodes a PM practice and is invoked via `/skill-name` or auto-matched by description.
- **Gemini CLI:** workflows created for Gemini (long-context synthesis, structured docs, AI specs) live under [.gemini/skills/](.gemini/skills/); see [GEMINI.md](GEMINI.md).
- **Codex:** repo-local skills under [.codex/skills/](.codex/skills/).

Prefer skills over ad-hoc prompts for recurring PM tasks.

| Skill | Command | Purpose |
|-------|---------|---------|
| agile-scrum-delivery | `/agile-scrum-delivery` | Sprint planning, ceremonies, and agile delivery workflows |
| go-to-market | `/go-to-market` | GTM strategy, messaging, and launch planning |
| interview-plan-questions | `/interview-plan-questions` | Generate a tailored 30–60 min interview question guide for founder customer discovery (pre-PMF) or UX / needfinding interviews |
| okrs-goal-setting | `/okrs-goal-setting` | OKR setting, cascade maps, and goal alignment |
| prd-requirements | `/prd-requirements` | Write, review, or scope PRDs, specs, and user stories |
| prioritization-rice | `/prioritization-rice` | RICE scoring and backlog prioritization |
| product-market-fit | `/product-market-fit` | PMF assessment, competitive analysis, and positioning |
| product-metrics-kpis | `/product-metrics-kpis` | North star, KPI trees, and metric frameworks |
| product-strategy-roadmap | `/product-strategy-roadmap` | Product vision, roadmap formats, and strategic planning |
| unit-economics | `/unit-economics` | LTV:CAC model and contribution margin analysis |
| user-research-interviews | `/user-research-interviews` | Research plans, interview guides, and synthesis |

## Conventions

- Dates are absolute (`YYYY-MM-DD`), never relative.
- Artifacts for a specific initiative go under `00_company/product/` — reference worksheets instead of duplicating them.
- Fill in `.productmap/` with your startup's facts; treat empty placeholders as prompts to complete.
