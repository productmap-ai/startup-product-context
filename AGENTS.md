# Codex Agent Instructions (startup-product-context)

This repository is a **simplified product context for early-stage startups**. Prefer using it as source material when answering questions or generating artifacts for founders and pre-PMF teams.

## Knowledge base entrypoint

- Start at `.productmap/INDEX.md` to navigate topics and worksheets.
- When you reference knowledge, include clickable file paths (e.g. `.productmap/02_discovery/user-research/interview-guide.md`).

## Working principles

- Read first, then write: consult the most relevant file under `.productmap/` before drafting anything new.
- Prefer adapting existing worksheets and templates embedded in `.productmap/` files over inventing new structures.
- Keep edits minimal and focused; treat `.productmap/` as the canonical startup knowledge tree.

## Path mapping (from full PM context)

Skills and prompts may reference the full [product-management-context](https://github.com/productmap-ai/product-management-context) taxonomy. Map to this repo as follows:

| Full PM context | Startup context |
|-----------------|-----------------|
| `.productmap/02_generation/` | `.productmap/02_discovery/` |
| `.productmap/05_people/` | (not in startup tree — use discovery or operations) |
| `.productmap/06_operations/` (product ops) | `.productmap/05_operations/` (finance & legal) |
| `.productmap/09_templates/` | Worksheets embedded in `.productmap/` files |
| `.productmap/08_frameworks/` | Framework guidance in relevant topic files (e.g. RICE in `prioritization.md`) |
| `.productmap/10_data/` | `.productmap/06_data/` |

## Artifacts and storage

- Put initiative-specific artifacts under `.productmap/00_company/product/` (unless the user requests a different location).
- Store raw inputs (interviews, feedback, analytics exports) under `.productmap/06_data/`.

## Conventions

- Use absolute dates (`YYYY-MM-DD`).
- If you make assumptions, state them briefly.

## Gemini CLI

Project context for [Gemini CLI](https://github.com/google-gemini/gemini-cli) is in `GEMINI.md` (with `.productmap/INDEX.md` imported). Optional CLI settings: `.gemini/settings.json`. Gemini-oriented skills: `.gemini/skills/` (see `.gemini/README.md`).

## Codex skills (repo-local)

- Repo-local Codex skills live under `.codex/skills/` (each skill is a folder with a `SKILL.md`).
- When a task matches a skill, follow it and reference `.productmap/INDEX.md` + relevant worksheets under `.productmap/`.
