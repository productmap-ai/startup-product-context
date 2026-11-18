---
name: runway-burn-planning
description: Use this skill when the user is working out burn and runway, checking default alive or default dead, building cash scenarios, testing a hiring plan against cash, or setting triggers for cutting costs or starting a raise. Triggers — "how much runway do we have", "burn rate", "default alive", "when do we run out of money", "can we afford this hire", "cut costs", "burn multiple", "cash scenarios", "when should we start raising".
---

# Runway and burn planning — Claude skill

Use this skill to give a founder one honest number, months of cash left, and the decisions hanging on it: scenarios, hiring, cut triggers, and raise triggers agreed before they are needed. Read `.productmap/` first. The burn table and thresholds already exist there and this skill fills them.

This skill organises numbers and common practice. It is no substitute for accounting, tax, or legal advice. Confirm figures and obligations with an accountant, and talk to a lawyer when cash gets tight.

## When this skill applies

- A founder asks how long the money lasts.
- The runway figure is computed from one month's spend, from booked revenue, or from memory.
- A hire, a tool contract, or an ad budget is proposed and nobody has checked the cash effect.
- Revenue came in under plan for two months.
- The team needs to decide when to start a raise.
- Runway has dropped under nine months and no plan exists for a slower raise.
- An investor asked for burn, runway, and the path to break-even.

## When not to use this skill (hand off instead)

- **Building the 18 to 24 month model.** Use `.codex/skills/startup-financial-model/SKILL.md`. This skill reads the model's outputs.
- **Round size, instruments, and investors.** Use `.claude/skills/fundraising-strategy/SKILL.md`. The raise trigger here hands over to it.
- **Price and packaging as the lever on revenue.** Use `.claude/skills/monetization-pricing/SKILL.md`.
- **A monthly investor update.** Use `.gemini/skills/investor-update-memo/SKILL.md`.
- **A weekly review of metrics and priorities.** Use `.gemini/skills/founder-weekly-review/SKILL.md`.
- **Whether the business direction should change.** Use `.gemini/skills/pivot-or-persevere-review/SKILL.md`.
- **Founder pay and commitment as a founder topic.** Use `.claude/skills/cofounder-alignment/SKILL.md`.
- **Bookkeeping, tax filings, payroll setup.** An accountant's job.

## Repo knowledge to consult first

- `.productmap/INDEX.md` for the map of the tree.
- `.productmap/05_operations/finance/runway-burn.md`: Definitions, Monthly Burn Table, Default Alive or Default Dead?, Runway Alert Thresholds.
- `.productmap/05_operations/finance/finance.md`: Setup Checklist and Monthly Close Rhythm. Trust the burn table only as far as the close is done.
- `.productmap/05_operations/finance/financial-model.md`: Revenue Drivers, Cost Structure, 18–24 Month Projection, Scenarios, Key Assumptions Log.
- `.productmap/03_analysis/unit-economics/unit-economics.md` for margin and payback where known.
- `.productmap/00_company/fundraising/fundraising-strategy.md`: Current Round, Runway Math, Timeline & Process.
- `.productmap/00_company/team.md`: Early Hires & Contractors, for committed people costs.

Ask for the bank balance and the last three to six months of cash in and cash out if the table is empty. Never estimate a balance.

## Burn and runway definitions

Use cash, as it moved through the bank. Accounting profit and booked revenue answer other questions.

| Term | Definition | Notes |
|---|---|---|
| Gross burn | Total cash out in a month | Every payment, including annual bills in the month they are paid |
| Net burn | Cash out minus cash in | The figure shortening runway |
| Runway | Cash balance ÷ average net burn | Months remaining |
| Cash-out date | Today plus runway | Write it as an absolute date |
| Decision date | Cash-out date minus the time a raise or a wind-down needs | The date by which you must act |

Rules for an honest number:

- **Average the last three months** of net burn. One month hides annual bills and late invoices.
- **Count cash collected.** An invoice sent is not cash. Recurring revenue signed but unpaid is not cash.
- **Separate one-off items.** List them beside the table: an annual licence, a legal bill, a tax refund, a grant payment. Show runway with and without them.
- **Add committed future costs.** Signed offers, contractor terms, annual renewals, and tax due inside the period.
- **Exclude money you don't have.** Soft-circled investment and unsigned deals stay out.
- **Hold a floor.** Wind-down costs, final payroll, and taxes need cash too. Ask an accountant what the minimum is for your entity and country.
- **Date everything.** Balance as of a day, burn as of a month.

Show two figures side by side: runway on trailing burn, and runway on planned burn including commitments. The lower one drives decisions.

## Default alive or default dead

The question, from Paul Graham: with expenses held constant and revenue growing at its current rate, does the company reach profitability before the cash runs out?

How to test it:

1. Take current monthly revenue collected, monthly expenses, and cash.
2. Take the average month-over-month revenue growth of the last three to six months. With fewer than three months of revenue, treat growth as unknown and answer "default dead until shown otherwise".
3. Project month by month: revenue grows at that rate, expenses stay flat, cash falls by the gap.
4. If revenue meets expenses before cash reaches the floor, default alive. Record the break-even month. Otherwise default dead. Record the cash-out month.

Reading the result:

- **Default alive.** You raise by choice. Check how sensitive the answer is: rerun with growth halved.
- **Default dead with a credible plan.** Name the plan in the template's field: raise, cut, or accelerate revenue. Give it a date.
- **Default dead and assuming a raise.** The raise is a hope until money is wired. Prepare the cut scenario now.
- A company with a few months of cash, slow growth, and no room to cut is in the hardest spot. Say so plainly and move the conversation to the decision date.

## Scenarios for low, base, and high cases

Three cases, same structure, different inputs. They map to Pessimistic, Base, and Optimistic in the Scenarios table of `financial-model.md`.

| Input | Low | Base | High |
|---|---|---|---|
| Revenue growth | Half of the recent rate, or flat | Recent rate | The plan's target rate |
| Churn | Double the recent rate | Recent rate | Slightly better |
| Collections | Customers pay 30 days late | As today | As today |
| Hiring | As planned | As planned | As planned, or earlier |
| New funding | None | None until signed | None until signed |
| One-off costs | All expected ones land | Expected ones land | Expected ones land |

Rules:

- Plan spending on the base case. Check survival on the low case.
- Costs are easier to predict than revenue. Hold them equal across cases unless a decision changes them.
- No case includes money from an unsigned round.
- For each case record runway in months, the cash-out date, and the break-even month if one exists.
- If low-case runway is under nine months, the raise or cut decision is already due.

## Burn multiple and hiring impact

**Burn multiple** = net burn ÷ net new annual recurring revenue, over the same period. It shows how much cash each new unit of recurring revenue costs.

| Burn multiple | Common reading |
|---|---|
| Under 1 | Outstanding efficiency |
| 1 to 1.5 | Strong |
| 1.5 to 2 | Good |
| 2 to 3 | Questionable. Find the cause |
| Over 3 | Poor. Growth is being bought at a loss |

These bands come from investor commentary on software companies with recurring revenue. They mean little before revenue exists or when revenue is tiny, since small denominators swing the ratio. Before revenue, track cash spent per validated milestone instead, such as cost per paying pilot.

**Hiring impact.** People are usually the largest cost and the slowest to reverse.

- Use fully loaded cost: salary plus employer taxes, benefits, equipment, and tools. A planning uplift of 20 to 40% over salary is common, and it varies by country. Ask an accountant for your figure.
- New runway = cash ÷ (current net burn + loaded monthly cost of the hire).
- Add ramp time. A new hire seldom contributes fully in the first two to three months.
- Tie each hire to a milestone it makes reachable. A hire with no milestone waits.
- Show runway before and after every proposed hire, on base and low cases.
- Prefer reversible commitments while runway is short: contractors, part-time, fixed-term.
- Notice periods and severance rules differ by country. Check them before the offer goes out, since they set how fast a cut takes effect.

## Triggers and review cadence

Agree the triggers while calm. Decisions made at three months of runway are worse than those planned at twelve.

**Raise triggers.** The Runway Alert Thresholds table in `runway-burn.md` sets the base: business as usual at 12 months or more, start raising at 9 to 12, raise actively and prepare cuts at 6, execute a bridge, cuts, or a wind-down decision at 3. A raise commonly takes three to six months, so starting under nine months of runway leaves little margin.

**Cut triggers.** Write each as a condition and an action already decided.

| Condition | Pre-agreed action |
|---|---|
| Net burn over plan by 15% or more for two months running | Review every line. Freeze new commitments |
| Revenue under the low case for two months running | Switch planning to the low case. Pause hiring |
| Low-case runway under nine months | Start the raise. Draft the cut plan with amounts |
| Runway under six months with no signed term sheet | Execute the first cuts |
| Runway under three months | Decide: bridge from existing investors, deep cuts, sale, or orderly wind-down |

The percentages are starting points. Set your own and write them down.

**Order of cuts,** least damaging first: unused tools and subscriptions, discretionary spend and travel, paid acquisition lacking a proven return, contractor hours, the hiring plan, founder pay, team size. Cut once and deeply enough. Repeated small cuts cost trust and time.

When cash becomes tight, speak to a lawyer and an accountant early. Directors' duties shift near insolvency in many jurisdictions, and payroll and tax obligations rank ahead of other spending.

**Monthly review,** right after the close described in `finance.md`:

1. Update the burn table with real cash in, cash out, and balance.
2. Recompute trailing and planned runway and the cash-out date.
3. Compare with the model. Explain each large variance in one line.
4. Rerun the default alive test and the three cases.
5. Check every trigger. If one fired, do the agreed action.
6. Record the decision and the date of the next review.

## Workflow

1. **Read the repo.** Burn table, model, round plan, people commitments.
2. **Get the facts.** Bank balance with its date. Cash in and out for the last three to six months. Committed future costs.
3. **Fill the Monthly Burn Table.** Note one-off items beside it.
4. **Compute runway** on trailing and planned burn. Give the cash-out date and the decision date.
5. **Run the default alive test.** Fill the template's fields.
6. **Build the three cases.** Record runway and cash-out date for each.
7. **Compute the burn multiple** if recurring revenue exists. Otherwise state why it is skipped.
8. **Test proposed hires and large commitments** against base and low cases.
9. **Set triggers.** Confirm or adjust the alert thresholds. Write the cut conditions and actions.
10. **Write into `runway-burn.md`** and set the next review date. If a raise trigger fired, hand off to the fundraising strategy skill.

## Pitfalls

- **Runway from one month.** The cheapest month flatters. The month with the annual bill frightens.
- **Counting booked revenue as cash.**
- **Counting a round before the wire.**
- **Forgetting annual and irregular costs:** insurance, licences, tax, audit, legal.
- **Only one scenario.** The plan and the hope become the same document.
- **Hiring on the high case.**
- **Starting the raise at six months.** By the time meetings happen, the weak position shows.
- **Triggers never written.** Each month the line moves.
- **Many small cuts.** The team waits for the next one.
- **A burn multiple on tiny revenue.** The ratio is noise.
- **Founders unpaid with no end date.** Personal runway ends before company runway.
- **Skipping the monthly close.** The table drifts from the bank.

## Questions to ask the user

1. What is the bank balance, and on which date?
2. What were cash in and cash out for each of the last six months?
3. Which payments were one-off, and which irregular ones are coming?
4. What costs are already committed for the next six months?
5. How much revenue was collected, as opposed to invoiced?
6. What has month-over-month revenue growth been?
7. Which hires or contracts are you considering, at what cost, starting when?
8. What can be cut within 30 days, and what takes longer?
9. Is any funding signed and wired, or only discussed?
10. How long can each founder go on current pay?
11. At what runway did you agree to start raising or cutting?
12. Who does the monthly close, and when was the last one?

## Artifact skeletons

**Monthly burn table** (columns match `runway-burn.md`)

```markdown
| Month | Cash In | Cash Out | Net Burn | Cash Balance | Runway (months) |
|-------|---------|----------|----------|--------------|-----------------|
| YYYY-MM | | | | | |

One-off items: <month, item, amount>
Trailing 3-month net burn: <amount> → runway <n> months → cash-out date YYYY-MM-DD
Planned net burn incl. commitments: <amount> → runway <n> months → cash-out date YYYY-MM-DD
Decision date: YYYY-MM-DD
Source: bank statements to YYYY-MM-DD / assumption: <item>
```

**Default alive check** (fields from the template)

```markdown
- **Default alive:** <Yes / No>
- **Assumed monthly revenue growth rate:** <%> (basis: last <n> months, source)
- **Month you break even at current trajectory:** <YYYY-MM / Never>
- **If default dead:** the plan is to <raise / cut costs / accelerate revenue>, decided by YYYY-MM-DD
- Sensitivity: with growth halved, <result>
```

**Scenarios**

```markdown
| Case | Revenue growth | Churn | Hiring | Net burn at M+6 | Runway (months) | Cash-out date | Break-even month |
|---|---|---|---|---|---|---|---|
| Low | | | | | | | |
| Base | | | | | | | |
| High | | | | | | | |
```

**Hiring impact**

```markdown
| Proposed hire or commitment | Start (YYYY-MM) | Loaded monthly cost | Milestone it serves | Runway before (base / low) | Runway after (base / low) | Decision |
|---|---|---|---|---|---|---|
```

**Triggers**

```markdown
| Trigger condition | Action agreed in advance | Owner | Status (not fired / fired on YYYY-MM-DD) |
|---|---|---|---|
```

## Storage conventions

- Burn, runway, and the default alive check live in `.productmap/05_operations/finance/runway-burn.md`. Fill the table and fields in place and keep the Runway Alert Thresholds table, adjusted if the founders agree other levels.
- The template has no sections for scenarios, hiring impact, or cut triggers. Add `## Scenarios`, `## Hiring Plan Impact`, and `## Cut Triggers` below Runway Alert Thresholds.
- Model inputs and the detailed scenario assumptions stay in `.productmap/05_operations/finance/financial-model.md`. Record changed assumptions in its Key Assumptions Log.
- The round plan in `.productmap/00_company/fundraising/fundraising-strategy.md` links to the burn file. Keep cash numbers out of it.
- Bank exports and ledger extracts go in `.productmap/06_data/analytics/` with dated names, or stay in the accounting tool with its location noted in `.productmap/00_company/resources.md`. Never paste account numbers or credentials.
- A dated monthly review note, if kept: `.productmap/05_operations/finance/runway-review-YYYY-MM.md`.
- Every figure carries a currency and an as-of date.

## Quality bar

- Runway uses cash figures with a dated bank balance.
- Net burn is a three-month average, with one-off items listed.
- Both trailing and planned runway are shown, with a cash-out date and a decision date.
- The default alive answer states its growth assumption and a sensitivity check.
- Three cases exist, and none counts unsigned funding.
- Each proposed hire shows runway before and after on base and low cases.
- Raise and cut triggers are written as condition and action.
- Each number is evidence with a source and a date, or a labeled assumption.
- The output names the points to confirm with an accountant or a lawyer.
- The next review has a date.

## Related on Product Map

- Agent: **[Calculate unit economics](https://app.productmap.io/agents/unit-economics)** — model LTV, CAC, and contribution margin.

More AI PM agents from Product Map: https://www.productmap.io/
