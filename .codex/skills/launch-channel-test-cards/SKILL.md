---
name: launch-channel-test-cards
description: Produce a first launch plan with a launch tier, a before and after launch checklist, a three-channel shortlist, and one channel test card per channel with a kill, iterate, or scale rule.
---

# Launch channel test cards — Skill

## Name

`launch-channel-test-cards` — Plan a first launch as three channel tests with numbers set in advance, sized to what a small team can run.

## When to use

- The MVP works for a few users and you're planning the first public or semi-public launch.
- Your channel plan is a list of ten ideas with no order, owner, or number attached.
- You can't decide how loud the launch should be.
- A previous launch brought signups from the wrong people and you want tighter tests.
- You have four to six weeks, one or two people, and a small budget.
- Use a sibling skill instead when there's no product yet and you're testing demand (`.codex/skills/landing-page-smoke-test/SKILL.md`), or the launch is over and you need the readout (`.gemini/skills/launch-retro-synthesis/SKILL.md`).

## Inputs (ask user for these)

- Product name:
- Artifact date (YYYY-MM-DD) (use today's date unless the founder gives another):
- Beachhead segment (one narrow group) and where its members gather:
- Positioning statement (or the path to it):
- Product state (private beta / public beta / paid) and what a new user can do on day one:
- Target launch date (`YYYY-MM-DD`) and any fixed event:
- Who runs the launch and hours per week each:
- Budget for the launch period:
- Channels tried so far and what happened (numbers if any):
- Assets you own (waitlist size, email list, audience, community memberships, partners):
- The one launch result that matters most (signups, activated users, calls booked, paid customers):

## Outputs

- First launch plan (Markdown) containing:
  - Launch tier (T1, T2, or T3) with the readiness check behind it
  - Channel longlist scored, and a three-channel shortlist
  - One test card per shortlisted channel
  - Before-launch checklist with owners and dates, and a go or no-go date
  - After-launch plan: primary metric, supporting metrics, guardrails, review dates
  - Launch goals table
- Where to store it:
  - `.productmap/02_discovery/marketing/gtm-launch.md` (existing template; fill `Channel Shortlist`, `Launch Checklist`, `Launch Goals`, and add the test cards below `Channel Shortlist`)
  - One row per channel test: `Hypothesis Backlog` in `.productmap/02_discovery/experiments/experiments.md`

## Repo knowledge to pull

- Start here: `.productmap/INDEX.md`
- Target file: `.productmap/02_discovery/marketing/gtm-launch.md`
- Segment and where to reach it: `.productmap/01_strategy/segmentation/segmentation.md`, `.productmap/01_strategy/segmentation/icp-b2b.md`, `.productmap/01_strategy/segmentation/icp-b2c.md`
- Message and offer: `.productmap/00_company/product/value-proposition.md`, `.productmap/02_discovery/marketing/marketing.md`
- Outreach templates and pipeline counts: `.productmap/02_discovery/growth-sales/founder-led-sales.md`
- Earlier channel results: `.productmap/02_discovery/experiments/experiments.md`
- Launch metric definitions and events: `.productmap/03_analysis/kpis-metrics/metrics-tracking.md`, `.productmap/03_analysis/analytics/analytics.md`
- Readiness evidence: `.productmap/01_strategy/product-market-fit/pmf-signals.md`
- Budget: `.productmap/05_operations/finance/runway-burn.md`

## Detailed prompt (copy/paste)

```
You are a go-to-market advisor for a founder running a first launch with a small team. Set the launch tier, shortlist three channels, write a test card for each, and plan the weeks before and after launch day. Read the repo first and cite every path you used.

Repo-first context to consult:
- Start at: .productmap/INDEX.md
- Read and keep the headings of: .productmap/02_discovery/marketing/gtm-launch.md
- Read: segmentation.md, icp-b2b.md or icp-b2c.md, value-proposition.md, marketing.md, founder-led-sales.md, experiments.md, metrics-tracking.md, analytics.md, pmf-signals.md, runway-burn.md
- Read any path the founder lists.

Constraints:
- Write every date as YYYY-MM-DD.
- Invent nothing. Do not quote channel benchmarks, audience sizes, or costs without a source. Baselines come from the founder's data, or are written as "unknown, first run sets the baseline".
- Label each claim (evidence: <repo path or source>) or (assumption: <test>).
- Clicks, views, and follower counts never stand alone. Tie each to signups from the segment, activation, calls booked, or revenue.
- Use positioning and pricing as inputs. If either is missing, state the assumption and note the gap.
- Size the plan to the hours and budget given. Run at most two channel tests at once, as gtm-launch.md says. The third waits in the queue.

Launch context (founder-provided):
- Product:
- Artifact date (YYYY-MM-DD):
- Beachhead segment and where it gathers:
- Positioning statement:
- Product state and day-one experience:
- Target launch date and fixed events:
- Team and hours per week:
- Budget:
- Channels tried and results:
- Assets owned:
- Launch result that matters most:

Steps:
1) Readiness check. Answer each with yes, no, or unknown, and cite the evidence:
   a. The problem is validated with the beachhead segment (interviews or commitments on file)
   b. Someone outside the team completed the core flow and got the value
   c. At least one channel has a measured result
   d. Analytics capture the primary launch metric
   e. The team can answer every new user within 24 hours during launch week
2) Launch tier. Apply this rule and say why:
   - T1, full public launch on every owned and earned channel, with two or more weeks of founder time blocked: needs a to e all yes.
   - T2, targeted launch to the beachhead through one or two channels: needs a, b, and d yes.
   - T3, quiet launch to the waitlist and existing contacts: everything else.
   List what would move the launch up one tier.
3) Channel longlist. Brainstorm 8 to 12 channels that reach this segment. Score each 1 to 5 on: segment fit, reach inside the beachhead, cost in time and money (5 = cheap), speed to a readable result (5 = under two weeks), confidence from evidence. Total out of 25. Columns: Channel | Fit | Reach | Cost | Speed | Confidence | Total | Evidence.
4) Shortlist the top three. Mark two as "run now" and one as "queued". Keep at least one channel where the founder talks to prospects directly.
5) Write one test card per shortlisted channel with these rows:
   - Hypothesis: "If we [action] for [ICP slice], [metric] goes from [baseline] to [target] by [YYYY-MM-DD]."
   - ICP slice
   - Offer (what the person gets for responding)
   - Message (the first two lines, in the segment's words)
   - Sample size (people contacted, visitors, or posts)
   - Duration (start and end dates, with a hard stop)
   - Primary metric and how it is counted
   - Guardrails (spend cap, hours cap, share of responders who match the ICP, complaints or unsubscribes)
   - Kill / iterate / scale rule: at or above target = scale. Between floor and target = change one variable and run once more. Below floor, or a guardrail broken = kill. Two iterations without reaching target = kill.
   - Owner and budget
   Mark targets and floors "proposed, founder to confirm before the test starts".
6) Before-launch checklist. Columns: Item | Done means | Owner | Due | Status. Start from the Pre-launch list in gtm-launch.md and add: analytics events tested, support replies drafted, rollback plan, claims on the page checked for accuracy, go or no-go date.
7) After-launch plan: one primary launch metric with a target, 2 to 4 supporting metrics split by channel, guardrails with thresholds, the launch-day list, the first-two-weeks list, and review dates at day 14 and day 30.
8) Launch goals table: Goal | Target | Actual (leave Actual blank).

Output format (Markdown), in this exact order:
1. Title: <Product> first launch plan, YYYY-MM-DD
2. Beachhead segment and positioning (as used)
3. Readiness check and launch tier
4. Channel longlist (scored)
5. Channel shortlist
6. Channel test cards
7. Before launch
8. After launch
9. Launch goals
10. Assumptions and open questions
11. Repo paths referenced
```

## Workflow (runbook)

1. Confirm the inputs. If `Beachhead Segment` or `Positioning Statement` in `.productmap/02_discovery/marketing/gtm-launch.md` is blank, fill those two first.
2. Read the repo, starting at `.productmap/INDEX.md`. Pull any channel result already logged in `.productmap/02_discovery/experiments/experiments.md`. A measured result outranks a score.
3. Run the readiness check with the founder. An "unknown" counts as "no" for the tier rule.
4. Run the prompt. Check the plan against the hours available. If three cards need more hours than the team has, cut sample sizes before cutting the hard stops.
5. Confirm targets and floors. The founder sets them before any test starts, and writes the date they were set.
6. Write back to `.productmap/02_discovery/marketing/gtm-launch.md`:
   - Fill `Channel Shortlist` with the three channels, their hypotheses, cost, and status (`Testing` for two, `Planned` for the queued one).
   - Add the test cards below `Channel Shortlist`.
   - Update `Launch Checklist` with owners and dates, and fill the `Target` column of `Launch Goals`.
7. Add one row per test to `Hypothesis Backlog` in `.productmap/02_discovery/experiments/experiments.md`.
8. Hold the go or no-go check on its date. If a T1 or T2 condition turned to "no", drop a tier instead of moving the date.
9. Read each card on its end date and apply the rule as written. Log the result in `Experiment Log`, then start the queued channel when a slot frees up.
10. At day 30, hand the results to `.gemini/skills/launch-retro-synthesis/SKILL.md`.

## Quality checklist

- The launch tier follows the rule, and each readiness answer cites evidence or is marked unknown.
- The longlist has 8 to 12 channels scored on the same five scales, and totals add up.
- Exactly three channels are shortlisted, with two running and one queued.
- Every card has all ten rows filled, and no row says "TBD" without an open question.
- Each hypothesis has a baseline (or "unknown, first run sets the baseline"), a target, and a date in `YYYY-MM-DD`.
- Each primary metric ties to segment signups, activation, calls, or revenue.
- Each card has a spend cap, an hours cap, and an ICP match guardrail.
- The kill, iterate, or scale rule uses numbers and caps iterations at two.
- The before-launch checklist has an owner and a due date per item, plus a go or no-go date.
- No benchmark or audience size appears without a source.
- `Repo paths referenced` lists every file read, starting with `.productmap/INDEX.md`.

## Related on Product Map

- Agent: **[Build go-to-market strategy](https://app.productmap.io/agents/go-to-market-strategy)** — choose your GTM motion, channels, and launch plan.
- Workflow: **[GTM strategy to growth loops](https://app.productmap.io/workflows/gtm-strategy-to-growth-loops)** — prepare the go-to-market strategy, generate digital marketing ideas, then plan growth loops.

More AI PM agents from Product Map: https://www.productmap.io/
