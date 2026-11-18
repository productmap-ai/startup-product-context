---
name: founder-led-sales
description: Use this skill when the user is a founder selling to the first customers, building a target list, writing outreach, running discovery calls, offering a pilot, handling objections, or deciding when to hire the first salesperson. Triggers — "first customers", "founder-led sales", "cold outreach", "who should I sell to first", "discovery call", "pilot offer", "how do I close", "handle objections", "first sales hire", "nobody replies to my emails".
---

# Founder-led sales — Claude skill

Use this skill to get a founder from an ICP on paper to the first paying customers: a narrowed target, a named list, outreach with a reason to reply, discovery calls built on past behaviour, a paid pilot, and a log of every objection. Read `.productmap/` first. The playbook file already holds the pipeline stages and call structure this skill fills in.

## When this skill applies

- The product can be shown or delivered by hand, and no one has paid yet.
- The ICP describes a broad market and the founder doesn't know whom to contact on Monday.
- Outreach goes out and replies don't come back.
- Calls happen, prospects are friendly, and nothing moves to a next step.
- Prospects ask for a free pilot and the founder has no offer ready.
- The same objection keeps ending deals.
- The founder has a handful of customers and wonders whether to hire a salesperson.

## When not to use this skill (hand off instead)

- **A structured design-partner programme with criteria and an agreement outline.** Use `.codex/skills/design-partner-program/SKILL.md`.
- **Setting list prices and tiers.** Use `.claude/skills/monetization-pricing/SKILL.md`. This skill covers the price conversation inside a deal.
- **The message and the named alternative are unclear.** Use `.claude/skills/value-proposition-positioning/SKILL.md`.
- **The problem is unproven and calls are pure discovery.** Use `.claude/skills/startup-idea-validation/SKILL.md`.
- **Marketing campaigns and content.** Use `.claude/skills/digital-marketing-campaigns/SKILL.md`.
- **Channel tests around a launch.** Use `.codex/skills/launch-channel-test-cards/SKILL.md`.
- **Growth loops and self-serve funnels.** Use `.claude/skills/growth-loops-engine/SKILL.md`.
- **Contract wording.** A lawyer's job. Track signed agreements in the contract register.

## Repo knowledge to consult first

- `.productmap/INDEX.md` for the map of the tree.
- `.productmap/02_discovery/growth-sales/founder-led-sales.md`: Target List & Outreach, Discovery Call Structure (30 min), Pipeline, Pricing Conversations, First 10 Customers.
- `.productmap/01_strategy/segmentation/icp-b2b.md`: Attributes, Qualification Criteria, Disqualifiers, Buying Committee.
- `.productmap/01_strategy/segmentation/icp-b2c.md`: Attributes, Behavioral Signals, Disqualifiers. Use it when the buyer is one person.
- `.productmap/01_strategy/segmentation/segmentation.md` for which ICP is the current beachhead.
- `.productmap/00_company/product/value-proposition.md`: the High pains and the Positioning Statement.
- `.productmap/02_discovery/user-research/interview-guide.md`: Ground Rules and the Question List for past-behaviour questions.
- `.productmap/06_data/interviews/`: earlier calls. Mine them for phrases, triggers, and people to go back to.
- `.productmap/00_company/team.md`: Advisors & Angels, for warm paths.

## Narrow the ICP for selling

An ICP for strategy can be a market. An ICP for selling is a list you can finish contacting in a month. Score candidate sub-segments from 1 to 5 on three factors.

| Factor | 5 looks like | 1 looks like | Where to find evidence |
|---|---|---|---|
| Pain urgency | It happened this month, it has a deadline or a cost attached, they already tried to fix it | They agree it is a problem when asked | Interviews, Pain Points in the ICP |
| Ability to pay | A budget line exists, the user can approve the price alone or with one sign-off | No budget, several approvals, procurement | Budget / ACV and Decision Makers |
| Reachability | You hold warm paths, or they gather in places you can enter | No shared contacts, gatekeepers, no public trail | Your network, communities, Where They Discover |

Multiply the three scores. Sell to the top sub-segment only until ten customers exist. Add a **trigger event** to the definition: new funding, a new hire in the role, a regulation deadline, a tool being retired. Triggers explain why this week.

Write the disqualifiers too. Saying no early saves the calls for buyers who can close.

## Target list and outreach

**The list.** Start with 50 to 100 named people at named companies. Fewer gives too little signal. More dilutes the personal work each message needs.

Order of approach, strongest path first:

1. Existing users, waitlist, and past interviewees who match the ICP.
2. Your own network and former colleagues.
3. Introductions from advisors, angels, and customers. Ask for a specific person by name.
4. Communities where the ICP already talks. Contribute first.
5. Cold email or direct message, with a trigger.

**The message.** Three parts, under 100 words:

- A first line only this person could receive: their trigger, their post, their situation.
- One line on the problem you work on, in words from the interviews.
- A small ask: 20 to 30 minutes to compare notes. No pitch, no deck attached.

Rules:

- Send in batches of 20 to 30. Change one element between batches: the segment, the trigger, or the first line.
- Follow up twice, a few days apart, each time adding something new. Then stop.
- Track sent, replied, and booked per batch. Reply rates vary widely by segment and channel, so compare batches against each other.
- Cold email is regulated: consent and opt-out rules differ by country. Check the rules for your market with a lawyer, and see `.productmap/05_operations/legal/privacy-compliance.md`.

## Discovery call and qualification

The playbook's 30-minute structure is the base: context, problem, fit check, show then ask, commitment. The call exists to learn whether a real, costly problem sits with someone who can buy.

Past-behaviour questions to keep at hand:

- "When did this last happen? Walk me through it."
- "What did you do about it? What did it cost?"
- "What have you tried or paid for? Why did you stop?"
- "Who else is involved when you buy a tool like this?"
- "What happens if nothing changes this quarter?"

Qualification after the call. Mark each line yes, no, or unknown.

| Criterion | Yes means |
|---|---|
| Pain | A recent, specific episode with a cost |
| Priority | It sits among their top problems this quarter |
| Alternative | They spend time or money on a workaround today |
| Buyer | You know who approves and have a path to them |
| Budget | Money exists or can be found at your price level |
| Timing | A date or trigger makes waiting costly |
| Next step | They agreed to a concrete action with a date |

Four or more yes answers including Pain and Next step: qualified. Fewer: ask for a referral, log what you learned, and move on. Demo only the part matching the problem they described.

## Pilot or paid-trial offer

A pilot is a time-boxed test with success criteria both sides agreed beforehand. Put it on one page.

| Element | Common practice |
|---|---|
| Scope | One team, one use case, the problem named in discovery |
| Duration | Two to eight weeks for most early B2B products. Long enough to see the result, short enough to keep attention |
| Success criteria | Two or three measurable outcomes, written by both sides before the start |
| Price | Paid, even at a reduced amount. Payment tests the buyer's intent and their purchasing process |
| What they give | A named owner, access to data and users, a weekly check-in |
| What happens after | The price and plan if criteria are met, agreed up front |
| Exit | Either side can stop. Say what happens to their data |

If the prospect insists on a free pilot, trade for something: a signed conversion clause, a case study, three introductions. A free pilot with no commitment tests nothing.

Have agreements reviewed by a lawyer before they are signed, and record them in the Contract Register in `.productmap/05_operations/legal/ip-and-contracts.md`.

## Objection log, closing, and when to hire

**Objection log.** Write down every objection, word for word, the same day.

| Type | Sounds like | First response to test |
|---|---|---|
| No pain | "We manage fine" | Ask about the last episode. If none, disqualify |
| Not now | "Maybe next quarter" | Ask what changes next quarter. Find the trigger or park the deal |
| Price | "Too expensive" | Ask "compared to what?" Return to the cost of the problem |
| Risk and trust | "You're too new for us" | Offer a pilot with an exit, a reference, your direct line |
| Authority | "I need to ask my boss" | Offer to join the conversation, or write the summary they will forward |
| Alternative | "We use X already" | Ask what X does poorly for them. If nothing, disqualify |

The same objection in three or more calls is a signal about the product, the segment, or the message. Take it to the value proposition or the roadmap.

**Closing.**

- Every call ends with a next step and a date, or with a clear no.
- Write a short mutual plan after a positive call: what each side does, by when, up to signature.
- Ask directly: "Are you ready to start on the first of the month?"
- Say the price once and wait. Founders talk themselves into discounts during the silence.
- Lower the price only in exchange for a commitment, as the playbook's Pricing Conversations section states.
- Log every closed-lost deal with the stated reason and your own read of the true one.

**When to stop selling as founder.** The playbook sets three conditions: ten or more paying customers closed with a repeatable pitch and pricing, a documented motion a new hire can follow, and founder time as the bottleneck where demand used to be. Until all three hold, a salesperson inherits an unsolved problem. The first hire is commonly someone who has sold at an early company and is comfortable without leads handed to them. Keep the founder on the largest deals after the hire.

## Workflow

1. **Read the repo.** ICP, value proposition, playbook, earlier calls.
2. **Narrow the ICP.** Score sub-segments on urgency, ability to pay, reachability. Pick one. Add a trigger and disqualifiers.
3. **Build the target list.** 50 to 100 names with the path to each.
4. **Draft outreach.** One template per path: warm introduction, community, cold. Personalise the first line per send.
5. **Send the first batch.** 20 to 30. Record replies and bookings.
6. **Prepare the call.** Adapt the 30-minute structure and choose five past-behaviour questions.
7. **Qualify after each call.** Fill the criteria. Save notes the same day.
8. **Offer a pilot** to qualified prospects, with success criteria and the price after it.
9. **Log objections and price reactions.** Review the pattern weekly.
10. **Review the pipeline weekly.** Counts per stage, stuck deals, next step and date for each.
11. **Update the playbook file** and the count toward ten customers.

## Pitfalls

- **Selling to everyone who answers.** Deals outside the ICP pull the product in ten directions.
- **Pitching in the first five minutes.** You lose the chance to hear the problem in their words.
- **Hypothetical questions.** "Would you buy this?" gets a polite yes.
- **Ending with "let's stay in touch".** No date means no deal.
- **Free pilots with no terms.** They run forever and convert rarely.
- **Talking only to the user.** The person who signs has different worries.
- **Mass outreach.** Hundreds of identical messages burn the segment and your sender reputation.
- **Not writing objections down.** Memory keeps the pleasant calls.
- **Discounting to end the silence.**
- **Hiring a salesperson to find the pitch.** The founder has to find it first.
- **Pipeline theatre.** Forty leads and no stage movement in three weeks means the list or the message is wrong.

## Questions to ask the user

1. Who are the last five people who showed real interest? What do they share?
2. Which sub-segment feels the pain this month, with a deadline or cost attached?
3. Who approves the purchase, and how do you reach them?
4. Which warm paths do you hold today?
5. What event makes a prospect ready to talk now?
6. How many messages went out last month, and how many replied?
7. What happened on your last three calls? How did each end?
8. Which objection do you hear most?
9. What price have you said aloud, and what was the reaction?
10. Can you deliver the outcome by hand for the first customers?
11. What would a successful pilot prove to the buyer?
12. How many paying customers exist today, as of which date?

## Artifact skeletons

**Target list**

```markdown
| # | Company | Contact and role | Trigger | Path (warm via <name> / community / cold) | Status | Next step | Date (YYYY-MM-DD) |
|---|---|---|---|---|---|---|---|
| 1 | | | | | Lead | | |
```

**Outreach template row** (columns from the playbook)

```markdown
| Template | Trigger / audience | Message (personalised opener + 1-line value + soft ask) |
|----------|--------------------|--------------------------------------------------------|
| Cold email | <trigger> | <first line about them>. I'm working on <problem in their words>. Could we compare notes for 20 minutes next week? |
```

**Call notes** (save per call)

```markdown
# <YYYY-MM-DD> <company or alias>
Segment / role:
Last episode of the problem (their words):
Current workaround and its cost:
Tried or paid for before:
Buying process and who approves:
Objections (verbatim):
Price said and reaction:
Qualification: pain / priority / alternative / buyer / budget / timing / next step
Commitment given or refused:
Follow-up owed, by date:
```

**Pilot offer**

```markdown
## Pilot: <customer> (start YYYY-MM-DD, end YYYY-MM-DD)
- Problem to solve:
- Scope: <team, use case>
- Success criteria: 1) 2) 3)
- Pilot price:
- Customer provides: <owner, access, weekly check-in>
- If criteria are met: <plan and price from YYYY-MM-DD>
- Exit and data handling:
- To review with a lawyer before signing: <open points>
```

**Objection log**

```markdown
| Date | Company | Objection (verbatim) | Type | Response tried | Outcome | Pattern count |
|---|---|---|---|---|---|---|
```

## Storage conventions

- The playbook is `.productmap/02_discovery/growth-sales/founder-led-sales.md`. Fill its sections in place: outreach templates, pipeline counts, the deal tracker, Pricing Conversations, and the count under First 10 Customers.
- The playbook has no objection section beyond a notes column. Add `## Objection Log` below Pricing Conversations and keep the table there.
- Call notes go to `.productmap/06_data/interviews/` as `YYYY-MM-DD-[name-or-alias].md`, following the interview guide.
- The narrowed ICP, trigger, and disqualifiers go back into `.productmap/01_strategy/segmentation/icp-b2b.md` or the B2C file.
- Signed pilots and customer agreements are listed in the Contract Register in `.productmap/05_operations/legal/ip-and-contracts.md`.
- Keep a long target list in a spreadsheet or CRM and note its location in `.productmap/00_company/resources.md`.
- Dates are absolute. Every next step has one.

## Quality bar

- One sub-segment is chosen, with scores, a trigger, and disqualifiers.
- The target list has named people and a path to each.
- Each outreach message has a first line specific to its recipient and a small ask.
- Discovery questions ask about past behaviour.
- Every prospect is marked against the qualification criteria after the call.
- The pilot has written success criteria, a price, and terms for what follows.
- Objections are logged verbatim with a count per pattern.
- Every open deal has a next step and a date.
- Claims about customers cite call notes, or are labeled assumption.
- The count toward ten paying customers is current and dated.

## Related on Product Map

- Agent: **[Define ICP and segments](https://app.productmap.io/agents/ideal-customer-profile-icp)** — clarify target customers and your positioning.

More AI PM agents from Product Map: https://www.productmap.io/
