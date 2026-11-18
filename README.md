# Startup product context

> Built by **[Product Map](https://www.productmap.io/)**, the AI operating system for product decisions. Run PM agents on this context in the [web app](https://app.productmap.io/), or **[install the plugin for Cursor, VS Code, and Antigravity](https://www.productmap.io/product-management-agents-for-cursor-vscode)** to run them next to your coding agents.

This repository is a **simplified product context for early-stage startups** — a lean, founder-focused knowledge base and agentic workspace. It covers what you need before and during product–market fit: company context, strategy, discovery, metrics, delivery, and operations — without the full lifecycle breadth of a mature PM organization.

The [`.productmap/`](.productmap/) folder is a curated startup taxonomy (company, strategy, discovery, analysis, delivery, operations, raw data). On top of that tree, [AGENTS.md](AGENTS.md), [CLAUDE.md](CLAUDE.md), and [GEMINI.md](GEMINI.md) spell out how agents should behave; repeatable workflows live under [`.claude/skills/`](.claude/skills/) (Claude Code), [`.codex/skills/`](.codex/skills/) (Codex), and [`.gemini/skills/`](.gemini/skills/) (Gemini CLI). Point Cursor, Claude Code, Codex, and Gemini CLI at one versioned source of truth instead of restarting context in every tool.

**Related:** For the full product management lifecycle (templates, frameworks, tools, people practices), see [product-management-context](https://github.com/productmap-ai/product-management-context).

## Get started with this repository

**What you are building.** A repo-first context layer for founders and early PMs: curated startup topics, worksheets, and checklists in files agents can read. Cursor, Claude Code, Codex, and Gemini CLI sit on top as different runners; you pick the tool for the job and keep one repo as the handoff surface.

**A setup that works well**

- **Cursor** as the hub. Open this repo as the workspace so chat and edits see [AGENTS.md](AGENTS.md), [CLAUDE.md](CLAUDE.md), and [GEMINI.md](GEMINI.md) without path gymnastics. Use the Claude Code plugin for workflows that match [`.claude/skills/`](.claude/skills/). Use the Codex plugin with the same repo so Codex follows [AGENTS.md](AGENTS.md) (mirrored in [`.codex/README.md`](.codex/README.md)) and [`.codex/skills/`](.codex/skills/) (see [`.codex/skills/README.md`](.codex/skills/README.md)).
- **Claude Code** for skill-driven founder PM runs. The plugin reads [CLAUDE.md](CLAUDE.md) and routes recurring jobs through the right skill under [`.claude/skills/`](.claude/skills/) instead of one-off prompts.
- **Codex (inside Cursor)** when you want Codex-specific behavior and repo-local skills. Keep initiative outputs under `.productmap/00_company/product/` and raw inputs under `.productmap/06_data/` as [AGENTS.md](AGENTS.md) describes.
- **Gemini CLI** for jobs that need long-context synthesis, structured multi-section docs, or batch turns over the same tree. Install the Gemini CLI, open terminal in Cursor, `cd` to this repo, and rely on [GEMINI.md](GEMINI.md) plus [`.gemini/skills/`](.gemini/skills/) (see [`.gemini/README.md`](.gemini/README.md)). Optional: [`.gemini/settings.json`](.gemini/settings.json) for CLI defaults.
- **Product Map** ([web app](https://app.productmap.io/)) to run PM [agents](https://app.productmap.io/agents) and [workflows](https://app.productmap.io/workflows) on this project context. Open the linked project from [`.productmap/INDEX.md`](.productmap/INDEX.md). To run the same agents inside your editor, [install the Product Map plugin for Cursor, VS Code, or Antigravity](https://www.productmap.io/product-management-agents-for-cursor-vscode).

**Steps**

1. Clone or copy this repository and open it in Cursor.
2. Fill in `.productmap/` with your startup's facts — team, product one-pager, ICP, roadmap, metrics, and so on. Templates are embedded in each file; there is no separate templates folder.
3. Skim [`.productmap/INDEX.md`](.productmap/INDEX.md) so you know where worksheets and overviews live.
4. For day-to-day work in Cursor, `@`-mention or paste paths to the relevant files under `.productmap/` instead of pasting unstructured blobs into chat.
5. For a recurring task (idea validation, pitch narrative, pricing page audit, launch readiness review), open the matching folder under [`.claude/skills/`](.claude/skills/), [`.codex/skills/`](.codex/skills/), or [`.gemini/skills/`](.gemini/skills/) and follow `SKILL.md` rather than improvising.
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

This repository is structured so the open [`skills`](https://github.com/vercel-labs/skills) CLI can discover installable skills: each skill is a folder with a `SKILL.md` that includes YAML frontmatter (`name` and `description` as plain strings). Skills live under [`.claude/skills/`](.claude/skills/) (Claude Code), [`.codex/skills/`](.codex/skills/) (Codex), and [`.gemini/skills/`](.gemini/skills/) (Gemini CLI). The CLI scans `.claude/skills/` and `.codex/skills/` on its own. [`skills.sh.json`](skills.sh.json) adds `.gemini/skills/` to its search paths, so the Gemini skills install from their real files (`SKILL.md` plus `subagent-prompt.md`).

The skills are founder jobs, and each tool gets its own list, built around the startup [agents](https://app.productmap.io/agents) on Product Map. Every `SKILL.md` ends with a "Related on Product Map" section that links the matching agent and, where one fits, a [workflow](https://app.productmap.io/workflows), so you can run the same job on your own product context.

**Claude Code: practice guides** ([`.claude/skills/`](.claude/skills/)). Each one teaches a founder practice end to end: when to use it, the frameworks, a workflow, pitfalls and artifact skeletons.

| Skill | What it does | Product Map agent |
| --- | --- | --- |
| [`startup-idea-validation`](.claude/skills/startup-idea-validation/SKILL.md) | Stress-test the problem, audience, fit and market; choose what to validate first | [Validate startup idea](https://app.productmap.io/agents/startup-idea-validation) |
| [`pre-seed-pitch-narrative`](.claude/skills/pre-seed-pitch-narrative/SKILL.md) | Build the investor story in eight beats, from problem to ask | [Prepare early stage pitch](https://app.productmap.io/agents/preseed-investor-pitch) |
| [`fundraising-strategy`](.claude/skills/fundraising-strategy/SKILL.md) | Decide whether, when and how much to raise, and from whom | [Prepare early stage pitch](https://app.productmap.io/agents/preseed-investor-pitch) |
| [`value-proposition-positioning`](.claude/skills/value-proposition-positioning/SKILL.md) | Value Proposition Canvas, fit check and a positioning statement to test | [Build unique value proposition](https://app.productmap.io/agents/value-proposition-positioning) |
| [`monetization-pricing`](.claude/skills/monetization-pricing/SKILL.md) | Pick the pricing model, value metric and tiers; check willingness to pay | [Define monetization strategy](https://app.productmap.io/agents/monetization-pricing) |
| [`founder-led-sales`](.claude/skills/founder-led-sales/SKILL.md) | Go from ICP to first paying customers through outreach, discovery calls and closing | [Define ICP and segments](https://app.productmap.io/agents/ideal-customer-profile-icp) |
| [`growth-loops-engine`](.claude/skills/growth-loops-engine/SKILL.md) | Find the bottleneck, pick the growth engine and design growth loops | [Build product growth strategy](https://app.productmap.io/agents/growth-marketing) |
| [`digital-marketing-campaigns`](.claude/skills/digital-marketing-campaigns/SKILL.md) | Growth brief, channel choice and ranked campaign ideas | [Create digital marketing ideas](https://app.productmap.io/agents/digital-product-marketing) |
| [`runway-burn-planning`](.claude/skills/runway-burn-planning/SKILL.md) | Burn, runway, scenarios, and cut or raise triggers | [Calculate unit economics](https://app.productmap.io/agents/unit-economics) |
| [`cofounder-alignment`](.claude/skills/cofounder-alignment/SKILL.md) | Roles, equity, vesting, decision rights and working norms | [Enable team collaboration](https://app.productmap.io/agents/team-collaboration-leadership) |

**Codex: artifact runbooks** ([`.codex/skills/`](.codex/skills/)). Each one produces a single artifact from stated inputs, with a copy-paste prompt and a quality checklist.

| Skill | What it does | Product Map agent |
| --- | --- | --- |
| [`startup-one-pager`](.codex/skills/startup-one-pager/SKILL.md) | One-pager with ranked riskiest assumptions | [Validate startup idea](https://app.productmap.io/agents/startup-idea-validation) |
| [`investor-qa-prep`](.codex/skills/investor-qa-prep/SKILL.md) | Hard investor questions with drafted answers and evidence gaps | [Prepare early stage pitch](https://app.productmap.io/agents/preseed-investor-pitch) |
| [`investor-pipeline-tracker`](.codex/skills/investor-pipeline-tracker/SKILL.md) | Investor target list, stages and next actions | [Prepare early stage pitch](https://app.productmap.io/agents/preseed-investor-pitch) |
| [`landing-page-smoke-test`](.codex/skills/landing-page-smoke-test/SKILL.md) | Landing copy plus a test card with pass/fail criteria | [Build unique value proposition](https://app.productmap.io/agents/value-proposition-positioning) |
| [`pricing-page-audit`](.codex/skills/pricing-page-audit/SKILL.md) | Scored pricing-page audit across six pillars, with fixes | [Define monetization strategy](https://app.productmap.io/agents/monetization-pricing) |
| [`mvp-build-stack-decision`](.codex/skills/mvp-build-stack-decision/SKILL.md) | No-code, low-code, AI-assisted or custom, as a decision record | [Scope and challenge MVP](https://app.productmap.io/agents/mvp-scope-decision) |
| [`launch-channel-test-cards`](.codex/skills/launch-channel-test-cards/SKILL.md) | First launch plan and channel test cards with kill, iterate or scale rules | [Build go-to-market strategy](https://app.productmap.io/agents/go-to-market-strategy) |
| [`growth-experiment-sprint`](.codex/skills/growth-experiment-sprint/SKILL.md) | Four-week growth sprint with three experiment cards | [Build product growth strategy](https://app.productmap.io/agents/growth-marketing) |
| [`design-partner-program`](.codex/skills/design-partner-program/SKILL.md) | Design-partner criteria, offer, feedback cadence and path to paid | [Define ICP and segments](https://app.productmap.io/agents/ideal-customer-profile-icp) |
| [`startup-financial-model`](.codex/skills/startup-financial-model/SKILL.md) | 18–24 month driver-based model with labeled assumptions | [Calculate unit economics](https://app.productmap.io/agents/unit-economics) |

**Gemini CLI: long-context synthesis** ([`.gemini/skills/`](.gemini/skills/)). Each one reads a lot at once (the whole context tree, many transcripts, long pages) and returns one structured document. Every folder pairs `SKILL.md` with a `subagent-prompt.md`.

| Skill | What it does | Product Map agent |
| --- | --- | --- |
| [`startup-launch-readiness-review`](.gemini/skills/startup-launch-readiness-review/SKILL.md) | Reads the whole context tree and scores a 12-step launch checklist | [Track startup launch](https://app.productmap.io/agents/startup-launch-tracker) |
| [`startup-context-bootstrap`](.gemini/skills/startup-context-bootstrap/SKILL.md) | Turns a site, deck and raw notes into filled context files | [Define strategy and roadmap](https://app.productmap.io/agents/product-strategy-roadmap) |
| [`market-sizing-decision-memo`](.gemini/skills/market-sizing-decision-memo/SKILL.md) | Bottom-up TAM/SAM/SOM and a one-page decision memo | [Run market research](https://app.productmap.io/agents/market-research) |
| [`competitor-teardown-matrix`](.gemini/skills/competitor-teardown-matrix/SKILL.md) | Public pages into a 0–3 matrix and match, ignore or differentiate calls | [Run competitor analysis](https://app.productmap.io/agents/competitor-analysis) |
| [`pivot-or-persevere-review`](.gemini/skills/pivot-or-persevere-review/SKILL.md) | Evidence against kill criteria, a verdict per assumption, and a decision memo | [Validate startup idea](https://app.productmap.io/agents/startup-idea-validation) |
| [`investor-update-memo`](.gemini/skills/investor-update-memo/SKILL.md) | Monthly investor update from metrics and notes | [Prepare early stage pitch](https://app.productmap.io/agents/preseed-investor-pitch) |
| [`launch-retro-synthesis`](.gemini/skills/launch-retro-synthesis/SKILL.md) | 30-day post-launch retro across channels, funnel and feedback | [Build go-to-market strategy](https://app.productmap.io/agents/go-to-market-strategy) |
| [`pricing-research-synthesis`](.gemini/skills/pricing-research-synthesis/SKILL.md) | Willingness-to-pay research and competitor pricing into a recommendation | [Define monetization strategy](https://app.productmap.io/agents/monetization-pricing) |
| [`mvp-scope-cut-review`](.gemini/skills/mvp-scope-cut-review/SKILL.md) | Challenges the backlog against the riskiest assumption, then keep, cut or defer | [Scope and challenge MVP](https://app.productmap.io/agents/mvp-scope-decision) |
| [`founder-weekly-review`](.gemini/skills/founder-weekly-review/SKILL.md) | One-page weekly review of metrics, runway, experiments and priorities | [Make data-driven decisions](https://app.productmap.io/agents/data-driven-product-decisions) |

A healthy clone should report **30** discoverable skills (10 Claude + 10 Codex + 10 Gemini). After you publish the repo to **public GitHub**, others can install with `npx skills add owner/repo`.

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
- [`skills.sh.json`](skills.sh.json). Tells the `skills` CLI to also look for skills under `.gemini/skills/`.

All skills here cite this repo's startup tree directly. For general PM skills (PRDs, OKRs, prioritization, research synthesis), see [product-management-context](https://github.com/productmap-ai/product-management-context). If you install those skills here, [CLAUDE.md](CLAUDE.md) has the path mapping.

## About Product Map

[Product Map](https://www.productmap.io/) is the **AI operating system for product decisions**: proactive AI agents covering the full product lifecycle, from strategy to delivery. It is built for teams that ship fast and can't afford to build the wrong thing.

AI-native teams ship fast, and engineering and design already have AI agents. Product does not. The bottleneck is no longer shipping. It's what to build, for whom, and why.

**Product context in. PM decisions out. Let your coding agents build them.** Connect your product context once. PM agents then handle strategy, specs, pricing, and go-to-market, grounded in your product and proven PM practice. Decisions go straight to your coding agents to build.

- **Multi-user, multi-agent.** People and agents share one environment, organized on top of your product context. Everybody is aligned. Not isolated chats.
- **Agentic workflows.** AI does the work. Agents perform PM tasks chained in workflows, all grounded in your product context, not generic prompts.
- **Knowledge-backed.** Every decision is backed by industry-standard frameworks and resources from top PMs, right when you make it. Not buried in a wiki.

This startup context repo is a simplified slice of that context layer, focused on founders validating and building before scale. Attach it so agents stay aligned with your situation instead of giving generic advice. Open the knowledge base from [`.productmap/INDEX.md`](.productmap/INDEX.md).

## Get Product Map

- **Website:** [www.productmap.io](https://www.productmap.io/)
- **Web app:** [app.productmap.io](https://app.productmap.io/), with PM [agents](https://app.productmap.io/agents) and [workflows](https://app.productmap.io/workflows)
- **Cursor, VS Code, and Antigravity:** [install the Product Map plugin](https://www.productmap.io/product-management-agents-for-cursor-vscode) to run PM agents next to your coding agents, on the product context in this repo
