---
name: startup-financial-model
description: Build an 18 to 24 month monthly financial model as Markdown tables with revenue drivers, cost of goods, operating costs, headcount, cash and runway, three scenarios, a labeled assumptions table, and sanity checks.
---

# Startup financial model — Skill

## Name

`startup-financial-model` — Build a driver-based monthly model a founder can explain line by line, with every assumption labeled and three scenarios for runway.

## When to use

- You're preparing to raise and need to show how the money turns into milestones.
- You know your bank balance and can't say which month the cash runs out under a slower plan.
- A hire is planned and you want to see what it does to runway before making the offer.
- Pricing or the funnel changed and the old projection no longer matches reality.
- An investor asked for "a simple model" and you have a spreadsheet nobody can follow.
- Use a sibling skill instead for burn tracking and cut triggers (`.claude/skills/runway-burn-planning/SKILL.md`) or for sizing the round (`.claude/skills/fundraising-strategy/SKILL.md`).

## Inputs (ask user for these)

- Company name:
- Artifact date (YYYY-MM-DD) (use today's date unless the founder gives another):
- Model start month (`YYYY-MM`) and length (18 or 24 months):
- Currency:
- Cash in the bank today, and any funding signed but not yet received:
- Revenue model (subscription, usage, one-off, take rate, services) and prices by plan:
- Current paying customers, monthly revenue, and monthly churn, with sources:
- Funnel today (monthly visitors or leads, each conversion step, sales cycle length):
- Costs to deliver the product (hosting, AI and API usage, payment fees, support):
- Current monthly spend by category:
- People on payroll and planned hires (role, start month, monthly cost, on-costs %):
- Funding you plan to raise (amount, expected month), marked as not committed:

## Outputs

- Financial model (Markdown) containing:
  - Assumptions table: every driver with value, basis, and label
  - Monthly revenue table (funnel x price)
  - Monthly cost table (cost of goods, operating costs by function)
  - Headcount plan
  - Monthly cash and runway table
  - Low, base, and high scenarios with cash-out month
  - Sanity checks: gross margin, LTV to CAC, CAC payback, growth rate
  - Open questions and items for an accountant
- Where to store it:
  - `.productmap/05_operations/finance/financial-model.md` (existing template; fill its five sections and add `Monthly Model` below `18–24 Month Projection`)
  - Bank, billing, and analytics exports: `.productmap/06_data/analytics/`

## Repo knowledge to pull

- Start here: `.productmap/INDEX.md`
- Target file: `.productmap/05_operations/finance/financial-model.md` (sections `Revenue Drivers`, `Cost Structure`, `18–24 Month Projection`, `Scenarios`, `Key Assumptions Log`)
- Recorded cash and burn: `.productmap/05_operations/finance/runway-burn.md`, `.productmap/05_operations/finance/finance.md`
- Per-customer economics: `.productmap/03_analysis/unit-economics/unit-economics.md`
- Pricing and revenue streams: `.productmap/01_strategy/business-model/business-model.md`
- Funnel rates: `.productmap/03_analysis/kpis-metrics/metrics-tracking.md`, `.productmap/06_data/analytics/`
- Team and planned hires: `.productmap/00_company/team.md`
- Raise amount and milestones: `.productmap/00_company/fundraising/fundraising-strategy.md`
- Roadmap items that carry cost: `.productmap/01_strategy/mvp-roadmap/roadmap.md`

## Detailed prompt (copy/paste)

```
You are a finance partner for an early-stage founder. Build a monthly driver-based model for the company below, with three scenarios and sanity checks. The founder must be able to explain every line. Read the repo first and cite every path you used.

Repo-first context to consult:
- Start at: .productmap/INDEX.md
- Read and keep the headings of: .productmap/05_operations/finance/financial-model.md
- Read: runway-burn.md, finance.md, unit-economics.md, business-model.md, metrics-tracking.md, team.md, fundraising-strategy.md, roadmap.md
- Read exports in .productmap/06_data/analytics/ and any path the founder lists.

Constraints:
- Write every date as YYYY-MM-DD and every month as YYYY-MM.
- Invent nothing. Every driver comes from the founder, the repo, or a cited source. A missing driver is an open question, and its rows read "needs input".
- Label every assumption (evidence: <repo path or source>) or (assumption: <test or the date it gets checked against real numbers>).
- Planned funding is not cash. Show it on its own line, marked "not committed", and show runway with and without it.
- Compute, do not estimate. If you can run code, generate the tables with code. Recheck every total.
- Months are rows, metrics are columns. One currency throughout.
- You are not an accountant. Revenue recognition, tax, payroll on-costs, and R&D credits differ by country. List them under "Confirm with an accountant" and do not decide them.

Model context (founder-provided):
- Company:
- Artifact date (YYYY-MM-DD):
- Start month and length:
- Currency:
- Cash today and signed funding:
- Revenue model and prices:
- Customers, monthly revenue, churn:
- Funnel and sales cycle:
- Delivery costs:
- Current monthly spend by category:
- Payroll and planned hires:
- Planned raise (not committed):

Steps:
1) Assumptions table. One row per driver. Columns: # | Driver | Value | Unit | Basis | Label (evidence / assumption) | Check date. Cover: top-of-funnel volume and its monthly growth, each conversion rate, sales cycle, price per customer per month, monthly churn, variable cost per customer, fixed delivery costs, each operating cost line, each hire, on-costs %, collection delay if invoiced.
2) Revenue table, base case. Formulas:
   - New customers = top-of-funnel volume x conversion rates, shifted by the sales cycle
   - Churned = customers at end of previous month x monthly churn
   - Customers at end = previous + new - churned
   - Revenue = customers at end x average price. For usage or one-off models: units x price.
   Columns: Month | Top of funnel | Conversion % | New customers | Churned | Customers at end | Average price | Revenue
3) Cost table. Cost of goods = variable cost per customer x customers + fixed delivery costs. Gross margin % = (revenue - cost of goods) / revenue. Operating costs by function: product and engineering, sales and marketing, general and admin. People costs sit in the function they work in.
   Columns: Month | Cost of goods | Gross margin % | Product and engineering | Sales and marketing | General and admin | Total costs
4) Headcount plan. Columns: Role | Function | Start month | Monthly cost with on-costs | Why now (the milestone it serves).
5) Cash table. Net burn = total costs - cash collected. Cash at end = previous cash + cash collected + funding received - total costs. Runway = cash at end / average net burn of the last three months. Write "profitable" when net burn is zero or negative.
   Columns: Month | Cash collected | Funding received | Total costs | Net burn | Cash at end | Runway (months)
6) Scenarios. Change at most three drivers per scenario and name them.
   - Low: the founder's cautious case, for example slower funnel growth, higher churn, one hire delayed
   - Base: the assumptions table as written
   - High: the founder's strong case
   Columns: Scenario | Drivers changed | Revenue at month 12 | Net burn at month 12 | Cash-out month | Runway today
   Map low, base, high to the Pessimistic, Base, Optimistic rows of the file's Scenarios table.
7) Sanity checks, on the base case. Show each formula with its numbers.
   - Gross margin %
   - CAC = sales and marketing costs / new customers, same period
   - LTV = average price x gross margin % / monthly churn. If churn is zero or unknown, cap customer lifetime at 36 months and label it an assumption.
   - LTV to CAC, and CAC payback in months = CAC / (average price x gross margin %)
   - Highest month-on-month revenue growth in the model against the highest the company has recorded
   Compare with common rules of thumb for software (LTV to CAC near 3 or more, payback under 12 months, gross margin of 70% or more) and call them rules of thumb, not targets. Early numbers from few customers are noisy. Say so.
   Flag: cash-out before month 12 in the low case, any month with runway under 6, growth above the recorded best, hires with no revenue or milestone logic.
8) Headline rows for the file's projection table: customers, revenue, total costs, net burn, cash at months 3, 6, 12, 18, 24.
9) The five assumptions the result is most sensitive to. For each, show what a 20% worse value does to the cash-out month.
10) Open questions, and the list "Confirm with an accountant".

Output format (Markdown), in this exact order:
1. Title: <Company> financial model, YYYY-MM-DD
2. Assumptions table
3. Revenue (monthly, base case)
4. Costs (monthly, base case)
5. Headcount plan
6. Cash and runway (monthly, base case)
7. Scenarios (low / base / high)
8. Sanity checks
9. Headline projection (months 3, 6, 12, 18, 24)
10. Most sensitive assumptions
11. Open questions
12. Confirm with an accountant
13. Repo paths referenced
```

## Workflow (runbook)

1. Collect recorded numbers first: bank balance, last three months of spend, current customers and revenue. Take them from `.productmap/05_operations/finance/runway-burn.md` or the founder's exports.
2. Read the repo, starting at `.productmap/INDEX.md`. Prices come from `.productmap/01_strategy/business-model/business-model.md` and funnel rates from `.productmap/03_analysis/kpis-metrics/metrics-tracking.md`. Where a file and the founder disagree, list both and ask.
3. Fill the assumptions table with the founder before any projection. Each row gets a basis and a check date.
4. Run the prompt. Generate the monthly tables with code or a spreadsheet when you can, then paste them as Markdown.
5. Check the arithmetic. Month 1 opening cash equals the bank balance. Customers reconcile month to month. Total costs equal the sum of the function columns plus cost of goods.
6. Read the scenarios with the founder. If the low case runs out of cash before the next milestone, take that to `.claude/skills/runway-burn-planning/SKILL.md`.
7. Read the sanity checks. A flag is a question to answer, and the answer goes in the assumptions table.
8. Write back to `.productmap/05_operations/finance/financial-model.md`:
   - Fill `Revenue Drivers` and `Cost Structure` from the assumptions table.
   - Fill `18–24 Month Projection` with the headline rows and `Scenarios` with the three cases.
   - Add the section `Monthly Model` below `18–24 Month Projection` with the revenue, cost, headcount, and cash tables.
   - Add each assumption to `Key Assumptions Log` with today's date and its basis.
9. Send the "Confirm with an accountant" list to an accountant before the model goes to investors.
10. Each month, compare the model with recorded numbers, mark assumptions validated or not, and re-run when a driver is off by more than 20%.

## Quality checklist

- Every driver sits in the assumptions table with a value, a unit, a basis, a label, and a check date.
- The model covers 18 or 24 months, one row per month, in one currency.
- Customers reconcile each month: previous + new - churned = end.
- Revenue follows from funnel volume, conversion, churn, and price. No typed-in revenue line.
- Costs split into cost of goods and three functions, and every hire has a start month and a loaded cost.
- Opening cash matches the bank balance, and planned funding is marked "not committed" with runway shown both ways.
- Three scenarios each name the drivers changed and state a cash-out month.
- Sanity checks show formula and numbers, and rules of thumb are labeled as such.
- All flags are listed, including any month with runway under 6.
- Tax, revenue recognition, and payroll items sit under "Confirm with an accountant".
- `Repo paths referenced` lists every file read, starting with `.productmap/INDEX.md`.

## Related on Product Map

- Agent: **[Calculate unit economics](https://app.productmap.io/agents/unit-economics)** — model LTV, CAC, and contribution margin.

More AI PM agents from Product Map: https://www.productmap.io/
