---
name: fundraising-strategy
description: Use this skill when the user is deciding whether and when to raise money, how much to raise, which instrument and investor type fit, or how to run the process. Triggers — "should we raise", "how much should I raise", "SAFE or priced round", "round size", "how much dilution", "fundraising plan", "when to start fundraising", "which investors to target", "non-dilutive funding".
---

# Fundraising strategy — Claude skill

Use this skill to plan a first raise: whether to raise at all, when, how much, on which instrument, from whom, and through what process. Read `.productmap/` first. The round size comes from milestones and burn already recorded there, and the plan goes back into the fundraising file.

This skill gives considerations and common practice. It is no substitute for legal, tax, or financial advice. Confirm terms, documents, and cap table effects with a lawyer and an accountant before signing anything.

## When this skill applies

- A founder asks whether now is the time to raise, or whether to keep bootstrapping.
- The target amount is a round number with no milestones or burn math behind it.
- The founder is choosing between a SAFE, a convertible note, and a priced round and wants the trade-offs in plain words.
- Runway has dropped into a zone where a raise takes longer than the cash lasts.
- The investor list mixes angels, seed funds, and corporates with no fit criteria.
- A raise is under way and has stalled, with meetings spread across months.
- The founder wants to know how much of the company a round will cost.

## When not to use this skill (hand off instead)

- **The pitch story and one-liner.** Use `.claude/skills/pre-seed-pitch-narrative/SKILL.md`.
- **Tracking investors, statuses, and next actions.** Use `.codex/skills/investor-pipeline-tracker/SKILL.md`.
- **Rehearsing hard questions.** Use `.codex/skills/investor-qa-prep/SKILL.md`.
- **Burn, runway, scenarios, and cut triggers.** Use `.claude/skills/runway-burn-planning/SKILL.md`. This skill reads its output.
- **An 18 to 24 month model.** Use `.codex/skills/startup-financial-model/SKILL.md`.
- **Monthly investor updates.** Use `.gemini/skills/investor-update-memo/SKILL.md`.
- **Founder equity split and vesting.** Use `.claude/skills/cofounder-alignment/SKILL.md`.
- **Reviewing a term sheet or drafting documents.** A lawyer's job. This skill helps you prepare the questions.

## Repo knowledge to consult first

- `.productmap/INDEX.md` for the map of the tree.
- `.productmap/00_company/fundraising/fundraising-strategy.md`: Current Round, Why Raise Now, Use of Funds, Milestones This Raise Unlocks, Runway Math, Timeline & Process.
- `.productmap/00_company/fundraising/investor-pipeline.md`: Stage Definitions, Follow-up Cadence, Round Math.
- `.productmap/05_operations/finance/runway-burn.md`: Monthly Burn Table, Default Alive or Default Dead?, Runway Alert Thresholds.
- `.productmap/05_operations/finance/financial-model.md`: Cost Structure, 18–24 Month Projection, Scenarios, Key Assumptions Log.
- `.productmap/01_strategy/product-market-fit/pmf-signals.md`: Leading Indicators and Current Verdict.
- `.productmap/05_operations/legal/incorporation.md`: Cap Table Summary, for existing SAFEs, notes, and the option pool.
- `.productmap/00_company/team.md`: Advisors & Angels, for warm paths.

Burn and cash numbers stay in `runway-burn.md`. The strategy file refers to them. If the burn table is empty, fill it before sizing a round.

## Raise, wait, or skip

A raise is a tool to reach a milestone sooner. Start with the milestone.

| Situation | Lean | Reasoning |
|---|---|---|
| You can name what the money proves, and current runway can't prove it | Raise | The "Why Raise Now" answer writes itself |
| No evidence beyond the idea, and no track record | Wait or raise small from angels | Cheap validation first raises the price of every later share |
| Revenue covers costs, growth is steady, the market is not a land grab | Skip or delay | Dilution buys speed you don't need yet |
| Default dead with under 9 months of runway | Raise and cut in parallel | A raise commonly takes 3 to 6 months from first meeting to cash |
| The business will stay small and profitable | Skip venture money | Venture funds need outsized outcomes. Their terms assume one |
| You can't finish the sentence "this round gets us to..." | Wait | Investors will ask it in the first meeting |

Non-dilutive and low-dilution options to check before or beside a round:

- **Customer money.** Presales, annual prepayment, paid pilots, design-partner fees.
- **Grants and public programmes.** Research and innovation grants vary by country. Check eligibility, reporting duties, and IP conditions.
- **R&D tax relief.** Available in several jurisdictions. Ask an accountant what qualifies.
- **Revenue-based financing and venture debt.** Both need predictable revenue. Rarely a fit before it exists. Debt has to be repaid in bad months too.
- **Services revenue.** Funds learning, costs focus. Set an end date.
- **Accelerators.** Small cheques for equity plus a network. Compare the equity cost against what the programme opens for you.

## Round size from milestones

Work forward from milestones, then check against dilution. Never start from "what others raised".

1. **List the milestones the next round needs.** Three at most, each measurable. Ask target investors for the next stage what they would need to see.
2. **Cost the plan.** Monthly spend to reach those milestones: people, infrastructure, go-to-market tests. Use `financial-model.md`.
3. **Set the months.** Time to hit the milestones, plus about 6 months to run the next raise. The common target is 18 to 24 months of runway.
4. **Multiply.** Average monthly net burn over the period × months.
5. **Add a buffer.** 10 to 20% for slips. Plans run late more often than early.
6. **Subtract cash on hand and committed revenue.**

`Raise = (average monthly net burn × months of runway) × (1 + buffer) − current cash`

Then state a range: a minimum that still reaches the first milestone, a target, and a ceiling above which extra money only adds dilution. If the dilution check below fails at the target, cut scope or lengthen the path. A higher valuation is the last lever to pull.

## Instruments, described neutrally

| Instrument | What it is | Commonly used when | Terms to understand | Watch-outs |
|---|---|---|---|---|
| SAFE | A right to future equity, converting at a later priced round. No interest, no maturity date | Pre-seed and small seed rounds, rolling closes | Valuation cap, discount, post-money vs pre-money version, most-favoured-nation clause, pro rata side letter | Several SAFEs stack. Total dilution only shows at conversion |
| Convertible note | A loan converting to equity at a later round | Markets where SAFEs are less familiar, bridge rounds | Cap, discount, interest rate, maturity date, what happens at maturity | It is debt. Maturity can force a hard conversation |
| Priced round | Shares sold at a set price per share | A lead investor sets terms, usually seed and later | Pre-money and post-money valuation, option pool size and who bears it, liquidation preference, board seats, pro rata rights, protective provisions | Higher legal cost and more time. Terms beyond price matter for years |

Local equivalents exist, such as the ASA in the UK. Standard documents differ by country. Ask a lawyer which instrument investors in your market expect, and have every document reviewed before you sign.

## Dilution sanity check

Run the math before the first meeting. It takes ten minutes and prevents the most common regret.

- **Post-money SAFE.** Ownership sold ≈ amount ÷ post-money valuation cap. $500k on a $5M post-money cap is about 10%.
- **Stacked SAFEs.** Add the percentages. $500k at a $5M cap plus $500k at a $10M cap is about 15% before the next round.
- **Priced round.** Ownership sold = investment ÷ post-money valuation. Post-money = pre-money + investment.
- **Option pool.** A pool created or topped up before the round usually comes out of existing holders. A 10% pool plus a 20% round leaves founders near 70 to 72% of what they held.

Common practice, stated as a range and no rule: pre-seed and seed rounds each tend to sell 10 to 25% of the company, and many founders plan around 20%. Selling over 30% in a first round leaves little room for later rounds and can worry future investors about founder motivation.

Record the result per founder: ownership today, after this round, and after one assumed next round. Keep the authoritative cap table in a dedicated tool or spreadsheet. A lawyer or the cap table tool confirms the exact figures.

## Investors and process

**Types and what each is for**

| Type | Typical role at pre-seed | Fit check |
|---|---|---|
| Angels and operator angels | First cheques, advice, intros. Fast decisions | Do they know the field or the buyer? |
| Angel syndicates | Pooled small cheques behind one lead | Who leads, and how long does their process take? |
| Accelerators | Small cheque, programme, demo day | Is the network relevant to your customer and market? |
| Pre-seed and seed funds | Lead or co-lead, set terms, reserve for follow-on | Stage, sector, geography, cheque size, can they lead? |
| Strategic or corporate investors | Distribution or credibility | Do their rights limit selling to their competitors? |
| Family offices | Flexible cheques, variable pace | Have they made startup investments before? |

Fit criteria to score for every name: invests at your stage, writes your cheque size, covers your sector and geography, leads or follows, has no competing portfolio company, decides in weeks, and adds something specific beyond money. A name failing stage or cheque size leaves the list.

**Process in four phases**

1. **Prepare (2 to 4 weeks).** Narrative, deck, model, data room, a list of 50 or more qualified names with a warm path for each. Pre-seed conversion is low. Around one term sheet per ten first meetings is a common planning assumption, already noted in `investor-pipeline.md`.
2. **Batch.** Book first meetings into a 2 to 3 week window. Start with investors you care about less, to rehearse. Parallel conversations create real deadlines.
3. **Keep momentum.** Same-day follow-ups. Two nudges at most. Share progress made during the raise. Treat a soft circle as unconfirmed until documents are signed and money is wired.
4. **Close.** Agree terms, get legal review, sign, collect wires, update the cap table, tell everyone who passed that the round is done. Then go back to building.

**Milestones to open the next round**

Ask this in early meetings: "What would you need to see to lead our next round?" Write the answers down. Common seed-stage expectations include a retention signal in one segment, early revenue with a visible trend, and one acquisition channel that repeats. Treat these as patterns to verify with your target investors, since each fund sets its own bar.

## Workflow

1. **Read the repo.** Pull burn, cash, runway, the PMF verdict, existing SAFEs or notes, and the current round table.
2. **Decide raise, wait, or skip.** Use the table. Write the "Why Raise Now" answer in two or three sentences, or say plainly that it can't be written yet.
3. **List the milestones.** Three, measurable, with dates.
4. **Size the round.** Run the six steps. State minimum, target, and ceiling.
5. **Run the dilution check.** Per founder, including the option pool and any stacked SAFEs.
6. **Describe the instrument options.** Neutral trade-offs, the questions to take to a lawyer, no recommendation on legal terms.
7. **Define investor fit.** Types to approach, criteria, and types to skip.
8. **Plan the process.** Dates for prep, first conversations, first close, final close.
9. **Check non-dilutive options.** List any worth a week of effort.
10. **Write into `fundraising-strategy.md`.** Fill each section. List open questions for the lawyer and the accountant.

## Pitfalls

- **Picking the amount first.** The number should fall out of milestones and burn.
- **Twelve months of runway.** Six go to building and six to the next raise. Nothing gets proven.
- **Raising because peers are.** Their milestones differ from yours.
- **Stacking SAFEs without the math.** Each one looked small. Together they took a third of the company.
- **Optimising for valuation alone.** A high cap today sets a bar the next round has to clear.
- **A slow, serial process.** One investor at a time gives each of them all the time in the world.
- **Counting soft circles as cash.** Plan burn on wired money only.
- **Pitching funds at the wrong stage.** A fund leading Series A rounds will take the meeting and pass.
- **No lead.** Ten followers waiting for a lead is zero commitments.
- **Use of funds as accounting.** Investors read it as a plan. Tie each line to a milestone.
- **Skipping legal review to save money.** Side letters and unusual clauses cost far more later.
- **Ignoring customer money.** A paid pilot is funding and proof in one.

## Questions to ask the user

1. What will be true at the end of this round's runway, in three measurable milestones?
2. What can't you prove with the cash you have today?
3. What are current cash, net burn, and runway in months, as of which date?
4. Are you default alive at current growth and costs?
5. What SAFEs, notes, or options already exist?
6. How much of the company are you prepared to sell in this round?
7. Which hires or spend does the round fund, and from which month?
8. Who in your network can make warm introductions?
9. Which investor types fit your stage and market, and which have you ruled out?
10. Have you checked grants, tax relief, or customer prepayment?
11. Who is your lawyer for this round, and have they seen the instrument you plan to use?
12. What happens if the round takes twice as long or closes at the minimum?

## Artifact skeletons

**Round plan** (sections match `fundraising-strategy.md`)

```markdown
## Current Round
| Item | Value |
|------|-------|
| Stage | |
| Target raise | <minimum / target / ceiling> |
| Instrument | <option under consideration, to confirm with lawyer> |
| Valuation cap / terms | <or TBD> |
| Committed so far | <signed and wired only> |
| Target close | YYYY-MM |

## Why Raise Now
<what is proven, with source paths> / <what the capital proves next>

## Milestones This Raise Unlocks
| Milestone | Target | By when |
|-----------|--------|---------|
```

**Round-size calculation**

```markdown
| Input | Value | Source or assumption |
|---|---|---|
| Months to milestones | | |
| Months for next raise | 6 | common practice |
| Average monthly net burn over the period | | `financial-model.md` |
| Buffer | 10-20% | assumption |
| Cash on hand (YYYY-MM-DD) | | `runway-burn.md` |
| Raise = burn × months × (1 + buffer) − cash | | |
```

**Dilution table**

```markdown
| Holder | Today | After this round | After assumed next round | Notes |
|---|---|---|---|---|
| Founder 1 | | | | |
| Founder 2 | | | | |
| Option pool | | | | |
| Existing SAFEs / notes | | | | |
| New investors | | | | |
Assumptions: <cap or valuation, pool size>. To confirm with lawyer and cap table tool.
```

**Investor fit criteria**

```markdown
| Criterion | Must have / nice to have | How to check |
|---|---|---|
| Invests at our stage | Must | Recent first cheques |
| Cheque size <range> | Must | Stated on site or by partner |
| Sector and geography | Must | Portfolio |
| Can lead | <Must for N names> | Past rounds led |
| No competing portfolio company | Must | Portfolio |
```

## Storage conventions

- The plan lives in `.productmap/00_company/fundraising/fundraising-strategy.md`. Fill its sections in place.
- Investor names, statuses, and next steps go in `.productmap/00_company/fundraising/investor-pipeline.md`.
- Burn and cash stay in `.productmap/05_operations/finance/runway-burn.md`. Link to it. Don't copy the table.
- The cap table snapshot lives in `.productmap/05_operations/legal/incorporation.md` under Cap Table Summary.
- A dated dilution or round-size working, if kept: `.productmap/00_company/fundraising/round-sizing-YYYY-MM-DD.md`.
- Use absolute dates. Every cash figure carries its as-of date.

## Quality bar

- The "Why Raise Now" answer names what is proven and what the money proves next.
- The round size shows its inputs: milestones, months, burn, buffer, cash.
- Runway after the raise is 18 to 24 months, or the plan explains why a different figure is right.
- The dilution check covers every founder, the option pool, and existing SAFEs or notes.
- Instruments are described with trade-offs and no legal recommendation.
- Every figure is evidence with a path and a date, or an assumption with a way to test it.
- Use of funds ties each line to a milestone.
- The output lists the questions to take to a lawyer and an accountant.
- The ask matches the pitch deck.

## Related on Product Map

- Agent: **[Prepare early stage pitch](https://app.productmap.io/agents/preseed-investor-pitch)** — turn notes into a script for an investor pitch deck.

More AI PM agents from Product Map: https://www.productmap.io/
