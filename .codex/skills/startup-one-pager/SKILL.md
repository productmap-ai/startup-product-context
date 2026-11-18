---
name: startup-one-pager
description: Write a one-page startup summary covering problem, target customer, solution, business model, alternatives, ranked riskiest assumptions, and validation experiments, saved to the onepager context file.
---

# Startup one-pager — Skill

## Name

`startup-one-pager` — Turn a raw idea into one page a founder can defend, with the assumptions ranked by risk and a test for the top three.

## When to use

- You have an idea, notes, or a website, and no single page says what the company does and for whom.
- An investor, advisor, or first hire asked for "something to read" and you want it to take two minutes.
- Interviews or a pivot changed the idea and `.productmap/00_company/product/onepager.md` is stale.
- You're about to write code and can't name the assumption that kills the company if it's wrong.
- Other skills keep asking for product context and the one-pager is still a blank template.
- Use a sibling skill instead when you need a full stress test (`.claude/skills/startup-idea-validation/SKILL.md`) or the investor story (`.claude/skills/pre-seed-pitch-narrative/SKILL.md`).

## Inputs (ask user for these)

- Product or working name:
- Artifact date (YYYY-MM-DD) (use today's date unless the founder gives another):
- The idea in the founder's own words (2 to 5 sentences):
- Who has the problem (role, company type or life situation, geography):
- How they handle it today (tools, workarounds, doing nothing):
- What exists so far (nothing / prototype / pilot / paying customers):
- How you expect to make money (who pays, for what, price if known):
- Evidence so far (interview count and file paths, signups, pilots, payments):
- Known alternatives and competitors (names or URLs):
- Website, deck, or notes to read (URLs or repo paths):
- Constraints (runway in months, team size, fixed deadlines in `YYYY-MM-DD`):

## Outputs

- One-pager (Markdown). Body under 500 words plus two tables:
  - One-line summary
  - Problem
  - Target customer
  - Solution and differentiator
  - Business model
  - Competitive landscape (3 to 5 alternatives, one of them "do nothing")
  - Riskiest assumptions, scored and ranked
  - Validation experiments for the top three assumptions
  - Open questions
- Where to store it:
  - The one-pager: `.productmap/00_company/product/onepager.md` (keep the template's headings, add the missing sections)
  - Top three assumptions: new rows in the `Hypothesis Backlog` table of `.productmap/02_discovery/experiments/experiments.md`
  - Pasted website text or notes: `.productmap/06_data/research/`

## Repo knowledge to pull

- Start here: `.productmap/INDEX.md`
- Target file and its current headings: `.productmap/00_company/product/onepager.md`
- Problem evidence: `.productmap/02_discovery/user-research/problem-framing.md` and transcripts under `.productmap/06_data/interviews/`
- Customer: `.productmap/01_strategy/segmentation/segmentation.md`, `.productmap/01_strategy/segmentation/icp-b2b.md`, `.productmap/01_strategy/segmentation/icp-b2c.md`
- Differentiator and alternatives: `.productmap/00_company/product/value-proposition.md`, `.productmap/01_strategy/competitors/competitor-matrix.md`
- Business model: `.productmap/01_strategy/business-model/business-model.md` (the `Validated / Assumed` column of the Lean Canvas)
- Experiments already planned or run: `.productmap/02_discovery/experiments/experiments.md`
- Traction, if any: `.productmap/01_strategy/product-market-fit/pmf-signals.md`

## Detailed prompt (copy/paste)

```
You are a startup advisor who has seen good ideas fail on untested assumptions. Write a one-page summary of the startup below, then rank what is unproven and design the cheapest tests. Read the repo before you write, and cite every repo path you used.

Repo-first context to consult:
- Start at: .productmap/INDEX.md
- Read the target file and keep its headings: .productmap/00_company/product/onepager.md
- Read if filled in: problem-framing.md, segmentation.md, icp-b2b.md, icp-b2c.md, value-proposition.md, competitor-matrix.md, business-model.md, experiments.md, pmf-signals.md, and transcripts in .productmap/06_data/interviews/
- Read every URL or repo path the founder lists.

Constraints:
- Write every date as YYYY-MM-DD. No "next month", no "Q3".
- Invent nothing. A missing number or fact becomes an open question.
- End every claim with a label: (evidence: <repo path or source>) or (assumption: <the test that would confirm it>).
- Reject vague subjects. "People want this" fails. Name which people, in which situation.
- Keep the body under 500 words. The two tables do not count.

Startup context (founder-provided):
- Product or working name:
- Artifact date (YYYY-MM-DD):
- The idea in the founder's words:
- Who has the problem:
- How they handle it today:
- What exists so far:
- How you expect to make money:
- Evidence so far:
- Known alternatives:
- Website, deck, notes, repo paths:
- Constraints (runway, team, deadlines):

Steps:
1) List Known facts and Unknowns as bullets. Each bullet ends with its source.
2) Problem (80 words max). State who has it, what happens, how often, and what it costs them in time, money, or risk. Use a real episode from an interview if one exists.
3) Target customer. Pick one primary segment narrow enough that the founder can name ten real prospects. Give role or situation, the trigger that makes the problem urgent, today's workaround, and who pays versus who uses. Add one "Not for" line.
4) Solution and differentiator. Describe what the customer can do, in three bullets or fewer. Then state the one difference against a named alternative. Test it with this question: would a customer of that alternative switch for this reason alone?
5) Business model. State who pays, the pricing model, the price or range, the first revenue source, and the two largest cost drivers. If the price is unknown, write the open question.
6) Competitive landscape. Build a table of 3 to 5 alternatives. One row must be "Do nothing or manual workaround". Columns:
   Alternative | Type (direct / indirect / substitute / do nothing) | What the customer does with it today | Where it wins | Where it falls short | Source
7) Riskiest assumptions. List 6 to 10 across these categories: problem, customer, solution, willingness to pay, channel, feasibility. Score each one:
   - Impact if wrong, 1 to 5. 5 means the company does not work. 3 means the plan changes. 1 means a small adjustment.
   - Evidence level, 0 to 4. 0 none. 1 opinion or stated interest. 2 past behaviour (they already spend time or money on the problem). 3 commitment (time, an intro, a signed letter of intent). 4 payment.
   - Risk score = Impact x (5 - Evidence level). Rank from highest to lowest. Break ties by lower evidence level.
   Columns: Rank | Assumption | Category | Impact | Evidence level | Risk score | Evidence or source
8) Validation experiments. For the top three assumptions, choose the cheapest test that would raise the evidence level by at least one step. Use the types in experiments.md: interviews, landing page or smoke test, concierge, Wizard-of-Oz, presale or letter of intent. Columns:
   Assumption rank | Experiment type | Setup | Sample | Duration (days) | Pass threshold | Fail threshold | Cost | Decision if pass / if fail | Start date
   Propose thresholds as numbers and mark them "proposed, founder to confirm before the test starts".
9) One-line summary in the template's format: "[Product] is a [category] that helps [target user] [achieve outcome]." Write it last.
10) Open questions, ordered by which one would change the page the most.
11) Write-back map. Show which section goes under which heading of onepager.md:
    - One-line summary -> One-line Summary
    - Solution bullets -> What [Product Name] Does and Core Product Components
    - Target customer -> Target Users
    - Differentiator -> Value Proposition
    - Competitive landscape -> Product Scope vs. Adjacent Tools
    - Problem, Business model, Riskiest assumptions, Validation experiments -> new sections placed below Product Scope vs. Adjacent Tools

Output format (Markdown), in this exact order:
1. Title: <Product> one-pager, YYYY-MM-DD
2. One-line summary
3. Problem
4. Target customer
5. Solution and differentiator
6. Business model
7. Competitive landscape
8. Riskiest assumptions (ranked)
9. Validation experiments
10. Open questions
11. Write-back map
12. Repo paths referenced
```

## Workflow (runbook)

1. Confirm the inputs. If the founder gives only an idea sentence, ask for two more facts before drafting: who has the problem, and what they do about it today.
2. Read the repo:
   - Open `.productmap/INDEX.md`, then `.productmap/00_company/product/onepager.md` to see which headings are filled.
   - Read the interview transcripts in `.productmap/06_data/interviews/` before any strategy file. Past behaviour outranks the founder's opinion.
3. Run the prompt. Draft the full page in one pass, with every gap labeled as an assumption.
4. Check the customer. If you can't name ten real prospects from the description, narrow the segment and redraft sections 3 to 5.
5. Check the differentiator against the "do nothing" row. If doing nothing is cheap and tolerable, move "the problem is painful enough to act on" to the top of the assumption list.
6. Score the assumptions with the founder. Agree the Impact and Evidence level numbers out loud. The ranking matters more than the prose.
7. Set thresholds. The founder confirms each pass and fail number before any test starts. Record the date they were set.
8. Write back to the repo:
   - Update `.productmap/00_company/product/onepager.md` using the write-back map. Keep the existing headings and add the four new sections below `Product Scope vs. Adjacent Tools`.
   - Add the top three assumptions to the `Hypothesis Backlog` in `.productmap/02_discovery/experiments/experiments.md`, with the pass threshold in `Success Criterion` and status `Planned`.
   - Flip any Lean Canvas block in `.productmap/01_strategy/business-model/business-model.md` whose label changed between `Assumed` and `Validated`.
9. Re-run the skill after each experiment closes. Raise the evidence level, re-rank, and pick the next three.

## Quality checklist

- A stranger can say what the product is and who it's for after reading the one-line summary once.
- The problem names a person, a situation, a frequency, and a cost. No "users struggle with".
- The target customer is one segment, and the founder can list ten real prospects who match it.
- The differentiator is stated against a named alternative, and "do nothing" is a row in the table.
- Every claim carries an evidence or assumption label. Evidence labels point to a real path or source.
- 6 to 10 assumptions are scored with the same two scales, and the risk score arithmetic is right.
- Each of the top three assumptions has one experiment with numeric pass and fail thresholds, a sample, a duration, and a start date in `YYYY-MM-DD`.
- No number appears without a source. Unknown prices, market sizes, and conversion rates sit under open questions.
- The body is under 500 words and the write-back map covers every section.
- `Repo paths referenced` lists every file read, starting with `.productmap/INDEX.md`.

## Related on Product Map

- Agent: **[Validate startup idea](https://app.productmap.io/agents/startup-idea-validation)** — challenge your startup idea and shape vision.
- Workflow: **[Product idea to MVP scope](https://app.productmap.io/workflows/product-idea-to-mvp-scope)** — validate the product idea, define strategy and roadmap, then scope and challenge the MVP.

More AI PM agents from Product Map: https://www.productmap.io/
