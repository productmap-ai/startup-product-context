---
name: landing-page-smoke-test
description: Write landing page copy from the positioning statement and a test card with hypothesis, traffic source, sample size, duration, pass and fail thresholds, and guardrails for an honest waitlist smoke test.
---

# Landing page smoke test — Skill

## Name

`landing-page-smoke-test` — Test demand and messaging with a real page and a real waitlist before you build, with the pass and fail numbers set in advance.

## When to use

- You have a positioning statement and want to know whether strangers in your segment respond to it.
- You're choosing between two messages and interviews gave mixed signals.
- "Demand exists" sits near the top of your riskiest assumptions and nothing above opinion supports it.
- You plan to spend on ads or outreach and want a measured conversion rate first.
- The product isn't ready and you want a waitlist of people who match the ICP.
- Use a sibling skill instead when the positioning itself is missing (`.claude/skills/value-proposition-positioning/SKILL.md`) or the product is live and you're testing launch channels (`.codex/skills/launch-channel-test-cards/SKILL.md`).

## Inputs (ask user for these)

- Product name:
- Artifact date (YYYY-MM-DD) (use today's date unless the founder gives another):
- Positioning statement (or the path to it):
- Target segment for this test (one ICP slice):
- Availability today (idea / prototype / private beta / live) and the earliest date anyone gets access:
- The action you want from a visitor (join waitlist / request early access / book a call):
- Traffic source and how you reach the segment (community, outreach, ads, newsletter):
- Budget cap and cost per visitor if known:
- Real proof you're allowed to publish (pilot results, quotes with permission, founder background):
- Page builder and analytics tool:
- Countries your visitors come from (for consent and privacy rules):

## Outputs

- Landing page copy (Markdown): headline, subhead, three benefits, proof, call to action with an availability line, FAQ, and one alternative headline
- Test card: hypothesis, audience and traffic source, sample size, duration, primary metric, pass and fail thresholds, guardrails, decision rule
- Honesty check: a list of what the page promises and whether each promise is true today
- Where to store it:
  - Copy: `.productmap/00_company/product/landing-page-copy-YYYY-MM-DD.md`
  - Test card: a row in `Hypothesis Backlog` and, after the run, a row in `Experiment Log` of `.productmap/02_discovery/experiments/experiments.md`
  - Exports of signups and traffic: `.productmap/06_data/analytics/`

## Repo knowledge to pull

- Start here: `.productmap/INDEX.md`
- Positioning, pains, and gains: `.productmap/00_company/product/value-proposition.md`
- Segment and its language: `.productmap/01_strategy/segmentation/icp-b2b.md`, `.productmap/01_strategy/segmentation/icp-b2c.md`, `.productmap/06_data/interviews/`
- The named alternative: `.productmap/01_strategy/competitors/competitor-matrix.md`
- Experiment format and earlier results: `.productmap/02_discovery/experiments/experiments.md`
- Channel bets: `.productmap/02_discovery/marketing/gtm-launch.md`
- Events to track: `.productmap/03_analysis/kpis-metrics/metrics-tracking.md`
- Data you collect and consent: `.productmap/05_operations/legal/privacy-compliance.md`

## Detailed prompt (copy/paste)

```
You are a conversion copywriter and experiment designer for an early-stage startup. Write landing page copy from the positioning below and a test card that says, before launch, what result counts as a pass. Read the repo first and cite every path you used.

Repo-first context to consult:
- Start at: .productmap/INDEX.md
- Read: value-proposition.md, icp-b2b.md or icp-b2c.md, competitor-matrix.md, experiments.md, gtm-launch.md, metrics-tracking.md, privacy-compliance.md
- Read interview transcripts in .productmap/06_data/interviews/ and reuse the customer's own words.

Constraints:
- Write every date as YYYY-MM-DD.
- Invent nothing. No made-up testimonials, logos, user counts, or results. If no proof exists, write "No proof yet" and use a how-it-works block.
- Be honest with visitors about availability. Use a waitlist, an early-access request, or a clear "coming soon" line. Never a checkout, a "buy now" button, or a payment form for a product that does not exist. No fake countdowns or "only 3 spots left" unless true.
- If you test a price, show it and say next to it that the product is not available yet.
- Label each claim in the copy notes (evidence: <repo path or source>) or (assumption: <test>).
- The founder sets thresholds before traffic starts. Mark your numbers "proposed".
- You are not a lawyer. Collecting emails needs a privacy notice and, in many countries, consent. Tell the founder to confirm with a lawyer for the countries listed.

Test context (founder-provided):
- Product:
- Artifact date (YYYY-MM-DD):
- Positioning statement:
- Target segment (one ICP slice):
- Availability today and earliest access date:
- Visitor action:
- Traffic source:
- Budget cap and cost per visitor:
- Publishable proof:
- Page builder and analytics:
- Visitor countries:

Steps:
1) Extract from the repo: the top three pains with intensity, the named alternative, and five customer phrases from transcripts. Cite each.
2) Write the copy:
   - Headline, 12 words or fewer. It names the outcome for this segment.
   - Subhead, 25 words or fewer. It says who it is for, what it does, and how it differs from the named alternative.
   - Three benefits, 20 words each. Each maps to one pain in value-proposition.md. Format: pain -> outcome.
   - Proof. Real items only, each with its source.
   - Call to action. A verb plus what happens next, for example "Join the waitlist". Add an availability line under the button with the earliest access date or "date not set".
   - FAQ, 5 to 7 questions. Include: is it available now, what it will cost, who it is for and not for, what happens to my email, how it differs from the named alternative.
   - One alternative headline that tests a different pain. Use it only if traffic allows the full sample for each version.
3) Honesty check. Table: Promise on the page | True today? (yes / no / planned by date) | Fix.
4) Write the test card:
   - Hypothesis: "If we show [message] to [ICP slice] from [traffic source], at least [X]% of unique visitors will [action] by [YYYY-MM-DD]."
   - Audience and traffic source, with the daily volume expected
   - Primary metric: unique visitors who complete the action / unique visitors, bots and team traffic removed
   - Pass threshold and fail threshold. Derive them from the business where you can. With paid traffic: lowest workable rate = cost per visitor / highest affordable cost per signup. Show the arithmetic.
   - Sample size: minimum unique visitors before reading the result. Show the margin of error as 2 x sqrt(p x (1 - p) / n). Example: at 200 visitors and a 10% rate the range is about 6% to 14%.
   - Duration: start and end dates, at least 7 days to cover weekday patterns, with a hard stop
   - Secondary metrics: share of signups that match the ICP (from one qualifying question on the form), reply rate to a follow-up email asking for a 20-minute call
   - Guardrails: spend cap, no page edits during the run, ICP match share above a founder-set floor, unsubscribes and complaints
   - Decision rule: at or above pass = keep the message and move to the next assumption. At or below fail = change the segment or the promise. In between = inconclusive: change one element and run once more.
5) List the events to instrument: page view, call-to-action click, form submit, qualifying answer.
6) Write the row for the Hypothesis Backlog in experiments.md: Hypothesis, Riskiest Assumption, Experiment Type "Landing page", Success Criterion, Status "Planned".

Output format (Markdown), in this exact order:
1. Title: <Product> landing page smoke test, YYYY-MM-DD
2. Source material (pains, alternative, customer phrases)
3. Landing page copy
4. Honesty check
5. Test card
6. Events to instrument
7. Hypothesis Backlog row
8. Open questions
9. Repo paths referenced
```

## Workflow (runbook)

1. Confirm the inputs. If `.productmap/00_company/product/value-proposition.md` has no positioning statement, fill it first.
2. Read the repo, transcripts first. Reuse the phrases customers used to describe the pain, word for word where you can.
3. Run the prompt. Review the honesty check line by line with the founder before any design work.
4. Set thresholds:
   - The founder confirms the pass number, the fail number, the minimum sample, and the end date.
   - Write them into `.productmap/02_discovery/experiments/experiments.md` before the page goes live. A threshold set after the data arrives proves nothing.
5. Build the page. Add the privacy notice and consent wording, checked against `.productmap/05_operations/legal/privacy-compliance.md`. Confirm with a lawyer for the visitor countries.
6. Instrument the four events and test them with your own visit. Exclude team traffic.
7. Run to the planned sample or the hard stop, whichever comes first. Don't edit the page mid-run and don't stop early on a good day.
8. Email every signup within 48 hours and ask for a 20-minute call. Replies and booked calls are stronger evidence than the signup.
9. Close the test:
   - Save the copy as `.productmap/00_company/product/landing-page-copy-YYYY-MM-DD.md`.
   - Add a row to `Experiment Log` with the setup, sample, result against the threshold, and the decision.
   - Tell the waitlist what happens next, and when. If you drop the idea, say so and delete the list.

## Quality checklist

- The headline names an outcome for one segment in 12 words or fewer.
- Each of the three benefits maps to a pain recorded in `.productmap/00_company/product/value-proposition.md`.
- The subhead names the alternative, and the FAQ answers "is it available now" truthfully.
- The page has no checkout, no payment form, and no invented proof, scarcity, or urgency.
- The honesty check has a row for every promise, and every "no" has a fix.
- The hypothesis states message, segment, source, a number, and a date in `YYYY-MM-DD`.
- Pass and fail thresholds are numbers, show their arithmetic or are marked as assumptions, and were set before launch.
- Sample size, margin of error, duration, and a hard stop are written down.
- Guardrails include a spend cap and an ICP match floor.
- The test card is logged in `.productmap/02_discovery/experiments/experiments.md`.
- `Repo paths referenced` lists every file read, starting with `.productmap/INDEX.md`.

## Related on Product Map

- Agent: **[Build unique value proposition](https://app.productmap.io/agents/value-proposition-positioning)** — nail your value proposition and positioning.

More AI PM agents from Product Map: https://www.productmap.io/
