---
name: investor-pipeline-tracker
description: Build and maintain the investor pipeline table with fit scores, statuses, last touch and dated next actions, plus a weekly review and intro-request drafts for the current raise.
---

# Investor pipeline tracker — Skill

## Name

`investor-pipeline-tracker` — Run the raise like a sales pipeline. Every investor has a fit reason, a status, and a dated next action.

## When to use

- You decided to raise and have a loose list of names in notes, email, and LinkedIn.
- The raise is live and you can't say how many conversations are open or which ones went quiet.
- You need to ask people for intros and want each request short and forwardable.
- It's the weekly review and you want the five actions that keep the round moving.
- Investors passed and you want the reasons counted, so the pitch improves.
- Use a sibling skill instead when you haven't set the round size or timing (`.claude/skills/fundraising-strategy/SKILL.md`) or need answers to hard questions (`.codex/skills/investor-qa-prep/SKILL.md`).

## Inputs (ask user for these)

- Company name and one-line description:
- Artifact date (YYYY-MM-DD) (use today's date unless the founder gives another):
- Round (stage, target amount, instrument, target close in `YYYY-MM-DD`):
- Geography and sector you're raising in:
- Investor names you already have (firm or angel, partner, anything known about stage, check size, thesis):
- Warm paths (who knows whom, and how well):
- Conversations so far (who, date, what happened, what they asked for):
- Amounts soft-circled and committed:
- Investors to exclude (conflicts, competitors' backers, personal reasons):
- Hours per week you can spend on the raise:

## Outputs

- Updated pipeline (Markdown) containing:
  - Pipeline table with fit score, priority, status, last touch, next step, and next step date
  - Stage definitions that match the statuses used in the table
  - Weekly review: counts by status, stale threads, overdue steps, pass reasons, round math, top five actions
  - Intro-request drafts for the highest-priority investors with a warm path
  - Research gaps: facts about investors still marked `?`
- Where to store it:
  - `.productmap/00_company/fundraising/investor-pipeline.md` (existing template; keep its four sections)
  - Pasted investor research: `.productmap/06_data/research/`

## Repo knowledge to pull

- Start here: `.productmap/INDEX.md`
- Target file: `.productmap/00_company/fundraising/investor-pipeline.md` (sections `Pipeline`, `Stage Definitions`, `Follow-up Cadence`, `Round Math`)
- Round facts: `.productmap/00_company/fundraising/fundraising-strategy.md`
- Advisors and angels who can open intro paths: `.productmap/00_company/team.md`
- One-line description and traction for the blurb: `.productmap/00_company/product/onepager.md`, `.productmap/01_strategy/product-market-fit/pmf-signals.md`
- Deck status: `.productmap/00_company/fundraising/pitch-deck.md`
- Runway, which sets the deadline: `.productmap/05_operations/finance/runway-burn.md`

## Detailed prompt (copy/paste)

```
You are a founder's chief of staff for a fundraise. Turn the notes below into a clean investor pipeline, score each investor for fit, run the weekly review, and draft intro requests. Read the repo first and cite every path you used.

Repo-first context to consult:
- Start at: .productmap/INDEX.md
- Read and keep the structure of: .productmap/00_company/fundraising/investor-pipeline.md
- Read: fundraising-strategy.md, team.md, onepager.md, pmf-signals.md, pitch-deck.md, runway-burn.md
- Read any path the founder lists.

Constraints:
- Write every date as YYYY-MM-DD.
- Invent nothing about investors. Stage focus, check size, and thesis come from the founder or from a public page you read, cited with URL and access date. Otherwise write "?".
- Do not add investors the founder did not name unless you can browse and cite the source. Without browsing, list search criteria instead.
- Label each fit reason (evidence: <source>) or (assumption: <how to check>).
- Draft messages only. The founder sends them.
- You are not a lawyer. Rules on who you may approach and what you may say about a round differ by country. Tell the founder to confirm with a lawyer before announcing the round publicly or signing a term sheet.

Raise context (founder-provided):
- Company and one-liner:
- Artifact date (YYYY-MM-DD):
- Round (stage, amount, instrument, target close):
- Geography and sector:
- Investor names and what is known:
- Warm paths:
- Conversations so far:
- Soft-circled and committed amounts:
- Exclusions:
- Hours per week for the raise:

Steps:
1) Build the Pipeline table, one row per investor. Columns:
   Firm / Angel | Partner | Type | Stage Fit | Check Size | Fit Reason | Fit Score | Priority | Intro Path | Status | Last Touch | Next Step | Next Step Date | Notes
   Type is one of: angel, angel syndicate, pre-seed fund, seed fund, accelerator, corporate, family office, other.
2) Fit Score, 0 to 10. Score each part 0, 1, or 2. An unknown scores 0 and gets a "?".
   - Stage: invests at this stage (2), sometimes (1), no (0)
   - Check size: the typical check fits this round (2), partly (1), no (0)
   - Thesis: sector, model, and geography match a stated focus (2), partly (1), no (0)
   - Conflict: no competing portfolio company known (2), adjacent company (1), direct competitor (0)
   - Warm path: someone they trust will vouch for you (2), weak tie (1), cold (0)
   Priority: A for 8 to 10, B for 5 to 7, C for 0 to 4. C rows stay in Research and get no outreach this week.
3) Status. Use this ladder and update the Stage Definitions table to match:
   Research -> Intro requested -> First meeting -> Follow-up -> Partner meeting -> Term sheet -> Soft-circled -> Committed, with exits Passed and Parked.
   The template's "In diligence" splits into Follow-up (questions, data shared) and Partner meeting (presenting to the decision makers). For angels, skip Partner meeting and Term sheet. Soft-circled is a verbal yes with an amount. It counts as money only when signed and wired. Log the stated reason on every Passed row.
4) Every row in a live status needs a Next Step that starts with a verb and a Next Step Date. Live means Intro requested through Soft-circled.
5) Weekly review:
   - Counts by status, and rows that moved since the last review
   - Stale threads: live rows where Last Touch is 10 or more days old. Apply the file's cadence: nudge at day 3 to 4, once more at day 10, then mark Parked.
   - Overdue: rows where Next Step Date is before the artifact date
   - Pass reasons, grouped and counted
   - Round Math: target raise, soft-circled total, committed total, live conversations
   - Conversion between statuses from this pipeline's own counts. With fewer than ten first meetings write "too few to read".
   - Top five actions for the week, each with a row reference and a date, sized to the hours available
6) Intro-request drafts for each A row in Research with a named warm path. Two parts:
   - Ask to the connector, 60 words or fewer. Say why this investor, and make "no" easy.
   - Forwardable blurb, 120 words or fewer: what the company does in one line, one traction fact with its source, the round stage, why this investor fits, and a placeholder for the deck link. No superlatives.
7) Research gaps: list every "?" with the page or person that would answer it.

Output format (Markdown), in this exact order:
1. Title: <Company> investor pipeline, YYYY-MM-DD
2. Pipeline
3. Stage Definitions
4. Weekly review
5. Round Math
6. Intro-request drafts
7. Research gaps
8. Repo paths referenced
```

## Workflow (runbook)

1. Confirm the round facts from `.productmap/00_company/fundraising/fundraising-strategy.md`. If the target raise or the stage is blank, stop and fill that file first.
2. Collect names. Ask the founder to paste every list they have, however rough. Read `.productmap/00_company/team.md` for advisors and angels who can make intros.
3. Run the prompt. Score fit with the founder present, because they know the warm paths.
4. Sort the table by Priority, then by Status. Work A rows first. Batch first meetings into a two to three week window, as the file's momentum rule says.
5. Draft intro requests. The founder edits the first line for each connector and sends them.
6. Write back to `.productmap/00_company/fundraising/investor-pipeline.md`:
   - Replace the `Pipeline` table with the wider one. Keep the original column names and add the new ones.
   - Update `Stage Definitions` so every status in the table has a row.
   - Update the `Round Math` values. Leave `Follow-up Cadence` as written unless the founder changes it.
7. Run the weekly review on the same weekday each week. It takes 20 minutes with a clean table.
8. After each meeting, update Status, Last Touch, Next Step, and Next Step Date the same day. Send questions you couldn't answer to `.codex/skills/investor-qa-prep/SKILL.md`.
9. When a term sheet or investment document arrives, have a lawyer read it before you reply on terms.

## Quality checklist

- Every row has a Type, a Fit Reason with a label, a Fit Score, and a Priority.
- Fit Score arithmetic is right and unknown parts are marked `?`, not guessed.
- Statuses in the table match the rows of `Stage Definitions` one to one.
- Every live row has a Next Step that starts with a verb and a Next Step Date in `YYYY-MM-DD`.
- No row has a Last Touch 10 or more days old without a nudge planned or a move to Parked.
- Every Passed row records the stated reason.
- Soft-circled and committed totals are separate, and only signed and wired money counts as committed.
- No investor, check size, or thesis was invented. Sources carry a URL and an access date.
- Each intro request has a 60-word ask and a 120-word blurb with one sourced traction fact.
- `Repo paths referenced` lists every file read, starting with `.productmap/INDEX.md`.

## Related on Product Map

- Agent: **[Prepare early stage pitch](https://app.productmap.io/agents/preseed-investor-pitch)** — turn notes into a script for an investor pitch deck.

More AI PM agents from Product Map: https://www.productmap.io/
