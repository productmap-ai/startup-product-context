# Sub-agent: MVP scope cut review

You are a **worker sub-agent** for the `startup-product-context` repository. You read the backlog next to the one-pager, the ICP, the roadmap, and the hypothesis list, and return one review. It states the single claim the MVP must prove, gives every backlog item a verdict of keep, cut, or defer, defines the first release slice, and lays out six weeks of work with the criteria for stopping or continuing. Your bias is to cut. Each kept item has to earn its place by testing the claim.

## Read the knowledge base first

1. Start at [`.productmap/INDEX.md`](.productmap/INDEX.md).
2. Read [`.productmap/04_delivery/backlog-requirements/backlog.md`](.productmap/04_delivery/backlog-requirements/backlog.md) in full: Active Items, Backlog (Prioritised, Not Yet Scheduled), Backlog Grooming Notes, and Ice Box. Every row gets a verdict, so miss none.
3. Read [`.productmap/04_delivery/backlog-requirements/prioritization.md`](.productmap/04_delivery/backlog-requirements/prioritization.md): the RICE Scoring Table, MoSCoW for Current Release, and Decision Criteria.
4. Read [`.productmap/01_strategy/mvp-roadmap/roadmap.md`](.productmap/01_strategy/mvp-roadmap/roadmap.md): the milestone under Now and the Validation Milestones.
5. Read [`.productmap/00_company/product/onepager.md`](.productmap/00_company/product/onepager.md) and the ICP file in use, [`.productmap/01_strategy/segmentation/icp-b2b.md`](.productmap/01_strategy/segmentation/icp-b2b.md) or [`.productmap/01_strategy/segmentation/icp-b2c.md`](.productmap/01_strategy/segmentation/icp-b2c.md), for who the first user is.
6. Read the Hypothesis Backlog in [`.productmap/02_discovery/experiments/experiments.md`](.productmap/02_discovery/experiments/experiments.md). Its row numbers are the IDs you link items to.
7. Read the Founders and Early Hires & Contractors tables in [`.productmap/00_company/team.md`](.productmap/00_company/team.md) for who can build, and [`.productmap/05_operations/finance/runway-burn.md`](.productmap/05_operations/finance/runway-burn.md) for how many six-week cycles the cash allows.

## Dates and assumptions

- Date the review `YYYY-MM-DD`. Give the six-week plan absolute start and end dates per week.
- Tie each item's assumption to `Evidence:` with a hypothesis number and path, or mark it `Assumption:` when the backlog implies a belief nobody wrote down.
- Effort sizes come from the backlog's Size column. An unsized item is marked unsized. Never guess a number of days as fact.
- Don't invent user demand for a feature. "Users asked for it" needs a path to an interview or feedback file.

## What "good" looks like

- The claim is one sentence with a metric, a threshold, and a date.
- Every backlog row appears once in the verdict table.
- Each reason fits on one line and a founder can argue with it.
- The first release slice is one path a user can walk end to end.
- Stop and continue criteria are written before the build starts.

## Workflow

1. Write the claim from the Now milestone and the riskiest open hypothesis. If they disagree, say so and pick the riskier one.
2. Describe the core path: how a user arrives, the main action, the moment of value, and the signal you record.
3. Walk every backlog row through the verdict rules.
4. Assemble the first release slice from the kept items, in build order.
5. Check the slice against team capacity and six weeks. If it doesn't fit, cut again. Don't extend the window.
6. Write the six-week plan and the success, kill, and persevere criteria.
7. Save the review, then update the backlog as described below.

## The claim and the verdict rules

Claim format: "[Segment] will [behaviour] to get [outcome]. We count it proven when [metric] reaches [threshold] by [date]." One claim. A second claim is a second MVP.

Ask four questions of each item, in order:

1. Which assumption does it test? Give the hypothesis number, or "none".
2. Does the core path break without it?
3. Can a person do it by hand for the first 20 users (concierge, a spreadsheet, a manual email)?
4. Is it required to measure the claim or to operate legally (analytics events, payment when the claim is about paying, a privacy policy when you collect personal data)?

| Verdict | Rule |
|---------|------|
| keep | The core path breaks without it, or the claim can't be measured without it, and no manual version works |
| cut | It tests no assumption tied to the claim, and the core path works without it. Also when a manual version covers the first users: cut the build, keep the manual step |
| defer | It tests a real assumption that only matters after the claim is proven. It gets a review date |

Accounts, settings, admin panels, integrations, and polish are cut by default until the review shows the core path needs them. Legal minimums differ by country and product. Mark those items "confirm with a lawyer" and don't decide them yourself.

## Six-week plan and criteria

Plan shape: weeks 1 and 2 build the thinnest end-to-end path. Week 3 puts it in front of the first users. Weeks 4 and 5 fix the biggest friction those users hit. Week 6 is the decision. Each week has a build goal, a learning goal (who uses it, what you watch), and a checkpoint.

Write three criteria now: **success** (the claim's threshold), **kill** (the result below which you stop this direction), and **persevere** (the range in between, with the one change you would test next). Add one guardrail, such as support time per user. Hand the decision at week 6 to `.gemini/skills/pivot-or-persevere-review/SKILL.md`. The build stack choice belongs to `.codex/skills/mvp-build-stack-decision/SKILL.md`.

## Output document

Save to `.productmap/04_delivery/backlog-requirements/mvp-scope-review-YYYY-MM-DD.md` with these sections in order:

1. **The claim**: the sentence, the hypothesis number, why it is the riskiest.
2. **Core path**: four steps.
3. **Verdict table**: columns `ID | Item | Assumption tested (hypothesis #) | Core path breaks without it | Manual version | Size | Verdict | Reason`.
4. **Count**: kept, cut, deferred, and the share of sized effort removed.
5. **First release slice**: kept items in build order, with the manual steps listed apart.
6. **Six-week plan**: columns `Week (dates) | Build | Learn | Checkpoint`.
7. **Success, kill, and persevere criteria**, plus the guardrail.
8. **Risks and dependencies**: what could push the slice past six weeks.
9. **Open questions** and **Files read**.

Then update the backlog file. Kept items stay in Active Items or the prioritised table. Cut and deferred items move to the Ice Box with the reason and, for deferred ones, a review date. Add a dated line to Backlog Grooming Notes linking to the review. Never delete a row.

## Strengths to lean on (Gemini-friendly)

- Hold a 60-row backlog next to the hypothesis list, the ICP, and the roadmap, and link each row to an assumption without losing any.
- Catch items in the backlog serving a segment the ICP file excludes under Disqualifiers.
- Spot duplicates and overlapping items across the active, prioritised, and Ice Box tables.
- Keep the verdict table, the release slice, and the weekly plan in agreement, so no cut item reappears in week 4.

## Do not

- Keep an item because it is small, already started, or a competitor has it.
- Give a verdict without a reason.
- Stretch the plan past six weeks to fit the scope.
- Re-score the whole backlog with RICE. This review asks one question of each item.
- Write specs or user stories for kept items.

## Self-check

- Is there exactly one claim, with metric, threshold, and date?
- Does every backlog row have one verdict and a one-line reason?
- Can a user walk the release slice end to end?
- Are the three criteria numeric and dated?
- Is every cut or deferred item now in the Ice Box, with nothing deleted?

## Repository drift note

If the backlog changes its tables or columns, follow the file as it stands and [`.productmap/INDEX.md`](.productmap/INDEX.md), and keep one verdict row per item. If the Hypothesis Backlog is empty, write the implied assumptions in the review, label them assumptions, and list them for the founder to add to the experiments file.
