---
name: growth-experiment-sprint
description: Plan a four-week growth sprint with one bottleneck metric and goal, 10 to 15 ideas scored with ICE, three experiment cards with decision rules, a weekly cadence, and a learnings log.
---

# Growth experiment sprint — Skill

## Name

`growth-experiment-sprint` — Pick the one stage of the funnel that holds growth back and run three experiments against it in four weeks.

## When to use

- You have real users and at least rough funnel numbers, and growth work is a pile of unrelated ideas.
- Signups arrive but few users reach the moment where the product pays off.
- You want to start paid acquisition and haven't checked whether users stay.
- The last experiments ended without a clear result because nobody wrote a decision rule.
- You can give growth 5 to 15 hours a week for a month and want it spent on one metric.
- Use a sibling skill instead when you need the growth model, engine, and loops first (`.claude/skills/growth-loops-engine/SKILL.md`), or you're still testing first channels (`.codex/skills/launch-channel-test-cards/SKILL.md`).

## Inputs (ask user for these)

- Product name:
- Artifact date (YYYY-MM-DD) (use today's date unless the founder gives another):
- Sprint start date (`YYYY-MM-DD`):
- Target segment:
- Funnel numbers for the last 4 to 8 weeks (visitors, signups, activated users, retained users, paying customers, referrals) and their source:
- Your activation event (the first moment a user gets the value):
- Retention by weekly cohort, if you have it:
- North star metric and current value:
- Ideas already on the list:
- Experiments run before and their results:
- People, hours per week, and budget for the sprint:
- Changes you won't make (pricing, brand, anything off limits):

## Outputs

- Growth sprint plan (Markdown) containing:
  - Funnel table and the chosen bottleneck, with evidence
  - Retention gate: whether adding acquisition is allowed this sprint
  - Sprint goal as a rate with a deadline
  - Idea backlog: 10 to 15 ideas scored with ICE
  - Three experiment cards
  - Week-by-week cadence and the weekly review agenda
  - Learnings log (empty rows, filled as experiments close)
- Where to store it:
  - Sprint plan: `.productmap/02_discovery/growth-sales/growth-sales.md`, as a new section `Growth sprint YYYY-MM-DD` below `Early-Stage Focus`
  - Experiment cards and results: `Hypothesis Backlog` and `Experiment Log` in `.productmap/02_discovery/experiments/experiments.md`
  - Metric exports: `.productmap/06_data/analytics/`

## Repo knowledge to pull

- Start here: `.productmap/INDEX.md`
- Target files: `.productmap/02_discovery/growth-sales/growth-sales.md`, `.productmap/02_discovery/experiments/experiments.md`
- North star, funnel events, and definitions: `.productmap/03_analysis/kpis-metrics/metrics-tracking.md`, `.productmap/03_analysis/kpis-metrics/kpis-metrics.md`
- Cohorts and instrumentation: `.productmap/03_analysis/analytics/analytics.md`, `.productmap/06_data/analytics/`
- Retention and must-have signals: `.productmap/01_strategy/product-market-fit/pmf-signals.md`
- Whether paid acquisition can pay back: `.productmap/03_analysis/unit-economics/unit-economics.md`
- Why users leave or stay: `.productmap/06_data/feedback/`, `.productmap/06_data/interviews/`
- Segment: `.productmap/01_strategy/segmentation/icp-b2b.md`, `.productmap/01_strategy/segmentation/icp-b2c.md`

## Detailed prompt (copy/paste)

```
You are a growth lead for an early-stage startup. Find the one funnel stage that limits growth, set a four-week goal for it, score ideas, and write three experiment cards with decision rules. Read the repo first and cite every path you used.

Repo-first context to consult:
- Start at: .productmap/INDEX.md
- Read: growth-sales.md, experiments.md, metrics-tracking.md, kpis-metrics.md, analytics.md, pmf-signals.md, unit-economics.md, icp-b2b.md or icp-b2c.md
- Read exports in .productmap/06_data/analytics/ and feedback in .productmap/06_data/feedback/.

Constraints:
- Write every date as YYYY-MM-DD.
- Invent nothing. Baselines come from the founder's data. A stage with no data is "not instrumented", and instrumenting it becomes the first task.
- Do not quote outside benchmarks without a source.
- Label each claim (evidence: <repo path or source>) or (assumption: <test>).
- Use rates and cohorts. A cumulative total is not a metric.
- Every idea names the stage and the metric it moves. Drop ideas that target a different stage from the bottleneck.
- No dark patterns: no hidden cancellation, fake urgency, forced continuity, or misleading defaults. Remove any idea that needs one.
- Use pricing and positioning as inputs. Do not redesign them here.

Sprint context (founder-provided):
- Product:
- Artifact date (YYYY-MM-DD):
- Sprint start date:
- Target segment:
- Funnel numbers and source:
- Activation event:
- Retention by cohort:
- North star metric and value:
- Ideas already listed:
- Past experiments and results:
- People, hours per week, budget:
- Off limits:

Steps:
1) Funnel table, using the stages in metrics-tracking.md. Columns: Stage (acquisition, activation, retention, referral, revenue) | Metric | Current rate | Sample size | Period | Source | Confidence (data / estimate / not instrumented).
2) Retention gate. State one of:
   - Open: weekly cohorts flatten above zero, or pmf-signals.md shows a strong signal. Acquisition experiments are allowed.
   - Closed: retention decays toward zero, or is unknown. This sprint targets activation or retention, and no money goes to acquisition.
3) Bottleneck. Choose one stage with this order of preference: retention if the gate is closed for decay, activation if fewer signups reach the activation event than the founder's target, otherwise the stage with the largest gap between current rate and target. Give the evidence in one sentence and say what result would change the choice.
4) Sprint goal: "Move [metric] from [baseline] to [target] by [YYYY-MM-DD]." The end date is 28 days after the start. Mark the target "proposed, founder to confirm".
5) Idea backlog, 10 to 15 ideas aimed at the bottleneck. Score each 1 to 10:
   - Impact: expected move in the bottleneck metric if it works
   - Confidence: 1 to 3 opinion, 4 to 6 customer quotes or a comparable case, 7 to 8 your own data, 9 to 10 your own earlier experiment
   - Ease: 10 = under a day with no code, 5 = about a week, 1 = more than the sprint
   - ICE = (Impact + Confidence + Ease) / 3, one decimal
   Columns: # | Idea | Stage | Metric it moves | Evidence | Impact | Confidence | Ease | ICE. Sort by ICE.
6) Pick the top three that fit the hours available and do not overlap on the same users at the same time. Say why any higher-scored idea was skipped.
7) Write one experiment card per pick with these rows: Hypothesis ("If we [change] for [segment], [metric] goes from [baseline] to [target] within [N] days") | Change (exactly what ships) | Metric and how it is counted | Baseline | Target | Sample (users or cohorts needed, and how long that takes at current volume) | Duration (start and end dates) | Owner | Instrumentation needed | Decision rule.
   Decision rule: at or above target = keep and roll out. Below baseline, or a guardrail broken = revert. In between = one more run with one variable changed, then decide.
   If volume is too low for a split test, use a before and after comparison of cohorts, say so on the card, and call the result directional.
8) Cadence. Week 1: instrument, confirm baselines, ship experiment 1. Week 2: ship experiment 2, read early data. Week 3: ship experiment 3, close experiment 1. Week 4: close the rest, write learnings, choose the next bottleneck. Add a 30-minute weekly review agenda: results against rules, one learning per closed test, is the bottleneck still the bottleneck, next actions with owners.
9) Learnings log with empty rows. Columns: Date | Experiment | Result vs target | What we learned | Decision | Next step.

Output format (Markdown), in this exact order:
1. Title: <Product> growth sprint, YYYY-MM-DD to YYYY-MM-DD
2. Funnel table
3. Retention gate
4. Bottleneck and sprint goal
5. Idea backlog (ICE)
6. Experiment cards
7. Weekly cadence
8. Learnings log
9. Assumptions and open questions
10. Repo paths referenced
```

## Workflow (runbook)

1. Collect the funnel numbers. If the founder has none, the sprint's first week is instrumentation. Use the events listed in `.productmap/03_analysis/kpis-metrics/metrics-tracking.md`.
2. Read the repo, starting at `.productmap/INDEX.md`. Check `.productmap/01_strategy/product-market-fit/pmf-signals.md` for the retention curve before anything else.
3. Set the retention gate with the founder. When the gate is closed, remove acquisition ideas from the backlog and keep them for a later sprint.
4. Run the prompt. Score ICE with the people who will do the work, since they know the effort.
5. Check capacity. Three experiments must fit the hours given. If they don't, run two.
6. Confirm each target and decision rule before the experiment ships. Record the date.
7. Write back to the repo:
   - Add the section `Growth sprint YYYY-MM-DD` to `.productmap/02_discovery/growth-sales/growth-sales.md` below `Early-Stage Focus`, with the goal, backlog, cadence, and learnings log.
   - Add each card to `Hypothesis Backlog` in `.productmap/02_discovery/experiments/experiments.md` with the target as `Success Criterion`.
8. Hold the weekly review on a fixed day. Apply decision rules as written. A result that misses the target is still a learning, so log it.
9. Close the sprint on day 28. Fill the learnings log, add rows to `Experiment Log`, update the funnel table, and pick the next bottleneck.

## Quality checklist

- The funnel table has a rate, a sample size, a period, and a source for each stage, or says "not instrumented".
- The retention gate is stated, and a closed gate means no acquisition spend in the sprint.
- One bottleneck is chosen, with evidence and the result that would change the choice.
- The sprint goal is a rate with a baseline, a target, and an end date in `YYYY-MM-DD`.
- The backlog holds 10 to 15 ideas, all aimed at the bottleneck, each scored on the same three scales.
- ICE arithmetic is right, and any skipped higher-scored idea has a reason.
- Each of the three cards has all ten rows, a counted metric, and a numeric decision rule.
- Low-volume tests are marked directional.
- No idea relies on a dark pattern, and no benchmark appears without a source.
- The cadence names a weekly review day, and the learnings log is in place.
- `Repo paths referenced` lists every file read, starting with `.productmap/INDEX.md`.

## Related on Product Map

- Agent: **[Build product growth strategy](https://app.productmap.io/agents/growth-marketing)** — pick your growth engine, design loops and sprints.
- Workflow: **[GTM strategy to growth loops](https://app.productmap.io/workflows/gtm-strategy-to-growth-loops)** — prepare the go-to-market strategy, generate digital marketing ideas, then plan growth loops.

More AI PM agents from Product Map: https://www.productmap.io/
