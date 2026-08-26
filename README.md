# Startup product context

This repository is a **simplified product context for early-stage startups** — a lean, founder-focused knowledge base and agentic workspace. It covers what you need before and during product–market fit: company context, strategy, discovery, metrics, delivery, and operations — without the full lifecycle breadth of a mature PM organization.

The [`.productmap/`](.productmap/) folder is a curated startup taxonomy (company, strategy, discovery, analysis, delivery, operations, raw data). On top of that tree, [AGENTS.md](AGENTS.md), [CLAUDE.md](CLAUDE.md), and [GEMINI.md](GEMINI.md) spell out how agents should behave; repeatable workflows live under [`.claude/skills/`](.claude/skills/) (Claude Code), [`.codex/skills/`](.codex/skills/) (Codex), and [`.gemini/skills/`](.gemini/skills/) (Gemini CLI). Point Cursor, Claude Code, Codex, and Gemini CLI at one versioned source of truth instead of restarting context in every tool.

**Related:** For the full product management lifecycle (templates, frameworks, tools, people practices), see [product-management-context](https://github.com/productmap-io/product-management-context).

## Get started with this repository

**What you are building.** A repo-first context layer for founders and early PMs: curated startup topics, worksheets, and checklists in files agents can read. Cursor, Claude Code, Codex, and Gemini CLI sit on top as different runners; you pick the tool for the job and keep one repo as the handoff surface.

**A setup that works well**

- **Cursor** as the hub. Open this repo as the workspace so chat and edits see [AGENTS.md](AGENTS.md), [CLAUDE.md](CLAUDE.md), and [GEMINI.md](GEMINI.md) without path gymnastics. Use the Claude Code plugin for workflows that match [`.claude/skills/`](.claude/skills/). Use the Codex plugin with the same repo so Codex follows [AGENTS.md](AGENTS.md) (mirrored in [`.codex/README.md`](.codex/README.md)) and [`.codex/skills/`](.codex/skills/) (see [`.codex/skills/README.md`](.codex/skills/README.md)).
- **Claude Code** for skill-driven founder PM runs. The plugin reads [CLAUDE.md](CLAUDE.md) and routes recurring jobs through the right skill under [`.claude/skills/`](.claude/skills/) instead of one-off prompts.
- **Codex (inside Cursor)** when you want Codex-specific behavior and repo-local skills. Keep initiative outputs under `.productmap/00_company/product/` and raw inputs under `.productmap/06_data/` as [AGENTS.md](AGENTS.md) describes.
- **Gemini CLI** for jobs that need long-context synthesis, structured multi-section docs, or batch turns over the same tree. Install the Gemini CLI, open terminal in Cursor, `cd` to this repo, and rely on [GEMINI.md](GEMINI.md) plus [`.gemini/skills/`](.gemini/skills/) (see [`.gemini/README.md`](.gemini/README.md)). Optional: [`.gemini/settings.json`](.gemini/settings.json) for CLI defaults.
- **Product Map AI** ([app](https://app.productmap.io/)) to work with AI agents using this project context. Open the linked project from [`.productmap/INDEX.md`](.productmap/INDEX.md).

**Steps**

1. Clone or copy this repository and open it in Cursor.
2. Fill in `.productmap/` with your startup's facts — team, product one-pager, ICP, roadmap, metrics, and so on. Templates are embedded in each file; there is no separate templates folder.
3. Skim [`.productmap/INDEX.md`](.productmap/INDEX.md) so you know where worksheets and overviews live.
4. For day-to-day work in Cursor, `@`-mention or paste paths to the relevant files under `.productmap/` instead of pasting unstructured blobs into chat.
5. For a recurring task (PMF assessment, interview guide, MVP scope, GTM plan), open the matching folder under [`.claude/skills/`](.claude/skills/), [`.codex/skills/`](.codex/skills/), or [`.gemini/skills/`](.gemini/skills/) and follow `SKILL.md` rather than improvising.
6. Put initiative-specific artifacts in `.productmap/00_company/product/`. Put interviews, exports, and raw feedback in `.productmap/06_data/`.
7. Use absolute dates (`YYYY-MM-DD`) in anything you write back to the repo.

You stay the orchestrator: same knowledge layer, different agents for different strengths; the repo is where outputs compound.

## What context engineering means for founders

**Context engineering** means you choose what an agent sees, in what format, and in what order, so outputs stay consistent, reviewable, and tied to your product. You shape the whole environment around the task, not only the line you type into the chat box.

For early-stage startups, context engineering covers:

- Separating roles: instructions (how the agent should act), durable knowledge (facts, worksheets, decisions), retrieval (large or fast-changing sources), and runtime context (the live initiative, interview batch, or sprint).
- Slowing drift: when priorities, messaging, and constraints move every week, shared files beat everyone keeping a private story in chat threads.
- Staying repo-first: Git gives history, review, rollback, and portability. Your team owns the text in files you can branch and diff.

Think in four layers: canonical project knowledge, then agent instruction files, then runtime task context, then personal preferences. Keep root instruction files short. Link to [`.productmap/INDEX.md`](.productmap/INDEX.md); pull deeper files only when the task needs them.

## TASK: topics, agents, skills, knowledge

The [TASK framework](https://www.productmap.io/task-agentic-product-management) (Product Map, 2026-04-02) names how agentic PM work fits together. You stay the orchestrator. Scoped helpers run in clear domains on your product context; you keep judgment and calls.

| Pillar | Role |
|--------|------|
| T: Topics | Startup domains and founder-focused resources: company, strategy, discovery, analysis, delivery, operations. |
| A: Agents | Scoped executors (research, drafting, prioritization, synthesis) with prompts, memory, and access to the right files. |
| S: Skills | Your competences and quality bars: what to delegate, how to steer agents, where to step in. |
| K: Knowledge | Outputs that compound: specs, roadmaps, research, decision logs; plain text, versioned, written back each cycle. |

### A loop you can run

- Start with one domain you are in today (PMF validation, discovery interviews, MVP scope, founder-led sales).
- Define or refine an agent: system prompt, tools, and which folders it may read or write.
- Apply your skills: steer output, set the bar, validate.
- Write back to the repo under `.productmap/` and raw inputs under `06_data/` so the next task reuses work.

Each pass gets faster when knowledge compounds and context stays clean. When output is wrong, thin, or stale, fix the source: the instruction or file that led to it.

## Agent skills ([skills.sh](https://skills.sh/) ecosystem)

This repository is structured so the open [`skills`](https://github.com/vercel-labs/skills) CLI can discover installable skills: each skill is a folder with a `SKILL.md` that includes YAML frontmatter (`name` and `description` as plain strings). Skills live under [`.claude/skills/`](.claude/skills/) (Claude Code), [`.codex/skills/`](.codex/skills/) (Codex), and [`.gemini/skills/`](.gemini/skills/) (Gemini CLI). The [`skills/`](skills/) directory mirrors Gemini skills for the ecosystem: each entry is a **real folder** containing `SKILL.md` and `subagent-prompt.md` as **file** symlinks into [`.gemini/skills/<name>/`](.gemini/skills/), because the CLI only treats **directory** dirents as skill packages.

A healthy clone should report **30** discoverable skills (10 Claude + 10 Codex + 10 Gemini mirrored under `skills/`). After you publish the repo to **public GitHub**, others can install with `npx skills add owner/repo`.

```bash
# List skills the CLI discovers from this repo (run from a clone)
npx skills add . --list

# After publishing: install from your public fork into an agent
npx skills add YOUR_GITHUB_USERNAME/startup-product-context
```

## How this repository supports that workflow

- [`.productmap/`](.productmap/). Lean startup knowledge: company, strategy, discovery, analysis, delivery, operations, and raw data.
- [`AGENTS.md`](AGENTS.md) and [`CLAUDE.md`](CLAUDE.md). Entry points that send agents to the index and house rules.
- Skills. Repeatable founder PM jobs with steps and guardrails: [`.claude/skills/`](.claude/skills/) for Claude Code, [`.gemini/skills/`](.gemini/skills/) for Gemini CLI (see [`.gemini/README.md`](.gemini/README.md)).
- Codex skills. Repo-local PM skills for Codex: [`.codex/skills/`](.codex/skills/) (see [`.codex/skills/README.md`](.codex/skills/README.md)).
- [`skills/`](skills/). Symlinks for Gemini skill folders so the same `SKILL.md` files are visible to tools that only scan a top-level `skills/` directory.

Skills may reference paths from the full [product-management-context](https://github.com/productmap-io/product-management-context) taxonomy. In this repo, map them to the startup tree — see [CLAUDE.md](CLAUDE.md) for the path mapping.

## Product Map AI

[Product Map AI](https://app.productmap.io/) is where you turn structured product context into day-to-day help. Attach your startup context so assistants stay aligned with your situation instead of generic advice. Open this knowledge base from [`.productmap/INDEX.md`](.productmap/INDEX.md).

## About Product Map

[Product Map](https://www.productmap.io/) is the **product management copilot to guide your decisions.** This startup context repo is a simplified slice of that map — focused on founders validating and building before scale.
