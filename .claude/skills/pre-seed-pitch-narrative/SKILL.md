---
name: pre-seed-pitch-narrative
description: Use this skill when the user is shaping the story of a pre-seed or seed pitch before any slide design, needs a one-liner, a two-minute verbal pitch, or a bottom-up market-size note. Triggers — "pitch narrative", "tell my startup story", "one-liner for investors", "two-minute pitch", "elevator pitch", "review my pitch", "why now slide", "how do I explain traction", "market size for the deck".
---

# Pre-seed pitch narrative — Claude skill

Use this skill to work on the story an investor hears, before anyone opens a slide tool. You draft eight beats, a one-liner, a two-minute verbal version, and a bottom-up market-size note. Read `.productmap/` first so every sentence of the pitch rests on a file, a number, or a labeled assumption.

## When this skill applies

- A founder is preparing a first raise and the deck outline is empty or reads like a feature list.
- The pitch exists and investors keep asking "so what do you do?" after hearing it.
- The founder needs a one-liner for intros, application forms, and the title slide.
- A demo day, a partner call, or an accelerator interview needs a spoken version under two minutes.
- The market slide shows a large top-down number with no math behind it.
- Numbers in the deck disagree with the metrics file, the financial model, or the fundraising plan.

## When not to use this skill (hand off instead)

- **Whether to raise, how much, and on which instrument.** Use `.claude/skills/fundraising-strategy/SKILL.md`. The ask in the pitch copies its numbers.
- **Preparing for hard investor questions.** Use `.codex/skills/investor-qa-prep/SKILL.md` after the narrative holds.
- **Building and working the investor list.** Use `.codex/skills/investor-pipeline-tracker/SKILL.md`.
- **A full market-sizing memo with scenarios and sources.** Use `.gemini/skills/market-sizing-decision-memo/SKILL.md`. This skill writes the short note only.
- **The idea itself is unproven.** Use `.claude/skills/startup-idea-validation/SKILL.md`. A pitch can't cover a missing problem.
- **Monthly updates to existing investors.** Use `.gemini/skills/investor-update-memo/SKILL.md`.
- **Positioning against alternatives is unclear.** Use `.claude/skills/value-proposition-positioning/SKILL.md` first.
- **Slide layout, colours, and visuals.** Out of scope. Finish the words first.

## Repo knowledge to consult first

- `.productmap/INDEX.md` for the map of the tree.
- `.productmap/00_company/fundraising/pitch-deck.md`: the twelve-slide outline and the Deck Hygiene checklist. Your beats land in its blockquote placeholders.
- `.productmap/00_company/product/onepager.md`: One-line Summary and Target Users.
- `.productmap/00_company/product/product-vision.md`: The World We See (Why Now), Why We Win, Vision Statement.
- `.productmap/01_strategy/product-market-fit/pmf-signals.md`: Leading Indicators and Current Verdict. This is the honest ceiling on traction claims.
- `.productmap/03_analysis/kpis-metrics/metrics-tracking.md`: North Star Metric and the validation milestone table.
- `.productmap/01_strategy/competitors/competitor-matrix.md`: Where we lead, Where we trail.
- `.productmap/00_company/team.md`: Founders, Advisors & Angels.
- `.productmap/00_company/fundraising/fundraising-strategy.md`: Current Round, Use of Funds, Milestones This Raise Unlocks.
- `.productmap/06_data/interviews/` for customer quotes and one vivid episode.

Before drafting, build a claim ledger: every number you plan to say, its source path, its as-of date. A number with no source is an assumption or it stays out.

## The eight beats

Write the story in this order. Each beat answers one silent investor question in three sentences or fewer. The slide numbers refer to `pitch-deck.md`.

| # | Beat | The investor's silent question | What to say | Slide |
|---|---|---|---|---|
| 1 | Problem | Is this pain real and costly, and for whom? | One named type of person, one recent episode, one cost. A story an investor can picture or has lived. | 2 |
| 2 | Solution | What do you make, in plain words? | What the customer does with it and what changes for them. Show the product if it exists. | 3, 6 |
| 3 | Why now | Why didn't this exist five years ago? | One or two shifts in technology, regulation, cost, or behaviour, each with a date or a source. | 4 |
| 4 | Team | Why you? | Founder-problem fit: the earned insight, the years in the field, the build you already shipped. Skip the full CV. | 10 |
| 5 | Business model | Who pays, how much, and does it scale past the founders? | Who the buyer is, the price or price range tested, and one sentence on how revenue grows per customer. | 8 |
| 6 | Traction and validation | What have you proven so far? | The strongest two or three facts on a time axis, each labeled with its date. | 7 |
| 7 | Competition and differentiation | Do you know the alternatives, and why do you win? | The named alternatives including the status quo, and the one edge that lasts. | 9 |
| 8 | Ask and use of funds | What do you need, and what does it prove? | The amount, the instrument if decided, the runway it buys, and three milestones it reaches. | 11 |

The market note supports slide 5. The vision line closes on slide 12 and reuses the Vision Statement.

Rules for the arc:

- An investor remembers one or two points a day later. Decide which two before you write. Usually they are the insight behind the problem and the strongest proof.
- Emotion enters in beat 1. Urgency enters in beat 3. Data enters in beat 6. Keep them in those places.
- One idea per beat. If a beat needs a second paragraph, something belongs in the appendix.
- Order of telling can differ from slide order. For a spoken pitch, lead with whichever of team or traction is strongest.

## Traction ladder for pre-seed

Pre-seed traction is evidence of reduced risk. Present the highest rung you hold and say plainly which rung it is.

| Rung | Evidence | How to say it honestly |
|---|---|---|
| 1 | Discovery interviews | "We ran N interviews with [role]. X described [episode] in the last month." |
| 2 | Waitlist or signups | "N people signed up from [source] since YYYY-MM-DD." State the source. Bought traffic and a launch spike are different facts. |
| 3 | Active use and retention | "N weekly active users. X% of the [month] cohort is still active at week 4." |
| 4 | Commitments | "N signed letters of intent" or "N pilots scheduled." Keep pilots and customers in separate counts. |
| 5 | Revenue | "N paying customers at $X per month since YYYY-MM." |

- Show a trend with a time axis. A monthly series reads better than one cumulative total.
- Use rates and cohorts where you have them. Totals only go up and investors know it.
- If the Current Verdict in `pmf-signals.md` says "No signal" or "Weak signal", the pitch says so in its own words and leans on beats 1, 3, and 4.

## One-liner

The one-liner goes on the title slide, in intro emails, and in the first ten seconds of speech.

Pattern: `<Company> helps <specific customer> <do outcome> by <mechanism in plain words>.`

Tests:

- **The stranger test.** Someone outside the field repeats it back after five minutes.
- **The noun test.** It names a product a person can picture. "Platform", "solution", and "ecosystem" fail.
- **The scope test.** One customer, one outcome. A second "and" means two one-liners.
- **The analogy test.** "X for Y" works only when every investor knows X and the mapping holds under one follow-up question.

Write three variants: one led by the customer, one by the outcome, one by the mechanism. Read each aloud. Pick the version you can say without taking a breath.

## Bottom-up market-size note

Top-down numbers from reports prove a category exists. They say nothing about your reach. Build the note from units.

1. **Define the buyer.** Use the ICP: role, company type, geography.
2. **Count them.** Number of accounts or people matching the definition, with the source of the count.
3. **Price them.** Annual revenue per account, from tested prices or labeled as assumption.
4. **Multiply.** Buyers × annual price = the serviceable market for this product today.
5. **Bound the near term.** The share you can reach through your first channel in three years, with the reasoning.
6. **Name the expansion.** The next segment or product, as one sentence, to show how the market grows.

Reading the result:

- A credible small number with visible math earns more trust than a large one without it.
- Venture investors commonly look for a path to a company with $100M or more in annual revenue. This is a rule of thumb, and it varies by fund size. If your math lands far below it, say what expands the market or reconsider who you pitch.
- When bottom-up and top-down differ by more than two to three times, name the assumption causing the gap. Leave both numbers visible.

## Two-minute verbal version

Two minutes of speech is about 280 to 320 words. Write to the word count, then time it aloud.

| Segment | Seconds | Content |
|---|---|---|
| Opening | 10 | Name, company, one-liner |
| Problem | 25 | The person, the episode, the cost |
| Solution | 20 | What they do with the product, what changes |
| Why now | 15 | The shift, with a date |
| Proof | 25 | Two or three traction facts with dates |
| Team | 10 | The earned insight |
| Model and market | 10 | Who pays, how much, how many buyers |
| Ask | 5 | Amount, what it proves, and a clear close |

Cut competition from the spoken version unless asked. Keep one sentence ready for it.

## Workflow

1. **Read the repo and build the claim ledger.** Number, source path, date, evidence or assumption.
2. **Ask at most two questions** to fill gaps the files leave open. Then draft.
3. **Write three one-liner variants.** Run the four tests. Pick one with the founder.
4. **Draft the eight beats.** Three sentences each. Mark every claim.
5. **Choose the two points to remember.** Check both appear early and again in the ask.
6. **Check consistency.** The ask matches `fundraising-strategy.md`. Traction matches `metrics-tracking.md` and `pmf-signals.md`. Competition matches `competitor-matrix.md`.
7. **Write the market-size note.** Show the math and the sources.
8. **Run the cut pass.** Remove jargon, superlatives, and any sentence an investor has heard from ten other founders.
9. **Write the two-minute version.** Count words. Have the founder say it aloud and time it.
10. **Write into `pitch-deck.md`.** Fill each slide's placeholder. List the weakest beats and the evidence each one needs.

Coach one weak beat at a time. Say what is strong before you say what to fix. A founder who receives twenty edits acts on none.

## Pitfalls

- **Opening with the product.** The investor has no reason to care yet. Problem first.
- **"We have no competitors."** Investors hear it as "we haven't looked". Name the status quo and two alternatives.
- **Top-down market math.** "1% of a $50B market" shows no reach. Count buyers.
- **Vanity traction.** Page views, followers, and cumulative signups with no activity behind them.
- **Pilots described as customers.** Diligence finds it. Trust goes with it.
- **A team slide of CVs.** Logos say where you worked. The pitch needs the insight you earned there.
- **An ask with no milestones.** "$1M for 18 months" is a duration. Say what will be true at the end.
- **Jargon and category words.** If the sentence works for any startup, cut it.
- **Six points to remember.** The investor keeps none.
- **Different numbers in different places.** The deck says 40 users, the model says 55. Fix the source file, then the pitch.
- **Invented urgency.** "The round closes Friday" when it doesn't. Real momentum comes from real meetings.
- **Forecasts stated as facts.** Label projections. Statements to investors carry legal weight, so keep every claim accurate and confirm wording on terms with a lawyer.

## Questions to ask the user

1. Who is the investor audience: angels, pre-seed funds, an accelerator panel?
2. What is the format: a sent deck, a live pitch, a two-minute slot?
3. Which customer episode do you retell most often? What happened?
4. What have you proven since you started, and on which date?
5. What is your strongest single number today? Where is it recorded?
6. Why are you the people to solve this? What do you know from experience?
7. What changed in the world to make this possible now?
8. What do customers use today? Why do they stay with it?
9. Who pays, and what price have you tested?
10. How much are you raising, and which three milestones does it reach?
11. Which two points should an investor remember tomorrow?
12. Which question from investors do you dread?

## Artifact skeletons

**Narrative draft**

```markdown
# Pitch narrative: <company> (YYYY-MM-DD)

One-liner: <chosen variant>
Two points to remember: 1) <insight> 2) <proof>

## 1. Problem
## 2. Solution
## 3. Why now
## 4. Team
## 5. Business model
## 6. Traction and validation
## 7. Competition and differentiation
## 8. Ask and use of funds

## Weak beats and the evidence each needs
| Beat | Gap | Evidence to collect | By (YYYY-MM-DD) |
|---|---|---|---|
```

**Claim ledger**

```markdown
| Claim as spoken | Number | Source path or external source | As of (YYYY-MM-DD) | Evidence or assumption |
|---|---|---|---|---|
| | | | | |
```

**Market-size note**

```markdown
## Market size (bottom-up), as of YYYY-MM-DD
- Buyer definition: <role, company type, geography>
- Count: <N> (source: <path or URL, date>)
- Annual price per buyer: <$X> (evidence: <path> / assumption)
- Serviceable market: <N × $X>
- Reachable in 3 years via <channel>: <share and reasoning>
- Expansion: <next segment or product>
- Top-down cross-check: <figure, source> and the assumption behind any gap
```

**Two-minute script**

```markdown
[0:00] I'm <name>, founder of <company>. <One-liner>.
[0:10] <Problem: person, episode, cost>
[0:35] <Solution: what they do, what changes>
[0:55] <Why now>
[1:10] <Proof: two or three dated facts>
[1:35] <Team insight>
[1:45] <Who pays, how much, how many buyers>
[1:55] <Ask and close>
Word count: <n>
```

## Storage conventions

- The narrative lives in `.productmap/00_company/fundraising/pitch-deck.md`. Fill the blockquote placeholder under each slide heading and keep the headings unchanged.
- The one-liner is also the One-line Summary in `.productmap/00_company/product/onepager.md`. Change both in the same edit.
- The spoken script and claim ledger, if kept: `.productmap/00_company/fundraising/pitch-narrative-YYYY-MM-DD.md`.
- The ask copies `.productmap/00_company/fundraising/fundraising-strategy.md`. If they disagree, fix the strategy file first.
- Dates are absolute. Every traction number carries its as-of date.

## Quality bar

- A stranger can repeat the one-liner after five minutes.
- Each beat fits in three sentences and carries one idea.
- Every number has a source path and a date, or is labeled assumption.
- Traction is stated at its true rung, with pilots, signups, and customers kept apart.
- The market note shows the count, the price, and the multiplication.
- The alternative customers use today is named.
- The ask, the milestones, and the runway match `fundraising-strategy.md` exactly.
- The two-minute version runs under 320 words and was timed aloud.
- The summary lists the weakest beats and what evidence would fix each.

## Related on Product Map

- Agent: **[Prepare early stage pitch](https://app.productmap.io/agents/preseed-investor-pitch)** — turn notes into a script for an investor pitch deck.

More AI PM agents from Product Map: https://www.productmap.io/
