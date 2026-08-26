# Startup product context (Gemini CLI)

You are assisting in a **simplified product context for early-stage startups** — a lean, founder-focused knowledge repository. Treat **`.productmap/`** as the authoritative knowledge tree. Start navigation from **[`.productmap/INDEX.md`](.productmap/INDEX.md)**.

## Knowledge layout

| Area | Path | Use for |
|------|------|---------|
| Company / product / fundraising | `.productmap/00_company/` | Team, resources, one-pager, vision, pitch deck, investor pipeline |
| Strategy | `.productmap/01_strategy/` | Business model, PMF, segmentation, competitors, roadmap |
| Discovery | `.productmap/02_discovery/` | User research, experiments, design/UX, marketing, GTM, founder-led sales |
| Analysis | `.productmap/03_analysis/` | KPIs, metrics tracking, analytics, unit economics |
| Delivery | `.productmap/04_delivery/` | Backlog, prioritization, development specs |
| Operations | `.productmap/05_operations/` | Finance (runway, model) and legal (incorporation, IP, privacy) |
| Data | `.productmap/06_data/` | Raw interviews, feedback, analytics exports, research |

## Path mapping (from full PM context)

Skills may reference the full [product-management-context](https://github.com/productmap-io/product-management-context) taxonomy. Map to this repo:

| Full PM context | Startup context |
|-----------------|-----------------|
| `02_generation/` | `02_discovery/` |
| `05_people/` | (not in startup tree) |
| `06_operations/` (product ops) | `05_operations/` |
| `09_templates/` | Worksheets embedded in topic files |
| `08_frameworks/` | Framework notes in relevant files |
| `10_data/` | `06_data/` |

## Operating rules

1. **Read before writing.** Open the relevant file under `.productmap/` before drafting artifacts.
2. **Worksheets are source of truth** for structure (pitch deck, interview guide, prioritization). Extend them; do not invent incompatible sections without user approval.
3. **Initiative-specific outputs** belong under `.productmap/00_company/product/` unless the user specifies otherwise.
4. **Raw inputs** (interviews, dumps) go under `.productmap/06_data/`.
5. **Dates:** use absolute `YYYY-MM-DD` (e.g. `2026-08-26`).
6. **Fill in placeholders** — empty fields in `.productmap/` are prompts for the founder to complete.

## Model strengths to leverage (Gemini)

Prefer tasks that benefit from **long-context synthesis**, **structured multi-section documents**, **clear hierarchies**, **blending narrative with checklists**, and **turning messy notes into spec-quality prose**. When the user attaches **screenshots, decks, or diagrams**, incorporate visual context explicitly.

## Project skills (Gemini)

Reusable workflows live under **`.gemini/skills/<skill-name>/`**. Each folder contains `SKILL.md` (how to run the workflow) and `subagent-prompt.md` (detailed delegation prompt for a sub-agent). Prefer these skills over ad-hoc instructions for the matching task. Claude Code skills that are not Gemini-oriented remain under [`.claude/skills/`](.claude/skills/).

## External reference

Curated topic list from the public Product Map page: [`.claude/resources/productmap-product-management-map-topics.md`](.claude/resources/productmap-product-management-map-topics.md).

Nested memory import (Gemini CLI): the following file is appended for folder-level navigation.

@./.productmap/INDEX.md
