# Codex setup (startup-product-context)

This folder contains **Codex-specific** setup for this repository.

## Codex agent instructions

These instructions mirror `AGENTS.md` so Codex agents can find the operating rules from within `.codex/`.

This repository is a **simplified product context for early-stage startups**. Prefer using it as source material when answering questions or generating artifacts.

### Knowledge base entrypoint

- Start at `.productmap/INDEX.md` to navigate topics and worksheets.
- When you reference knowledge, include clickable file paths (e.g. `.productmap/02_discovery/user-research/interview-guide.md`).

### Working principles

- Read first, then write: consult the most relevant file under `.productmap/` before drafting anything new.
- Prefer adapting existing worksheets over inventing new structures.
- Keep edits minimal and focused; treat `.productmap/` as the canonical startup knowledge tree.

### Path mapping (from full PM context)

| Full PM context | Startup context |
|-----------------|-----------------|
| `02_generation/` | `02_discovery/` |
| `09_templates/` | Worksheets embedded in topic files |
| `10_data/` | `06_data/` |

### Artifacts and storage

- Put initiative-specific artifacts under `.productmap/00_company/product/` (unless the user requests a different location).
- Store raw inputs (interviews, feedback, analytics exports) under `.productmap/06_data/`.

### Conventions

- Use absolute dates (`YYYY-MM-DD`).
- If you make assumptions, state them briefly.

### Gemini CLI

Project context for Gemini CLI is in `GEMINI.md` (with `.productmap/INDEX.md` imported). Optional CLI settings: `.gemini/settings.json`. Gemini-oriented skills: `.gemini/skills/` (see `.gemini/README.md`).

### Codex skills (repo-local)

- Repo-local Codex skills live under `.codex/skills/` (each skill is a folder with a `SKILL.md`).
- When a task matches a skill, follow it and reference `.productmap/INDEX.md` + relevant worksheets under `.productmap/`.
