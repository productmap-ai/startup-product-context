---
name: monetization-pricing
description: Use this skill when the user is choosing how to charge, picking a value metric, designing tiers and packaging, checking willingness to pay, or planning a price change. Triggers — "how should we charge", "pricing model", "what price should I set", "freemium or free trial", "pricing tiers", "value metric", "willingness to pay", "raise our prices", "discount policy", "usage-based pricing".
---

# Monetization and pricing — Claude skill

Use this skill to design how a startup earns money: the model, the value metric, the tiers, the price range, the discount rules, and the way a price change is announced. Read `.productmap/` first. Draft a first monetization hypothesis from what the repo holds, then refine it against evidence.

Tax, invoicing, and contract terms vary by country. Confirm them with an accountant or a lawyer.

## When this skill applies

- The product is live or close to it, and the founder has no price or a price copied from a competitor.
- The founder is choosing between subscription, usage, freemium, one-off, take rate, or services.
- A free tier attracts signups and converts almost nobody.
- Customers on the cheapest plan use the product heavily and have no reason to upgrade.
- Deals close fast with no pushback, or every deal ends in a custom discount.
- A price rise or a packaging change is planned for existing customers.
- An investor asked how revenue per customer grows and the answer was unclear.

## When not to use this skill (hand off instead)

- **Auditing an existing pricing page.** Use `.codex/skills/pricing-page-audit/SKILL.md`.
- **Synthesising many willingness-to-pay interviews and survey results.** Use `.gemini/skills/pricing-research-synthesis/SKILL.md`. This skill plans the checks and reads small samples.
- **An 18 to 24 month model with revenue drivers.** Use `.codex/skills/startup-financial-model/SKILL.md`.
- **Runway effects of a price or margin change.** Use `.claude/skills/runway-burn-planning/SKILL.md`.
- **The value proposition is unclear.** Use `.claude/skills/value-proposition-positioning/SKILL.md` first. Price follows value.
- **Negotiating one deal or a pilot price.** Use `.claude/skills/founder-led-sales/SKILL.md`.
- **Competitor pricing teardown.** Use `.gemini/skills/competitor-teardown-matrix/SKILL.md`.

## Repo knowledge to consult first

- `.productmap/INDEX.md` for the map of the tree.
- `.productmap/01_strategy/business-model/business-model.md`: Lean Canvas rows for Revenue Streams, Cost Structure, Customer Segments, and their Validated / Assumed status.
- `.productmap/03_analysis/unit-economics/unit-economics.md`: whatever exists on LTV, CAC, and contribution margin.
- `.productmap/01_strategy/segmentation/icp-b2b.md`: Budget / ACV, Decision Makers, Sales Cycle.
- `.productmap/01_strategy/segmentation/icp-b2c.md`: Willingness to Pay, Tools Used.
- `.productmap/01_strategy/competitors/competitor-matrix.md`: named alternatives, for price anchors.
- `.productmap/00_company/product/value-proposition.md`: the High pains, the Must-have gains, and the named alternative.
- `.productmap/02_discovery/growth-sales/founder-led-sales.md`: Pricing Conversations, where price reactions are logged.
- `.productmap/05_operations/finance/financial-model.md`: Revenue Drivers and Cost Structure, for variable costs per customer.

## Model choice by stage

Before product-market fit, pick the simplest model you can charge on this month. A paying customer teaches more about price than any survey.

| Model | Fits when | Breaks when | Early-stage note |
|---|---|---|---|
| Flat subscription | Value is steady and usage is similar across customers | Heavy users cost far more to serve than light ones | Simplest to sell and explain. A good default for a first price |
| Per-seat subscription | Value grows with the number of people using it | One login can be shared, or value sits with one power user | Buyers know it. It discourages wide adoption |
| Usage-based | Value and cost both scale with a measurable unit | The bill is hard to predict, so buyers hesitate | Add a minimum or a prepaid bundle to steady revenue |
| Freemium | Marginal cost per free user is near zero and free users bring others | Free covers the whole job, or support costs grow with free users | Costly before you know what people pay for |
| Free trial or reverse trial | Value shows within the trial period | Setup takes longer than the trial | Usually a safer start than a permanent free plan |
| One-off purchase | The product is used once or rarely | You carry ongoing costs per customer | Cash now, no recurring base |
| Take rate | You sit in the transaction between two sides | Parties can settle outside your product | Needs volume. Charge the side with more to gain |
| Services or paid pilot | The outcome needs hands-on work today | Margins stay low and time doesn't scale | Fine for funding learning. Set a date to productise |

Decision rules:

- Charge from the first customer. Free pilots hide the willingness-to-pay signal.
- One model at a time. Hybrids come after the first model shows its limits.
- If variable cost per customer is material, as with AI inference, the model has to cover it at heavy usage. Check Cost Structure in `financial-model.md`.

## Value metric

The value metric is the unit you charge per: seat, project, transaction, record, gigabyte, outcome.

A good one passes four tests:

1. **Grows with value.** Customers who get more from the product use more of the unit.
2. **Easy to understand.** A buyer predicts next month's bill without a calculator.
3. **Measurable and auditable.** Both sides trust the count.
4. **Hard to game.** Sharing a login or batching work doesn't dodge it.

Method: list three to five candidate metrics. For each, ask whether your happiest customers score high on it and your least engaged score low. The metric separating them most cleanly wins. Record the reasoning and whether it rests on usage data or assumption.

When no metric passes, start flat and add the metric as a tier limit later.

## Tier design with upgrade pressure

Tiers exist so different buyers choose for themselves and have a reason to move up.

- **Three tiers at most** at this stage. Two is fine. One is acceptable for the first ten customers.
- **Name the buyer for each tier.** Solo user, small team, company with security review. A tier with no buyer in mind is clutter.
- **Fence with limits customers hit as they succeed:** amount of the value metric, collaboration, automation, history, admin and security controls, support response.
- **Keep the core job in every paid tier.** Crippling the entry tier loses the customer before they see value.
- **Define the upgrade trigger.** The event that makes the next tier the obvious choice: the sixth teammate, the hundredth record, the first audit request.
- **Use the middle tier as the recommended one.** A higher tier beside it makes its price look reasonable.
- **Enterprise or "contact us"** only when deals need contracts, security reviews, or custom terms.

Free plan rule: offer one only when all three hold. Serving a free user costs close to nothing. Free users bring paying users through invites, content, or network effects. The free plan stops short of the full job. Otherwise use a time-limited trial.

Annual plans: a discount of 10 to 20% for paying yearly is common, often presented as two months free. It brings cash forward and lowers churn. Offer it after the customer has seen value.

## Willingness-to-pay checks

Use three sources and compare them. None is reliable alone.

**1. Van Westendorp price sensitivity questions.** Ask people in the target segment, after they understand the product:

- At what price would it be so cheap you would doubt its quality?
- At what price would it be a bargain?
- At what price would it start to feel expensive, though you would still consider it?
- At what price would it be too expensive to consider?

Plot the cumulative answers. The acceptable range sits between the point where "too cheap" crosses "expensive" and the point where "bargain" crosses "too expensive". With fewer than about 30 answers from one segment, read it as a rough range only. Mixed segments blur the curves.

**2. Competitive and substitute anchors.** List what the customer pays today for the alternative: a tool, a contractor, staff hours. Your price is read against it. Being far below the anchor signals a lesser product. Being above it needs a reason the buyer can repeat.

**3. Value-based check.** Estimate the yearly value delivered: hours saved × hourly cost, revenue gained, cost avoided. A common rule of thumb prices at 10 to 20% of the value, leaving the customer a clear return. Treat the result as a ceiling check, since value estimates run optimistic.

**Real behaviour outranks all three.** Quote the price in sales calls and log the reaction in Pricing Conversations in `founder-led-sales.md`. Sales practice holds that if nobody pushes back, the price is too low. Run presales and paid pilots where possible.

## Packaging, discounts, stress test, and price changes

**Discount rules.** Write them once, then follow them.

- Trade for a commitment: annual prepayment, a case study, a reference call, a longer term.
- Set a maximum discount the founder gives without a second opinion, and an expiry date on every offer.
- Record each discount and its reason. A pattern of discounts means the list price or the packaging is wrong.
- Early-customer pricing has an end date written into the offer.

**Stress test.** Before publishing, answer each:

| Question | Where to check |
|---|---|
| Does gross margin hold for the heaviest plausible user on each tier? | `financial-model.md`, Cost Structure |
| Does the price recover acquisition cost in a period you can fund? | `unit-economics.md` |
| What happens to the bill when usage grows tenfold? | The value metric |
| Can a customer stay on the entry tier forever while getting full value? | Tier limits |
| What does the strongest alternative charge, and how do you answer the comparison? | `competitor-matrix.md` |
| What is the loudest objection, and who raises it? | Pricing Conversations log |
| Does the buyer in the ICP hold budget at this level without extra approval? | ICP file |

**Communicating a price change.**

1. Decide who is affected: new customers only, or existing ones too.
2. Choose a policy for existing customers: keep the old price permanently, keep it for a fixed period, or move everyone with notice.
3. Give notice in advance. Thirty days or more is common. Contracts and consumer law can require longer, so check with a lawyer.
4. Write the message in this order: what changes, when, what it means for this customer, what they get, how to keep the current price if an option exists, who to contact.
5. Tell the heaviest users personally before the general notice.
6. Track churn, downgrades, and support volume for 60 days after the change.

## Workflow

1. **Read the repo.** Revenue Streams, ICP budget lines, alternatives, logged price reactions, variable costs.
2. **Ask at most two questions:** what the product does and who pays. Skip them if answered.
3. **Draft a first monetization hypothesis.** Model, value metric, one to three tiers, a price range. Mark each element evidence or assumption.
4. **Offer three to five concrete changes** with a one-line reason each. Let the founder pick where to go deeper.
5. **Refine the chosen element** and show the full updated version.
6. **Plan willingness-to-pay checks.** Which of the three sources, with whom, by when.
7. **Run the stress test.** Fix every row that fails.
8. **Write discount rules.**
9. **If a price change is involved,** write the policy for existing customers and the message.
10. **Write into `business-model.md`.** Update Revenue Streams and add the pricing section. Add open assumptions to the Hypothesis Backlog.

## Pitfalls

- **Cost-plus pricing.** Customers pay for outcomes. Your costs set a floor only.
- **Copying a competitor's price.** Their costs, segment, and strategy differ from yours.
- **Free for too long.** Early users anchor on zero and feedback comes from people who would never pay.
- **Too many tiers.** Choice slows the decision.
- **A value metric the buyer can't predict.** Unpredictable bills block purchase approval.
- **Discounting on reflex.** It trains every buyer to ask and erases the price signal.
- **Asking "what would you pay?"** Stated numbers run low or random. Use ranges, anchors, and real quotes.
- **Ignoring variable cost.** Heavy users on a flat plan can cost more than they pay.
- **Surprise price rises.** Customers forgive a higher price sooner than a silent one.
- **Never revisiting.** Review price at least twice a year, and after any major feature release.

## Questions to ask the user

1. Who pays, and is the payer the person who uses the product?
2. What do customers pay today for the alternative, in money or hours?
3. What price have you quoted so far, and what happened each time?
4. Which unit of usage best tracks the value a customer gets?
5. What does serving one heavy customer cost you per month?
6. Which buyers are you designing tiers for?
7. What event should push a customer to the next tier?
8. Does a free user bring you anything: invites, data, content?
9. What discount have you given, and what did you get in return?
10. What price would make you nervous to say aloud? Have you tried it?
11. If you change the price, what happens to existing customers?
12. Which part of the pricing are you least sure about?

## Artifact skeletons

**Monetization hypothesis**

```markdown
## Pricing and packaging (as of YYYY-MM-DD)

- Model: <model> (evidence: <path> / assumption)
- Who pays: <buyer>
- Value metric: <unit>, chosen because <reason>
- Price range under test: <low> to <high> per <unit / month>
- Anchor: <alternative and its price, source>

| Tier | For whom | Price | Limits (value metric and features) | Upgrade trigger |
|---|---|---|---|---|
| | | | | |

Discount rules: <trade, maximum, expiry>
Open assumptions: <list, each with a test>
```

**Willingness-to-pay check plan**

```markdown
| Source | Who and how many | Questions or data | By (YYYY-MM-DD) | Result | Reading |
|---|---|---|---|---|---|
| Van Westendorp | | four price questions | | | |
| Anchors | | price of alternatives | | | |
| Value-based | | hours or money per year | | | |
| Real quotes | | price said, reaction | | | |
```

**Price-change note**

```markdown
Subject: <what changes> from YYYY-MM-DD

- What changes: <old> to <new>
- When: YYYY-MM-DD
- For you: <effect on this customer>
- What you get: <new value, if any>
- Your options: <keep current price until YYYY-MM-DD / switch to annual / other>
- Contact: <name, address>
```

## Storage conventions

- The model and price hypothesis go in `.productmap/01_strategy/business-model/business-model.md`. Update the Revenue Streams row and its Validated / Assumed status. The template has no pricing section, so add `## Pricing and packaging` below the Lean Canvas.
- Price reactions from calls go in Pricing Conversations in `.productmap/02_discovery/growth-sales/founder-led-sales.md`.
- Raw survey answers and competitor price captures go in `.productmap/06_data/research/` with dated file names.
- Pricing tests go into the Hypothesis Backlog in `.productmap/02_discovery/experiments/experiments.md`.
- A dated pricing decision record, if kept: `.productmap/01_strategy/business-model/pricing-decision-YYYY-MM-DD.md`.
- Every price carries a currency, a billing period, and an as-of date.

## Quality bar

- One model is chosen, with the reason it fits this stage.
- The value metric passes the four tests, or the output says which test it fails.
- Each tier names its buyer and its upgrade trigger.
- The price range rests on at least two of the three willingness-to-pay sources, each labeled evidence or assumption.
- The stress test table is filled, with failing rows fixed or listed as risks.
- Discount rules are written.
- A price change includes a policy for existing customers and a notice period.
- No competitor price or benchmark is stated without a source and a date.
- `business-model.md` is updated and the changed paths are cited.

## Related on Product Map

- Agent: **[Define monetization strategy](https://app.productmap.io/agents/monetization-pricing)** — pick the right model, pricing, and packaging.

More AI PM agents from Product Map: https://www.productmap.io/
