---
name: value-proposition-positioning
description: Use this skill when the user is defining or testing a value proposition, mapping customer jobs, pains and gains, or writing a positioning statement against a named alternative. Triggers — "value proposition", "value proposition canvas", "jobs pains gains", "positioning statement", "why would they pick us", "how are we different", "who is this for", "test our messaging", "unique value proposition".
---

# Value proposition and positioning — Claude skill

Use this skill to build a Value Proposition Canvas for one segment, assess fit, and write a positioning statement naming the alternative the customer uses today. Read `.productmap/` first. Draft from what the repo and the founder give you, label every guess, then refine the weakest part.

## When this skill applies

- The founder explains the product with features, and listeners ask who it is for.
- The value claim is generic: "saves time", "easy to use", "for everyone".
- Interviews exist, and nobody has turned them into ranked pains and gains.
- A landing page, a deck, or outreach needs one clear message and there are four competing ones.
- The product serves two segments and the founder has to choose whose problem leads.
- The positioning statement compares against no alternative, or against a competitor customers never mention.
- A pivot changed the customer or the product, and the old canvas no longer matches.

## When not to use this skill (hand off instead)

- **The problem itself is unproven.** Use `.claude/skills/startup-idea-validation/SKILL.md` first.
- **Landing page copy and a smoke test card.** Use `.codex/skills/landing-page-smoke-test/SKILL.md`. It takes the positioning from this skill as input.
- **A scored competitor matrix and teardowns.** Use `.gemini/skills/competitor-teardown-matrix/SKILL.md`.
- **Price, tiers, and the value metric.** Use `.claude/skills/monetization-pricing/SKILL.md`.
- **Campaigns and channel plans.** Use `.claude/skills/digital-marketing-campaigns/SKILL.md`.
- **Outreach, discovery calls, and objections.** Use `.claude/skills/founder-led-sales/SKILL.md`.
- **Market size and beachhead choice.** Use `.gemini/skills/market-sizing-decision-memo/SKILL.md`.
- **A one-page company summary.** Use `.codex/skills/startup-one-pager/SKILL.md`.

## Repo knowledge to consult first

- `.productmap/INDEX.md` for the map of the tree.
- `.productmap/00_company/product/value-proposition.md`: Target Customer, Customer Profile (Customer Jobs, Pains, Gains), Value Map (Products & Services, Pain Relievers, Gain Creators), Fit Assessment, Positioning Statement.
- `.productmap/01_strategy/segmentation/icp-b2b.md`: Attributes, Qualification Criteria, Disqualifiers, Buying Committee.
- `.productmap/01_strategy/segmentation/icp-b2c.md`: Attributes, Behavioral Signals, Jobs to Be Done.
- `.productmap/01_strategy/segmentation/segmentation.md` for which ICP file is in use.
- `.productmap/01_strategy/competitors/competitor-matrix.md`: Where we lead, Where we trail, Where it is unclear.
- `.productmap/01_strategy/business-model/business-model.md`: Lean Canvas blocks for Customer Segments, Unique Value Proposition, Channels, Revenue Streams, Unfair Advantage.
- `.productmap/06_data/interviews/`: read for verbatim phrases, workarounds, and money or time already spent.

One canvas covers one segment. If the ICP files describe two, ask which one this canvas is for, or draft both and compare.

## Customer profile with jobs, pains, and gains

Describe the customer before the product. Nothing in this half mentions your features.

**Jobs.** What the customer is trying to get done. Tag each one.

| Tag | Definition | Example |
|---|---|---|
| Functional | The task or outcome | Close the monthly books by day 3 |
| Emotional | How they want to feel, or stop feeling | Stop dreading the audit email |
| Social | How they want to be seen | Be the finance lead who is never the bottleneck |

Write jobs in the customer's verbs. "Manage" and "optimise" are your words. Theirs are in the transcripts.

**Pains.** What blocks or spoils the job. Rate intensity with the template's scale: High, Medium, Low.

| Intensity | Signs in the evidence |
|---|---|
| High | Happens weekly or more, costs named hours or money, and they already paid for or built a workaround |
| Medium | Happens regularly, they complain, they tolerate a free workaround |
| Low | Mentioned only when prompted, no action taken |

**Gains.** Outcomes they want. Rate importance with the template's scale: Must-have or Nice-to-have. A must-have gain is one whose absence stops the purchase.

Rules for the profile:

- Rank, then cut. Keep the top three to five in each list. A canvas with fifteen pains guides no decision.
- Each line carries a source: a quote and file path, or the word Assumption.
- Past behaviour outranks stated opinion. A workaround someone built is stronger than a pain someone agreed with.
- Buyer and user can differ in B2B. Note whose job, pain, or gain each line is.

## Value map

Now the product side. Every line points back to a specific line in the profile.

- **Products & Services.** What you offer today. Mark planned items as planned.
- **Pain Relievers.** Format: `<pain> → <how the product reduces it> → <by how much, if known>`.
- **Gain Creators.** Format: `<gain> → <how the product produces it>`.

Rules:

- One reliever names one pain. A reliever with no matching pain is a feature looking for a customer.
- Quantify where evidence exists: hours saved per week, errors avoided, days faster. Label estimates.
- A capability every alternative has is table stakes. Keep it in the product list and out of the differentiators.
- Features mapped to Low pains or Nice-to-have gains are candidates to cut or postpone.

## Fit assessment

Mark each ranked pain and gain against the value map.

| Verdict | Criteria |
|---|---|
| Strong | The product addresses it directly today, and at least one customer confirmed the result through behaviour or payment |
| Partial | Addressed with limits, by a planned feature, or supported by opinion only |
| None | Not addressed. Either a deliberate exclusion or a gap |

Decision rules:

- At least one High pain needs Strong fit. Without it, stop. The work is on the segment or the product, and positioning waits.
- A High pain with None fit is either the next item to build or proof you picked the wrong segment. Say which.
- Strong fit on Low pains only means a pleasant product nobody needs.
- Record deliberate exclusions under "No fit / out of scope". They protect the roadmap.

This is fit on paper. Fit in the market shows up later as retention and payment, tracked in `pmf-signals.md`.

## Positioning statement and the named alternative

Positioning answers "compared to what?". A statement with no alternative is a description.

`For <target customer> who <need or job>, <product> is a <category> that <key benefit>. Unlike <alternative>, we <differentiator>.`

| Slot | How to fill it | Common failure |
|---|---|---|
| For | The ICP in one phrase, narrow enough to exclude someone | "Teams", "businesses" |
| Who | The top job plus the High pain | A need the customer never voiced |
| Is a | A category the buyer already knows and budgets for | An invented category needing its own explanation |
| That | The outcome of the strongest fit line | A feature |
| Unlike | What they use today: a spreadsheet, a hire, an agency, an incumbent, or doing nothing | A rival the customer has never heard of |
| We | The difference the buyer cares about and you can prove | "Easier", "faster" with no number |

Choosing the alternative: ask what the customer would do if your product vanished tomorrow. The most frequent answer in the interviews is the alternative. Check it against `competitor-matrix.md`.

Then check consistency with the Lean Canvas in `business-model.md`:

| Check | Question | If it fails |
|---|---|---|
| Customer Segments | Does "for" match the early adopters listed? | Fix the canvas or the statement. One of them is out of date |
| Channels | Can the listed channels reach this customer? | Positioning for a buyer you can't reach is theory |
| Revenue Streams | Does the buyer in the statement hold the budget for this price? | Reposition to the budget holder or change the price |
| Unique Value Proposition | Does the canvas say the same benefit? | Rewrite the canvas line from the statement |
| Unfair Advantage | Does the differentiator rest on something hard to copy? | Mark the differentiator as temporary and plan the next one |

## Cheap validation tests

Turn the weakest assumptions into tests with a pass or fail line written in advance. The numbers below are illustrations. Set your own before the test starts.

| Assumption | Test | Example pass line | Effort |
|---|---|---|---|
| The top pain is High | 5 to 10 past-behaviour interviews in the segment | Most describe a recent episode and a paid or built workaround | 1 to 2 weeks |
| The message is understood | Show the headline for five seconds, ask them to say back what it is and who it is for | Most of ten people in the segment get both right | 2 days |
| The message beats another | Two outreach or ad variants to the same audience | The winner leads on replies or clicks by a margin you set beforehand | 1 week |
| The alternative is right | Ask five recent buyers or prospects what they used before | Your named alternative is the most frequent answer | 3 days |
| The differentiator matters | Open sales calls with it, log the reaction | It is repeated back or asked about in most calls | 2 weeks |
| Demand exists at this promise | Landing page with a real call to action | Conversion above the threshold set in the test card | 1 to 2 weeks |

Small samples give direction, never proof. Say so in the write-up.

## Workflow

1. **Read the repo.** Canvas, ICP files, matrix, Lean Canvas, the latest interviews.
2. **Ask no more than two things, together:** who the product is for and what it does for them. Skip both if the files answer them.
3. **Draft the full canvas at once.** Customer profile and value map, every guess marked Assumption.
4. **Refine the profile.** One weak line at a time. Replace assumptions with quotes and paths.
5. **Rework the value map.** Map each reliever and creator to a ranked line. Flag orphans.
6. **Assess fit.** Strong, partial, or none for each line. Apply the decision rules.
7. **Write the positioning statement.** Two or three variants with different alternatives or benefits. Pick one with the founder.
8. **Run the consistency check** against the Lean Canvas.
9. **Stress-test.** Voice the strongest objection a buyer and a competitor would raise. Adjust.
10. **Define validation tests** for the top three assumptions and add them to the Hypothesis Backlog.
11. **Write the clean canvas and statement** into `value-proposition.md`, with a ranked list of assumptions to validate next.

## Pitfalls

- **Starting from the product.** Filling the value map first bends the customer profile to fit it.
- **One canvas for two segments.** Their pains differ. The blend describes nobody.
- **Vague value.** "Saves time" without hours, person, and frequency.
- **Pains the founder feels and customers don't.** Check each one against a transcript.
- **Every pain marked High.** Ranking forces the trade-off the canvas exists to make.
- **Positioning against a strawman.** The real rival is often a spreadsheet or inertia.
- **An invented category.** You pay to explain it before you can sell in it.
- **Differentiators nobody buys on.** Technical elegance the buyer can't see.
- **A statement that contradicts the business model.** Promising enterprise outcomes at a self-serve price through a channel the buyer ignores.
- **Treating the canvas as finished.** Update it after each batch of interviews and each lost deal.

## Questions to ask the user

1. Which single segment is this canvas for?
2. What did the last three customers or prospects say they were trying to get done, in their words?
3. What do they do about it today? What does the workaround cost?
4. Which pain made someone pay, sign up, or take a second call?
5. If your product disappeared tomorrow, what would they use?
6. What can you do for this customer that the alternative can't? How would you prove it?
7. Who pays, and is it the same person who uses the product?
8. Which outcomes would stop a purchase if missing?
9. What do you deliberately leave unsolved?
10. Which category would the buyer file you under?
11. Which line of the canvas are you least sure about?
12. How many interviews back this up, and where are they saved?

## Artifact skeletons

**Value Proposition Canvas** (headings match `value-proposition.md`)

```markdown
## Target Customer
**Primary segment:** <ICP, with path>
**Persona / buyer:** <who feels the pain / who pays>
**Context / situation:** <when the job arises>

## Customer Profile
### Customer Jobs
- **Functional:** <job> (source: <path> / Assumption)
- **Emotional:** <job>
- **Social:** <job>
### Pains
- <pain> (intensity: High / Medium / Low; source)
### Gains
- <gain> (importance: Must-have / Nice-to-have; source)

## Value Map
### Products & Services
- <live or planned>
### Pain Relievers
- <pain> → <how relieved> → <measured or estimated effect>
### Gain Creators
- <gain> → <how created>
```

**Fit table**

```markdown
| Pain or gain | Rating | Addressed by | Fit (Strong / Partial / None) | Evidence or assumption | Action |
|---|---|---|---|---|---|
| | | | | | |
```

**Positioning block**

```markdown
## Positioning Statement
For **<target customer>** who **<need / job>**, **<product>** is a **<category>** that **<key benefit>**. Unlike **<alternative>**, we **<differentiator>**.

Alternative named because: <evidence, path>
Consistency with business model: segments <ok / gap>, channels <ok / gap>, revenue streams <ok / gap>
As of: YYYY-MM-DD
```

**Assumptions to validate next**

```markdown
| Rank | Assumption | Test | Pass line | Fail line | Owner | By (YYYY-MM-DD) |
|---|---|---|---|---|---|---|
| 1 | | | | | | |
```

## Storage conventions

- The canvas, fit assessment, and positioning statement live in `.productmap/00_company/product/value-proposition.md`. Fill the template in place and keep its headings.
- The same positioning statement appears in `.productmap/02_discovery/marketing/gtm-launch.md` and feeds the Value Proposition bullets in `.productmap/00_company/product/onepager.md`. Update them in the same edit, or note which file is behind.
- Validation tests go into the Hypothesis Backlog in `.productmap/02_discovery/experiments/experiments.md`.
- Interview notes stay in `.productmap/06_data/interviews/`. Cite them by file name.
- If the Lean Canvas disagrees with the new positioning, correct `.productmap/01_strategy/business-model/business-model.md` and set the block to Assumed.
- Date the positioning statement with an absolute date.

## Quality bar

- One segment per canvas, named and linked to an ICP file.
- Jobs are tagged, pains carry intensity, gains carry importance.
- Each list is ranked and cut to five or fewer.
- Every reliever and creator maps to a specific pain or gain.
- At least one High pain has Strong fit, or the output says positioning should wait.
- The positioning statement names the alternative customers use today.
- The statement passes the checks against segments, channels, and revenue streams.
- Every line is evidence with a path or an assumption with a test.
- The top three assumptions have tests with pass and fail lines.

## Related on Product Map

- Agent: **[Build unique value proposition](https://app.productmap.io/agents/value-proposition-positioning)** — nail your value proposition and positioning.
- Workflow: **[Market research to positioning](https://app.productmap.io/workflows/market-research-to-positioning)** — run market research, run competitor analysis, then build a unique value proposition.

More AI PM agents from Product Map: https://www.productmap.io/
