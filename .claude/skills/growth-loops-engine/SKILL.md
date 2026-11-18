---
name: growth-loops-engine
description: Use this skill when the user is planning how the product grows as a system, finding the funnel bottleneck, choosing an engine of growth or a product-led versus sales-led motion, or designing growth loops. Triggers — "growth strategy", "growth loop", "engine of growth", "where is our funnel leaking", "product-led or sales-led", "north star metric for growth", "improve activation", "viral loop", "growth ideas", "should we spend on acquisition".
---

# Growth loops and engine — Claude skill

Use this skill to treat growth as one system with one constraint: a growth canvas, a funnel with a named bottleneck, one primary engine, a motion, and one or two loops written as systems. Read `.productmap/` first. The sequencing rule holds throughout: retention before scale.

## When this skill applies

- The product has users, and the founder asks how to grow.
- Signups rise while active use and revenue stay flat.
- The team runs scattered tactics and can't say which one worked.
- The founder is choosing between self-serve, sales-assisted, and sales-led.
- Someone proposes spending on ads and nobody has checked retention.
- A referral or content idea needs to become a loop with a metric.
- A backlog of growth ideas needs ranking against one bottleneck.

## When not to use this skill (hand off instead)

- **A four-week experiment sprint with cards and cadence.** Use `.codex/skills/growth-experiment-sprint/SKILL.md`. This skill picks the bottleneck and the loop. The sprint runs the tests.
- **Campaign ideas, channel mix, and a content calendar.** Use `.claude/skills/digital-marketing-campaigns/SKILL.md`.
- **Selling by hand to the first ten customers.** Use `.claude/skills/founder-led-sales/SKILL.md`. Before those customers exist, there is no loop to design.
- **Price, tiers, and paywall placement.** Use `.claude/skills/monetization-pricing/SKILL.md`.
- **Positioning and the core promise.** Use `.claude/skills/value-proposition-positioning/SKILL.md`.
- **Deciding whether to pivot after weak results.** Use `.gemini/skills/pivot-or-persevere-review/SKILL.md`.
- **A weekly numbers review.** Use `.gemini/skills/founder-weekly-review/SKILL.md`.
- **Burn and runway limits on growth spend.** Use `.claude/skills/runway-burn-planning/SKILL.md`.

## Repo knowledge to consult first

- `.productmap/INDEX.md` for the map of the tree.
- `.productmap/02_discovery/growth-sales/growth-sales.md`: Key Artefacts and Early-Stage Focus. The growth plan is written here.
- `.productmap/03_analysis/kpis-metrics/kpis-metrics.md` for the metric hierarchy.
- `.productmap/03_analysis/kpis-metrics/metrics-tracking.md`: North Star Metric, the validation milestone table, Events to Track by AARRR stage, Reporting Cadence.
- `.productmap/03_analysis/analytics/analytics.md` for funnel and cohort readouts.
- `.productmap/01_strategy/product-market-fit/pmf-signals.md`: Sean Ellis Survey, Retention Curve Check, Current Verdict.
- `.productmap/03_analysis/unit-economics/unit-economics.md` for acquisition cost, lifetime value, and payback where known.
- `.productmap/06_data/analytics/` for exported funnels and cohorts.

If no numbers exist, say so. Draft the plan with labeled assumptions and make instrumentation the first action.

## Retention gate

Check this before any other growth work. Growth spend on a product people leave buys churn.

| What `pmf-signals.md` shows | Where growth work goes |
|---|---|
| Retention curve flattens for a known group, or 40% or more "very disappointed" in the Sean Ellis survey | Acquisition and loops, aimed at the group that stays |
| Curve decays toward zero, or the survey is well under 40% | Activation and retention only. No paid acquisition |
| Unknown: no cohorts, no survey | Instrument first. Acquire by hand in small numbers to create cohorts worth reading |
| Retention holds in one segment and fails in others | Narrow to the segment that stays. Stop acquiring the others |

The 40% line and the flattening curve are heuristics already recorded in the repo. State the gate result in one line at the top of the plan: ready to scale acquisition, or not yet and why.

## Growth canvas and the four fits

**Growth canvas.** Fill it in this order. Each row constrains the next.

| Row | What to write |
|---|---|
| Target audience | The segment that retains, from the ICP |
| Value proposition | The promise, copied from the positioning statement |
| North star metric | A count of value delivered to customers, such as weekly teams completing the core action. Revenue arrives too late to steer by |
| Input metrics | Three to five numbers the team can move this month that drive the north star |
| Wow moment | The first point where a new user gets the promised outcome |
| Product strengths | What in the product creates return visits, invites, or expansion |
| Loop or channel bet | The one mechanism you believe will bring the next users |
| Activities | The few pieces of work serving the bet |
| Budget and owner | Money, hours, and one named person |

**Four fits.** Growth holds when four pairs fit each other. Find the weakest.

| Fit | Question | Sign of a weak fit |
|---|---|---|
| Market and product | Does a defined group keep using it? | Poor retention across every segment |
| Product and channel | Does the product suit the way the channel works? | A product needing a demo, sold through app-store search |
| Channel and model | Does the price support the channel's cost? | A low monthly price sold through outbound sales |
| Model and market | Are there enough buyers at this price to reach your goal? | A high price in a market of a few hundred accounts |

Changing one side of a fit changes its partner. A new price can break a channel that worked.

## Customer Factory and activation

Picture the business as a factory turning strangers into satisfied customers through five stages. Give every stage two numbers: the share of people who move on, and how long the move takes. Read both by signup cohort.

| Stage | Conversion metric (example) | Time metric (example) |
|---|---|---|
| Acquisition | Visitor to signup | Days from first visit to signup |
| Activation | Signup to wow moment | Minutes or days to the wow moment |
| Retention | Active in week 4 | Days between sessions |
| Revenue | Activated to paying | Days from signup to first payment |
| Referral | Customers who bring one more | Days from signup to first invite |

Finding the bottleneck:

- Compare each stage with the others and with its own past. The stage with the steepest drop or the longest delay is the constraint.
- Before fit, work the stages in this priority: retention, then activation, then referral and revenue, then acquisition.
- One constraint at a time. Improving a stage ahead of the constraint piles users in front of it.
- State the evidence for the bottleneck in one sentence, and what result would change your mind.
- Use rates and cohorts. A cumulative total only rises and hides the leak.
- In B2B, keep user-level and account-level metrics apart.

When activation is the bottleneck:

1. Define the wow moment as one observable event.
2. List every step between signup and the event.
3. Mark each step: required for value, can wait until later, or remove.
4. Add help where users stall: sample data, templates, a checklist, an empty state telling them what to do next, a message triggered by inactivity.
5. Measure activation rate, time to the wow moment, and drop-off per step.

## Engines of growth and motion

**Engines.** Pick one primary engine. Tune it before adding a second.

| Engine | How it grows | Governing metric | Fits when |
|---|---|---|---|
| Sticky | Customers stay, so each new one adds to the base | New customer rate above churn rate | The product is a habit, a workflow, or a system of record |
| Viral | Each user brings others through use | Viral coefficient = invites per user × invite conversion | Using the product exposes others to it: sharing, collaboration |
| Paid | Revenue from a customer funds the next acquisition | Lifetime value above acquisition cost, with a payback period you can fund | Margins and retention are known and the channel has room |

Notes:

- A viral coefficient above 1 is rare. Below 1 it still lowers the blended acquisition cost.
- The paid engine comes last for most early startups. It needs retention and margin data the other two don't.
- Name the next engine to build once the first one flattens.

**Motion.** How a buyer goes from interest to payment.

| Signal | Points to product-led | Points to sales-led |
|---|---|---|
| Time to value | Minutes or hours | Weeks, with setup or integration |
| Who buys | The user | A committee or a budget holder apart from the user |
| Price level | Card-payable | Contract, security review, procurement |
| Complexity | Self-explanatory | Needs configuration or training |

Mostly left column: product-led. Mixed: hybrid, where users start alone and a founder steps in on defined product signals, such as a third teammate invited, a usage limit reached, or a pricing page viewed twice. Mostly right column: sales-led, with a trial for qualified prospects. Write the handoff signals down.

## Growth loops, idea scoring, and guardrails

**Loops as systems.** A loop is a cycle where the output of one round becomes the input of the next. Write it in four parts.

`Input → Action → Output → Reinvestment`

| Loop type | Input | Action | Output | Reinvestment |
|---|---|---|---|---|
| Content | A user creates or publishes something | It gets indexed or shared | New visitors find it | Some sign up and create more |
| Referral or invite | An active user | Invites a colleague to do the job together | The colleague joins | The colleague invites others |
| Paid | Revenue from customers | Spend on a channel | New customers | Their revenue funds more spend |
| Sales | A satisfied customer | Gives a case study or introduction | New qualified conversations | New customers become references |

For each loop add a **loop metric**, such as new users per active user per month, and the **funnel metric showing where it breaks**. A loop doesn't replace the funnel. Design one or two loops only, starting with the one the product already shows signs of.

**Idea scoring.** Tag every idea with its stage, the metric it moves, and the segment. Drop ideas aimed at any stage other than the bottleneck. Then rank.

- **ICE** for fast ranking: Impact, Confidence, Ease, each 1 to 10, averaged.
- **RICE** when ideas reach different numbers of users: (Reach × Impact × Confidence) ÷ Effort.

Scores are opinions with numbers attached. Use them to order a list, never to prove an idea.

**Guardrails.**

- Pair each growth metric with a counter-metric: activation with support load, conversion with refunds, invites with spam complaints.
- No hidden cancellation, forced renewal, fake urgency, or pre-ticked options. Decline ideas crossing this line and say why.
- A tactic copied from another company works only when audience, price, and buying process match. Say when they don't.
- Every tactic fades. Note how long you expect it to work.

## Workflow

1. **Read the repo.** Metrics, cohorts, PMF verdict, unit economics.
2. **Ask at most three questions in one message:** product and segment, stage with best-known numbers, what growth work was tried. Skip those the repo answers.
3. **State the retention gate.**
4. **Draft the growth canvas** with assumptions labeled.
5. **Fill the Customer Factory table.** Name the bottleneck, its evidence, and what would change your mind.
6. **Run the four fits.** Name the weakest.
7. **Choose the engine and the motion.** One primary engine, its governing metric, a health threshold the founder sets, and handoff signals.
8. **Design one or two loops** as input, action, output, reinvestment, with metrics.
9. **List 10 to 15 ideas against the bottleneck.** Score. Keep the top three to five.
10. **Set guardrails and counter-metrics.**
11. **Write into `growth-sales.md`.** Pass the top ideas to the experiment sprint. List open assumptions.

Draft first, then refine one weak block per turn. Fold each answer back into the canvas so it stays coherent.

## Pitfalls

- **Starting with "which campaign?"** Start with where the factory slows down.
- **Filling a leaking funnel.** More acquisition while retention is the constraint.
- **Revenue as north star.** It moves after the behaviour you can influence.
- **Vanity metrics alone.** Signups, followers, and page views with nothing downstream.
- **Three engines at once.** Nobody can tell what works.
- **A loop on paper only.** If no user has done the action unprompted, test the action before building the loop.
- **Ideas with no stage, metric, or segment.** They can't be ranked or judged.
- **Experiments with no baseline or decision rule.** Results become stories.
- **Copying a famous tactic.** The context that made it work is missing.
- **Treating a channel as permanent.** Channels saturate and platforms change rules.
- **Aggregates over cohorts.** New signups mask old users leaving.

## Questions to ask the user

1. Which users are still active a month after signup? What do they share?
2. What is the first moment a new user gets the promised outcome?
3. How long does it take to reach it, and what share get there?
4. Where is the largest drop between signup and payment?
5. How did your last twenty users find you?
6. Does using the product expose it to other people?
7. Can a user get value without talking to you?
8. Who pays, and can they pay by card?
9. What does it cost to acquire a customer today, and how do you know?
10. Which growth tactics have you tried, with what result?
11. Which one number, if it moved, would tell you customers get more value?
12. How much money and time per week can growth work use?

## Artifact skeletons

**Growth plan** (sections to add to `growth-sales.md`)

```markdown
## Growth plan (as of YYYY-MM-DD)

Retention gate: <ready to scale acquisition / not yet, because ...> (source: <path>)

### Growth canvas
- Target audience:
- Value proposition:
- North star metric:
- Input metrics:
- Wow moment:
- Product strengths:
- Loop or channel bet:
- Activities:
- Budget and owner:

### Customer Factory
| Stage | Conversion metric | Time metric | Current value | Confidence (High / Medium / Assumption) |
|---|---|---|---|---|
| Acquisition | | | | |
| Activation | | | | |
| Retention | | | | |
| Revenue | | | | |
| Referral | | | | |

Bottleneck: <stage>. Evidence: <one sentence, path>. Would change our mind: <result>.

### Four fits
| Fit | Verdict (Strong / Weak / Unknown) | Why |
|---|---|---|

### Engine and motion
Primary engine: <engine>, governing metric <metric>, healthy above <threshold>.
Next engine: <engine>, once <condition>.
Motion: <product-led / hybrid / sales-led>. Sales steps in on: <signals>.
```

**Growth loop**

```markdown
### Loop: <name> (<type>)
- Input:
- Action:
- Output:
- Reinvestment:
- Loop metric:
- Funnel metric showing the break:
- First experiment to strengthen it:
```

**Idea backlog**

```markdown
| Idea | Stage | Metric it moves | Segment | Evidence or assumption | Impact | Confidence | Ease | ICE | Counter-metric |
|---|---|---|---|---|---|---|---|---|---|
```

## Storage conventions

- The growth plan goes in `.productmap/02_discovery/growth-sales/growth-sales.md`. The file is an overview with no plan sections yet, so add `## Growth plan` below Early-Stage Focus using the skeleton.
- The north star and input metrics are defined in `.productmap/03_analysis/kpis-metrics/metrics-tracking.md`. Change them there and copy the names into the canvas.
- Experiments from the top ideas go into the Hypothesis Backlog in `.productmap/02_discovery/experiments/experiments.md`.
- Cohort and funnel exports go in `.productmap/06_data/analytics/` with dated file names.
- Survey results and retention readings update `.productmap/01_strategy/product-market-fit/pmf-signals.md`.
- Dates are absolute. Every metric value carries its date and cohort.

## Quality bar

- The retention gate is stated in one line with its source.
- The north star counts delivered customer value.
- One bottleneck stage is named, with evidence and what would change the call.
- The weakest of the four fits is named.
- One primary engine with a governing metric, and one motion with handoff signals.
- Each loop has input, action, output, reinvestment, a loop metric, and a break point.
- Every idea is tied to the bottleneck stage and carries a counter-metric.
- No benchmark, acquisition cost, or viral coefficient appears without a source. Unknowns are labeled assumption.
- Nothing scales before retention supports it, and the plan says so.

## Related on Product Map

- Agent: **[Build product growth strategy](https://app.productmap.io/agents/growth-marketing)** — pick your growth engine, design loops and sprints.
- Workflow: **[GTM strategy to growth loops](https://app.productmap.io/workflows/gtm-strategy-to-growth-loops)** — prepare the go-to-market strategy, generate digital marketing ideas, then plan growth loops.

More AI PM agents from Product Map: https://www.productmap.io/
