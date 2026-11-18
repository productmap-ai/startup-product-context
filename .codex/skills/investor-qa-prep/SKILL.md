---
name: investor-qa-prep
description: Build a bank of 25 to 40 hard investor questions with short answers, evidence paths, gaps, and a plan to close the five weakest answers before the first meeting.
---

# Investor Q&A prep — Skill

## Name

`investor-qa-prep` — Prepare honest, short answers to the questions investors ask after the pitch, and find the five answers that need work.

## When to use

- First investor meetings are booked and the deck is drafted, but nobody has asked you a hard question yet.
- An investor passed and you want to turn the stated reason into a better answer.
- Two co-founders give different numbers for the same metric.
- You're applying to an accelerator and the form asks about competition, traction, and use of funds.
- A partner meeting or diligence call is coming and the questions get more specific.
- Use a sibling skill instead when the story itself is unclear (`.claude/skills/pre-seed-pitch-narrative/SKILL.md`) or you haven't decided whether to raise (`.claude/skills/fundraising-strategy/SKILL.md`).

## Inputs (ask user for these)

- Company name:
- Artifact date (YYYY-MM-DD) (use today's date unless the founder gives another):
- Round (stage, target amount, instrument if decided):
- Who you're meeting (angel, pre-seed fund, seed fund, accelerator) and names if known:
- Meeting dates (`YYYY-MM-DD`):
- Current traction numbers and where each one comes from:
- Deck or narrative to read (default `.productmap/00_company/fundraising/pitch-deck.md`):
- Questions investors already asked, and pass reasons (paste them):
- Topics you hope nobody asks about:
- Numbers you can't share or don't trust yet:

## Outputs

- Investor Q&A document (Markdown) containing:
  - Readiness summary: question count and average score per group
  - Numbers sheet: one agreed value and source for each metric you'll quote
  - Question bank: 25 to 40 questions in eight groups, each with a short answer, evidence, gap, and score
  - The five weakest answers with a closing plan and an honest interim answer
  - Claims to stop making until evidence exists
  - Mismatches found between repo files
- Where to store it:
  - New dated file: `.productmap/00_company/fundraising/investor-qa-YYYY-MM-DD.md`
  - Real questions heard in meetings: the `Notes` column of `.productmap/00_company/fundraising/investor-pipeline.md`

## Repo knowledge to pull

- Start here: `.productmap/INDEX.md`
- The story being questioned: `.productmap/00_company/fundraising/pitch-deck.md`, `.productmap/00_company/product/onepager.md`
- Round facts: `.productmap/00_company/fundraising/fundraising-strategy.md`, `.productmap/05_operations/finance/runway-burn.md`, `.productmap/05_operations/finance/financial-model.md`
- Past objections: `.productmap/00_company/fundraising/investor-pipeline.md`
- Traction: `.productmap/01_strategy/product-market-fit/pmf-signals.md`, `.productmap/03_analysis/kpis-metrics/metrics-tracking.md`, `.productmap/06_data/interviews/`
- Business model: `.productmap/01_strategy/business-model/business-model.md`, `.productmap/03_analysis/unit-economics/unit-economics.md`
- Competition: `.productmap/01_strategy/competitors/competitor-matrix.md`
- Team and ownership: `.productmap/00_company/team.md`, `.productmap/05_operations/legal/founder-agreements.md`, `.productmap/05_operations/legal/incorporation.md`

## Detailed prompt (copy/paste)

```
You are an early-stage investor preparing to question a founder, and then the founder's coach. Write the questions an investor at this stage would ask, draft the shortest honest answer to each from the repo, and show where the evidence runs out. Read the repo first and cite every path you used.

Repo-first context to consult:
- Start at: .productmap/INDEX.md
- Read: pitch-deck.md, fundraising-strategy.md, investor-pipeline.md, onepager.md, pmf-signals.md, metrics-tracking.md, business-model.md, unit-economics.md, competitor-matrix.md, team.md, founder-agreements.md, incorporation.md, runway-burn.md, financial-model.md
- Read interview transcripts in .productmap/06_data/interviews/ and any path the founder lists.

Constraints:
- Write every date as YYYY-MM-DD.
- Invent nothing. If the repo and the founder give no answer, the answer is "Unknown" and the score is 0.
- Each answer ends with (evidence: <repo path or source>) or (assumption: <the test that would confirm it>).
- Answers are 60 words or fewer. A founder says them aloud in 30 seconds.
- Lead with the number or the fact. No adjectives in place of data.
- You are not a lawyer or accountant. For valuation, instrument terms, equity, vesting, tax, and securities rules, state the founder's facts, list the open points, and write "confirm with a lawyer or accountant". Do not propose a valuation or a cap.

Company context (founder-provided):
- Company:
- Artifact date (YYYY-MM-DD):
- Round (stage, amount, instrument):
- Investor type and names:
- Meeting dates:
- Traction numbers and sources:
- Deck or narrative path:
- Questions and pass reasons already heard:
- Topics to avoid:
- Numbers not to share:

Steps:
1) Numbers sheet. List every metric the founder will quote. Columns: Metric | Value | As of (YYYY-MM-DD) | Source | Also appears in. Where two files disagree, list both values under Mismatches and do not pick one.
2) Write 25 to 40 questions across these eight groups, at least three per group. Put more questions in the groups where the repo has the least evidence.
   A. Problem and market
   B. Product
   C. Traction
   D. Business model
   E. Competition
   F. Team
   G. Round and terms
   H. Risks
   Include the questions the founder already heard and the topics they want to avoid. Tag each question "opener" or "follow-up". At least eight are follow-ups that press on a previous answer.
3) For each question fill one table row:
   # | Group | Question | Why they ask | Short answer | Evidence | Gap | Score | Likelihood
   - Score 3: the answer rests on evidence in the repo or a cited source.
   - Score 2: partly evidenced. One key number or fact is an assumption.
   - Score 1: assumption only, with a defined test.
   - Score 0: no answer yet.
   - Likelihood (High / Medium / Low): how likely this investor type is to ask it.
4) Readiness summary. Columns: Group | Questions | Average score | Lowest-scored question.
5) The five weakest answers. Sort by score ascending, then by likelihood descending. For each one write:
   - What is missing
   - The action that closes it
   - Owner and by-date (YYYY-MM-DD)
   - The answer after the action succeeds
   - Honest interim answer, in three parts: what we know, what we don't know, how and when we find out
6) Claims to stop making. List statements in the deck or one-pager that no evidence supports, with the file and the fix.
7) For group G, add a short "confirm before the meeting" list: instrument, amount, use of funds, existing commitments, cap table, vesting, IP assignment. Mark each as confirmed by a lawyer or accountant, or not yet.

Output format (Markdown), in this exact order:
1. Title: <Company> investor Q&A, YYYY-MM-DD
2. Readiness summary
3. Numbers sheet
4. Question bank (groups A to H)
5. Five weakest answers and how to close them
6. Claims to stop making
7. Round and terms: confirm before the meeting
8. Mismatches between files
9. Repo paths referenced
```

## Workflow (runbook)

1. Confirm the inputs. The round, the investor type, and the meeting date change which questions matter.
2. Read the repo:
   - Start at `.productmap/INDEX.md`, then the deck and `.productmap/00_company/fundraising/fundraising-strategy.md`.
   - Pull pass reasons and objections from `.productmap/00_company/fundraising/investor-pipeline.md`. Real questions go in first.
3. Build the numbers sheet before any answer. One value per metric, one date, one source.
4. Run the prompt and produce the full bank in one pass.
5. Review scores with the founder. Lower any score where the founder hesitates or the source is older than 60 days.
6. Work the five weakest answers:
   - If the action is a test, add it to `.productmap/02_discovery/experiments/experiments.md`.
   - If the action is a legal or accounting check, book it before the first meeting.
7. Rehearse aloud. Read each question, answer without notes, and time it. Rewrite any answer that runs past 30 seconds.
8. Save the document as `.productmap/00_company/fundraising/investor-qa-YYYY-MM-DD.md`.
9. After each meeting, add new questions to the bank and log them in the `Notes` column of the pipeline. Re-run the skill when a metric changes or after every five meetings.

## Quality checklist

- The bank holds 25 to 40 questions, at least three in each of the eight groups, and at least eight follow-ups.
- Every answer is 60 words or fewer and opens with a number or a fact.
- Every answer has an evidence or assumption label, and evidence labels point to a real path or source.
- Scores follow the 0 to 3 scale. No answer scores 3 on the founder's opinion alone.
- The numbers sheet has one value per metric with an as-of date, and mismatches are listed, not resolved by guessing.
- The five weakest answers each have an action, an owner, a date in `YYYY-MM-DD`, and an honest interim answer.
- Questions the founder wanted to avoid are in the bank.
- Round and terms answers state facts and open points only, and tell the founder to confirm with a lawyer or accountant.
- No valuation, cap, or market size was invented.
- `Repo paths referenced` lists every file read, starting with `.productmap/INDEX.md`.

## Related on Product Map

- Agent: **[Prepare early stage pitch](https://app.productmap.io/agents/preseed-investor-pitch)** — turn notes into a script for an investor pitch deck.

More AI PM agents from Product Map: https://www.productmap.io/
