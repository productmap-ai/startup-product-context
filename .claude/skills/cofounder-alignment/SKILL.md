---
name: cofounder-alignment
description: Use this skill when the user is aligning with co-founders on roles, decision rights, the equity split, vesting, time commitment, IP assignment, or what happens if a founder leaves or the founders disagree. Triggers — "co-founder agreement", "equity split", "who decides what", "founder vesting", "my co-founder and I disagree", "co-founder is part-time", "what if a founder leaves", "founder roles", "founder 1:1".
---

# Co-founder alignment — Claude skill

Use this skill to help founders talk through the topics that break founding teams, and to record what they agree: who owns what, how decisions and disagreements resolve, how equity is split and vested, how much time each commits, who owns the IP, and what happens in the hard scenarios. Read `.productmap/` first to see what is already agreed and what still shows a placeholder.

This skill structures a conversation and records its outcome. It is no substitute for legal or tax advice. Equity, vesting, IP, and leaver terms depend on jurisdiction. Have a lawyer draft or review every agreement, and ask a tax adviser about share purchases and elections.

## When this skill applies

- Two or three people are starting a company and nothing is written down.
- The founders are about to incorporate or take money and need the split and vesting settled.
- Decisions stall because nobody knows who has the final word.
- One founder works full-time and another part-time, and resentment is building.
- A new co-founder joins after the start.
- The founders disagree on direction, pace, or money and the same argument keeps returning.
- An investor asked about vesting, IP assignment, or what happens if a founder leaves.

## When not to use this skill (hand off instead)

- **Drafting or reviewing legal documents.** A lawyer's job. This skill produces the term outline the lawyer starts from.
- **Dilution from a funding round.** Use `.claude/skills/fundraising-strategy/SKILL.md`.
- **How founder salaries change runway.** Use `.claude/skills/runway-burn-planning/SKILL.md`.
- **Investor questions on the team.** Use `.codex/skills/investor-qa-prep/SKILL.md`.
- **A disagreement about pivoting.** Use `.gemini/skills/pivot-or-persevere-review/SKILL.md` to put evidence under the argument first.
- **Weekly priorities and numbers.** Use `.gemini/skills/founder-weekly-review/SKILL.md`. The founder 1:1 here covers the relationship.
- **A founder in distress, or a conflict already past repair.** Suggest a coach, a mediator, or a lawyer. Recording terms comes after.

## Repo knowledge to consult first

- `.productmap/INDEX.md` for the map of the tree.
- `.productmap/00_company/team.md`: Founders, Early Hires & Contractors, Advisors & Angels, Who Owns What, Ways of Working. Equity details stay out of this file by its own rule.
- `.productmap/05_operations/legal/founder-agreements.md`: Founder Equity Split, Vesting Terms, IP Assignment, ESOP Pool Status, What-If Notes, Open Items.
- `.productmap/05_operations/legal/incorporation.md`: Entity Status, Cap Table Summary, Key Documents Checklist.
- `.productmap/05_operations/legal/ip-and-contracts.md`: IP Ownership Checklist.
- `.productmap/00_company/fundraising/fundraising-strategy.md`, if a round is planned, since investors will review founder terms.

Note which rows are filled, which show `[Fill in]`, and where two files disagree. A team table saying "Agreed" beside an empty equity table is the first finding.

## Roles and decision rights

**One owner per area.** The Who Owns What table in `team.md` lists five areas: product and roadmap, engineering and infrastructure, customer conversations and sales, fundraising and investor relations, finance, legal and admin. Each gets one name. Shared ownership means nobody decides.

**Three kinds of decision.** Sort decisions before the next disagreement arrives.

| Kind | Who decides | Examples |
|---|---|---|
| Owner decides | The area owner, after hearing others | Feature order, tooling, a sales pitch, a contractor under an agreed budget |
| Consult, then owner decides | The owner, after a set discussion with the co-founders | A first hire in the area, a pricing change, a large customer commitment |
| Joint | All founders, or the board once one exists | Fundraising terms, selling the company, pivots, founder pay, issuing equity, hiring or removing an executive, spending above an agreed amount |

Set the spending threshold as a number. Write the joint list down. Everything outside it belongs to an owner.

**How disagreements resolve.** Agree the steps in calm weather.

1. Each founder writes their position and the evidence for it in half a page.
2. They discuss it once, with a time limit.
3. If it sits in one area, the owner decides. The others commit to the decision and say so.
4. If it is joint and still split, the agreed tie-break applies.
5. The decision and its reasoning are logged with a date, and a review date if it is reversible.

**Tie-breaks for an even split.** Options founders commonly choose: the CEO holds the final word on company-level matters, a named adviser or independent board member casts the deciding view, or the matter waits a fixed period before a final vote. Fifty-fifty teams with no tie-break can freeze the company. Whatever you choose, a lawyer should check how it fits your shareholder documents.

## The equity-split conversation

Have this conversation early and in one sitting. Postponing it raises the price.

**Factors to put on the table.**

| Factor | Questions |
|---|---|
| Contribution to date | Who originated the idea, built what exists, brought customers, or put in cash? |
| Commitment ahead | Who is full-time from which date? Who carries which role for the next four years? |
| Risk taken | Who left a salary, who invests savings, who has dependants relying on this? |
| Scarcity of role | Is one founder's skill hard to replace for this company? |
| Opportunity cost | What is each giving up to do this? |

**Two common approaches,** described neutrally.

- **Equal split.** Signals partnership and avoids a negotiation about worth. It suits founders who start together, full-time, with comparable commitment. It can sit badly when contributions or commitment are plainly unequal.
- **Weighted split.** Reflects different contribution, commitment, or risk. It needs an honest discussion and a rationale each founder can repeat a year later without bitterness.

Most of a company's value is created after the split is set. Weight future commitment over past contribution, and let vesting carry the risk of a founder leaving.

**Process.**

1. Each founder writes, alone, the split they consider fair and three reasons.
2. Compare. Talk about the reasons before the numbers.
3. Agree the split and write the rationale per founder in the Rationale column of the Founder Equity Split table.
4. Agree what would reopen the split: a change from full-time to part-time, a role change, a founder joining late.
5. Take the outcome to a lawyer. Share issuance and purchase have tax effects, so ask a tax adviser before signing.

## Vesting, cliffs, and IP as common practice

**Vesting.** Founders earn their shares over time, so a founder who leaves early doesn't keep a full stake. The standard reference in `founder-agreements.md` is four years with a one-year cliff: nothing vests before month 12, then it vests monthly. Investors commonly expect it.

| Term | What it means | To decide |
|---|---|---|
| Vesting start date | When the clock begins | Incorporation date, or earlier to credit work already done |
| Cliff | Period before the first shares vest | Usually 12 months. Founders with a long history together sometimes shorten it |
| Acceleration, single trigger | Vesting speeds up on one event, such as a sale of the company | Buyers and investors often resist it |
| Acceleration, double trigger | Vesting speeds up on a sale followed by termination without cause | More widely accepted |
| Leaver terms | What happens to unvested and vested shares when a founder goes | Buyback right, price, and whether the reason for leaving changes them |

Mechanics differ by country. In the US, founders buying restricted stock usually consider an 83(b) election, due within 30 days of the purchase, as the checklist in `incorporation.md` notes. Missing it can be costly and can't be fixed later. Other countries use other mechanisms. Confirm all of this with a lawyer and a tax adviser.

**IP assignment.** The company has to own what the founders make for it.

- Every founder signs an assignment covering work done before incorporation as well as after.
- Check prior employers. An employment contract can claim inventions made during employment, on employer time, or with employer equipment. Raise any doubt with a lawyer before it reaches diligence.
- Contractors and early helpers sign assignments too. Track them in the IP Ownership Checklist in `ip-and-contracts.md`.
- Domains, code hosting, cloud accounts, and app store accounts belong to the company, with more than one founder holding access.

**Option pool.** Record its planned size and status in ESOP Pool Status. A pool dilutes all founders, so agree it together.

## Time commitment and money

Unequal commitment is the most frequent source of founder resentment. Make it explicit.

- **Full-time date.** For each founder, the date they are or will be full-time. A condition such as "after funding" needs a deadline too.
- **Outside work.** Which side projects, consulting, or board seats are fine, and which need agreement.
- **Founder pay.** Current pay, the trigger for raising it, and whether unpaid months are owed back. Deferred pay can create a liability, so ask an accountant.
- **Personal runway.** How many months each founder can live on current pay. The shortest answer sets a real deadline for the company.
- **Money put in.** Whether founder cash is a loan, an investment, or a gift to the company. Each has different tax and legal effects. Ask an accountant.
- **Location and hours.** Time zones, overlap hours, expected response time.
- **Time off.** How holidays, illness, and parental leave are handled. Agree it before it is needed.

Part-time founders: common practice ties their vesting or share to the commitment and sets a date by which they go full-time or the terms are revisited.

## What-if scenarios and working norms

Answer each scenario together and record the answer. `founder-agreements.md` lists the first three under What-If Notes. Add the others.

| Scenario | Questions to settle |
|---|---|
| A founder leaves before the cliff | Do all shares return? What happens to IP, accounts, and announcements? |
| A founder leaves after partial vesting | Who can buy back vested shares, at what price, within what period? |
| Deadlock between founders | Which tie-break applies, and how long before it is used? |
| An acquisition offer arrives | What price would each accept today? Who negotiates? What if one wants to sell and one doesn't? |
| A founder underperforms in their role | How is it raised? Who decides a role change? |
| The CEO role should change hands | What triggers the conversation, and who has a say? |
| A founder can't work for months | What happens to pay, vesting, and decisions? |
| A new co-founder joins | From which pool do their shares come, on what vesting? |
| The company runs out of money | Who decides to stop, and how are remaining obligations handled? |

**Working norms.** Keep them few and real. `team.md` holds them under Ways of Working.

- **Founder 1:1.** Weekly, 30 minutes, founders only. It covers the relationship and leaves status for other meetings. A simple agenda: how each is doing, what is working between you, what is bothering you, one request each.
- **Feedback.** Direct, private, soon after the event, about behaviour and its effect.
- **Disagreement in front of the team.** Decide whether you debate openly or settle it first.
- **Decision log.** Joint decisions are written with a date, in the repo.
- **Review.** Revisit roles, commitment, and this agreement every six months, and after any funding round or role change.

Early warning signs worth naming in the 1:1: decisions being reopened, one founder routing around the other, score-keeping about hours, long silences on hard topics.

## Workflow

1. **Read the repo.** List what is filled, what is blank, and what conflicts.
2. **Ask who is in the conversation.** If only one founder is present, prepare them for the joint talk. Never record an agreement the other founders haven't seen.
3. **Separate preparation.** Each founder answers the questionnaire alone, in writing.
4. **Compare answers.** Mark matches and gaps. Start the discussion with the largest gap.
5. **Roles and decision rights.** One owner per area, the joint list, the spending threshold, the tie-break.
6. **Equity and vesting.** Run the split conversation. Record split, rationale, vesting, cliff, start dates, acceleration.
7. **Commitment and money.** Full-time dates, pay, outside work, personal runway.
8. **IP.** Check assignments and prior-employer exposure.
9. **What-if scenarios.** Answer each in one or two sentences.
10. **Working norms.** Set the founder 1:1 and the review date.
11. **Write into the repo.** `team.md` for roles and norms, `founder-agreements.md` for equity, vesting, IP, and what-ifs. List open items for the lawyer and the tax adviser with owners and dates.

Stay neutral between founders. Describe options and trade-offs. Leave the choice to them.

## Pitfalls

- **Splitting in the first week and never revisiting.** Fine with vesting, dangerous without it.
- **No vesting between friends.** The friendship is the reason to have it.
- **A handshake split.** Memories diverge within a year.
- **Titles without decision rights.** Two people each believe they have the last word.
- **Fifty-fifty with no tie-break.**
- **Avoiding the commitment talk.** The part-time founder and the full-time founder each assume the other understands.
- **IP left with a founder or a past employer.** It surfaces in diligence at the worst moment.
- **Founder pay never discussed.** One founder can go a year unpaid. The other can't.
- **Treating the founder 1:1 as a status meeting.** Hard topics never find a slot.
- **Using a template agreement unread.** Clauses from another country or another situation bind you anyway.
- **Asking an AI or a blog to settle legal terms.** Take the outline to a lawyer.

## Questions to ask the user

Each founder answers separately first.

1. Why are you doing this company, and what would make you stop?
2. Which areas do you want to own? Which do you want to stay out of?
3. Which decisions do you expect to make alone, and which together?
4. When you disagree and neither moves, what should happen?
5. What split feels fair to you, and what are your three reasons?
6. When are you full-time, and what else are you working on?
7. How long can you go on current pay?
8. Did you create anything for this company while employed elsewhere?
9. What happens to your shares if you leave in month 8? In year 3?
10. At what price would you sell the company today?
11. What does your co-founder do that frustrates you, and have you said it?
12. What should the two of you review in six months?

## Artifact skeletons

**Founder alignment record**

```markdown
# Founder alignment (YYYY-MM-DD)
Present: <names>. Next review: YYYY-MM-DD.

## Roles and decision rights
| Area | Owner |
|------|-------|
| Product & roadmap | |
| Engineering & infra | |
| Customer conversations & sales | |
| Fundraising & investor relations | |
| Finance, legal & admin | |

Joint decisions: <list>
Spending threshold for joint approval: <amount>
Tie-break: <mechanism> (to confirm with lawyer)

## Commitment and money
| Founder | Full-time from (YYYY-MM-DD) | Outside work agreed | Current pay | Pay trigger | Personal runway (months) |
|---|---|---|---|---|---|

## Open items for lawyer / tax adviser
| Item | Owner | Due | Status |
|------|-------|-----|--------|
```

**Equity and vesting** (tables match `founder-agreements.md`)

```markdown
| Founder | Role | Equity % | Rationale |
|---------|------|----------|-----------|

| Founder | Vesting Schedule | Start Date | Cliff | Acceleration Terms |
|---------|------------------|------------|-------|--------------------|

Reopen the split if: <conditions>
Status: discussed YYYY-MM-DD / reviewed by lawyer YYYY-MM-DD / signed YYYY-MM-DD
```

**What-if notes**

```markdown
- **A founder leaves before the cliff:** <agreed answer>
- **A founder leaves after partial vesting:** <buyback right, price basis>
- **Deadlock between founders:** <tie-break, waiting period>
- **Acquisition offer:** <who negotiates, how a split view resolves>
- **A founder can't work for months:** <pay, vesting, decisions>
- **A new co-founder joins:** <source of shares, vesting>
```

**Founder 1:1 agenda**

```markdown
Weekly, 30 min, founders only.
1. How are you, outside the task list?
2. What worked between us this week?
3. What bothered you? (behaviour and effect)
4. One request each.
5. Anything to add to the decision log?
```

## Storage conventions

- Roles, owners, and working norms go in `.productmap/00_company/team.md`: the Founders table, Who Owns What, and Ways of Working. Note equity status there in a few words and keep the numbers out.
- The joint-decision list and spending threshold have no section in `team.md`. Add them under Who Owns What.
- Equity split, vesting, IP assignment, option pool, and what-if answers go in `.productmap/05_operations/legal/founder-agreements.md`. The template's What-If Notes cover three scenarios. Add bullets for the others.
- Lawyer and tax follow-ups go in Open Items in the same file, each with an owner and a due date.
- Signed documents live in the legal vault listed in `.productmap/00_company/resources.md`. Record their status in the Key Documents Checklist in `.productmap/05_operations/legal/incorporation.md`.
- A dated record of the conversation, if kept: `.productmap/05_operations/legal/founder-alignment-YYYY-MM-DD.md`.
- Mark each entry as discussed, reviewed by a lawyer, or signed, with an absolute date. Keep personal financial details out if the repo is shared.

## Quality bar

- Every area has one owner, and the joint-decision list is written.
- A tie-break exists for an even split.
- The equity split has a rationale per founder and conditions for reopening it.
- Vesting schedule, start date, cliff, and acceleration are recorded per founder.
- Each founder's full-time date and pay arrangement are stated.
- IP assignment status is checked, including work done before incorporation and prior-employer exposure.
- Each what-if scenario has an agreed answer or sits in Open Items.
- A founder 1:1 slot and a six-month review date are set.
- Every entry is marked as agreed fact or open question. Nothing is recorded on behalf of an absent founder.
- The output lists what to take to a lawyer and a tax adviser, and says plainly it is no legal advice.

## Related on Product Map

- Agent: **[Enable team collaboration](https://app.productmap.io/agents/team-collaboration-leadership)** — improve how teams lead and communicate.

More AI PM agents from Product Map: https://www.productmap.io/
