---
name: startup-idea-validation
description: Use this skill when the user is stress-testing a startup idea before building, wants a sparring partner on the problem, the customer and the evidence, or needs to pick which assumption to test first. Triggers — "validate my idea", "is this idea any good", "poke holes in my startup", "riskiest assumption", "what should I test first", "do people have this problem", "why now", "idea stress test".
---

# Startup idea validation — Claude skill

Use this skill to act as a sparring partner for a founder who has an idea and thin proof. You run five challenges in order, grade every claim on an evidence ladder, rank the riskiest assumptions, and leave the founder with one test to run first. Read `.productmap/` before asking anything. The repo often holds the answer already.

## When this skill applies

- A founder describes an idea, a prototype, or a "people want this" claim and asks whether it holds up.
- The problem statement names a missing feature instead of a need, or names "everyone" as the customer.
- A batch of interviews came in and the assumptions need re-ranking.
- The founder has two or three ideas and wants to compare them on evidence, with excitement set aside.
- An experiment is planned and you need to check it tests the assumption that can kill the company.
- The team is about to write a backlog or a deck, and nobody has written down what would prove the idea wrong.

## When not to use this skill (hand off instead)

- **Writing the one-pager itself.** Use `.codex/skills/startup-one-pager/SKILL.md` once the stress test has produced answers.
- **Experiments have run and the question is pivot or continue.** Use `.gemini/skills/pivot-or-persevere-review/SKILL.md`.
- **Market size is the open question.** Use `.gemini/skills/market-sizing-decision-memo/SKILL.md`. This skill only checks the market logic is plausible.
- **Jobs, pains, gains, and a positioning statement.** Use `.claude/skills/value-proposition-positioning/SKILL.md`.
- **Building and running a landing page test.** Use `.codex/skills/landing-page-smoke-test/SKILL.md`.
- **Cutting an MVP backlog.** Use `.gemini/skills/mvp-scope-cut-review/SKILL.md` after the core claim is clear.
- **A scored competitor matrix.** Use `.gemini/skills/competitor-teardown-matrix/SKILL.md`.

## Repo knowledge to consult first

Read these before the first question. Note what is filled in, what still shows `[Fill in]`, and what contradicts another file.

- `.productmap/INDEX.md` for the map of the tree.
- `.productmap/00_company/product/onepager.md`: One-line Summary, Target Users, Value Proposition, Product Scope vs. Adjacent Tools.
- `.productmap/02_discovery/user-research/problem-framing.md`: the Problem Statement Template, including the field "How do we know this is real?".
- `.productmap/01_strategy/product-market-fit/opportunity-assessment.md`: the Opportunity Assessment Table, the confidence levels, and Decision Notes.
- `.productmap/02_discovery/experiments/experiments.md`: Hypothesis Backlog, Experiment Types, Experiment Log.
- `.productmap/01_strategy/business-model/business-model.md`: the Lean Canvas column "Validated / Assumed".
- `.productmap/02_discovery/user-research/interview-guide.md`: the ground rules for past-behaviour questions.
- `.productmap/06_data/interviews/`: transcripts and notes. Count them. Read the most recent five in full.

If the files are empty, say so and work from what the founder tells you. Label all of it as assumption until a source exists.

## The five challenges

Run them in this order. Each one depends on the one before. If a challenge fails, stop and fix it before moving on. A clever solution to an unproven problem is still unproven.

| # | Challenge | The question that needs a specific answer | A weak answer sounds like | A strong answer contains |
|---|---|---|---|---|
| 1 | Problem definition | What happened the last time this problem occurred, and what did it cost? | "It's annoying", "it's inefficient" | A recent episode, a frequency, a cost in hours or money, the workaround used today |
| 2 | Audience specificity | Which people exactly? Name five. | "SMBs", "creators", "anyone who..." | A role, a situation, a trigger event, and named people or companies you can reach this week |
| 3 | Solution-problem fit | Which step of the painful episode disappears with your product? | A feature list | One before-and-after walk-through of the same episode, and a reason the current workaround loses |
| 4 | Market dynamics and why now | What changed in the last two to three years to make this possible or urgent? | "The market is huge", "AI" | A named shift in technology, regulation, cost or behaviour, the alternatives customers use today, and a bottom-up count of buyers |
| 5 | Validation experiments | What result would make you drop this idea? | "We'll launch and see" | A hypothesis, a test, a sample, a deadline, and pass and fail numbers written before the test runs |

How to run a challenge:

- Ask one question at a time. Wait for the answer. Then ask the next.
- Offer a draft answer when the founder is stuck, marked as assumption, so they react to something concrete.
- Push on every vague noun. "Users" becomes "which users". "Saves time" becomes "how many hours, for whom, how often".
- Treat "doing nothing" and "a spreadsheet" as competitors. They are the usual alternative to a new product.
- End each challenge with a verdict: holds, holds with gaps, or fails. Name the gap.

## Evidence ladder

Grade every claim by the highest rung it reaches. Write the rung next to the claim.

| Rung | What counts | Example | Confidence level in `opportunity-assessment.md` |
|---|---|---|---|
| 1. Opinion | What someone says they would do, compliments, survey intent, your own belief | "I'd use it" | Low |
| 2. Past behaviour | What they already did about the problem | Built a spreadsheet, hired a contractor, tried two tools and quit | Medium |
| 3. Commitment | They gave up time, reputation or access | An intro to their boss, a second meeting with real data, a signed letter of intent, a pilot slot in the calendar | Medium to High |
| 4. Payment | Money moved | Presale, paid pilot, deposit, subscription | High |

Rules:

- Compliments count as zero. So does enthusiasm from friends, family and other founders.
- One story is an anecdote. Look for the same behaviour in at least five people from one narrow segment before calling it a pattern. Ten to fifteen interviews in one segment is a common point where new conversations stop adding new problems.
- Evidence expires. Note the date of each source. Re-check anything older than six months.
- Evidence from the wrong segment does not transfer. A paying enterprise customer says little about freelancers.
- A claim without a repo path or a named source is an assumption. Write it as one.

## Assumption map and risk ranking

List every belief the idea needs to be true. Sort them into five types, then score.

| Type | The belief | Typical first test |
|---|---|---|
| Problem | The pain exists, is frequent, and costs something | Past-behaviour interviews |
| Customer | A reachable group has it and can decide to buy | List 50 named targets, book 10 calls |
| Solution | Your approach removes the pain better than the workaround | Concierge or Wizard-of-Oz delivery |
| Payment | They will pay enough, soon enough | Presale, paid pilot, letter of intent |
| Reach | You can get in front of them at a cost you can carry | One channel test with a small budget |

Score each assumption on two scales from 1 to 5:

- **Impact if wrong.** 5 means the company has no reason to exist. 1 means a detail changes.
- **Evidence gap.** 5 means opinion only. 3 means past behaviour from a few people. 1 means payment from the target segment.

Risk = impact × evidence gap. Rank from highest to lowest. Then apply three tie-break rules:

1. Dependencies first. Test the problem before the solution, the solution before the price, the price before the channel.
2. Between two equal risks, the cheaper and faster test wins.
3. Test one assumption per experiment. A test with two mixed assumptions gives a result nobody can read.

Pick the top one. Park the others in the Hypothesis Backlog with status Planned.

## Choosing the first test

Match the test to the assumption. Use the experiment types already defined in `.productmap/02_discovery/experiments/experiments.md`.

| Riskiest assumption | Cheapest adequate test | Signal to set as pass or fail | Usual timebox |
|---|---|---|---|
| The problem is real and frequent | 10 to 15 interviews in one segment | Share who describe a recent episode and a workaround they spent time or money on | 2 weeks |
| This group wants this outcome | Landing page or smoke test with a real call to action | Conversion from targeted visitors to an email or a booked call | 1 to 2 weeks |
| The outcome is valuable | Concierge: deliver it by hand to 3 to 5 customers | They come back for a second round, or ask to keep going | 2 to 4 weeks |
| The solution works before code exists | Wizard-of-Oz | Task completed without help, repeat use | 2 to 4 weeks |
| They will pay | Presale or letter of intent | Number of signed commitments at the stated price | 2 to 3 weeks |

Rules for the test card:

- Write the pass number and the fail number before the test starts. Leave no room to reinterpret later.
- Define the sample: who counts, how many, from which source.
- Set an end date. A test with no end date becomes a hobby.
- Say what you will do on pass, on fail, and on a result in between.
- Tell participants the truth about availability. A waitlist is honest. A fake checkout asking for card details is deception.

## Workflow

1. **Read the repo.** Go through the files above. List what is stated with evidence, what is stated without, and what is missing.
2. **Restate the idea.** One sentence: who, what problem, what outcome. Fill the Problem Statement Template as a draft. Mark each field evidence or assumption.
3. **Run the five challenges in order.** One question at a time. Give a verdict per challenge. Stop at the first one to fail.
4. **Grade the evidence.** For every claim, record the rung, the source path, and the date.
5. **Build the assumption map.** Five types, two scores, one ranked list.
6. **Pick the first test.** Choose the experiment type, sample, timebox, pass and fail numbers. Get the founder to agree to the numbers before the test runs.
7. **Write the results into the repo.** Problem statement into `problem-framing.md`. Scored comparison into `opportunity-assessment.md`. Hypotheses into `experiments.md`.
8. **Set a review date.** Give an absolute date. On it, log the result and re-rank. If the top assumption is invalidated, hand off to the pivot-or-persevere review.

Keep the tone of a teammate at the same table. Challenge the claim, never the founder. Close every exchange with the one next action, never a task list.

## Pitfalls

- **Testing the solution before the problem.** A prototype demo gets polite praise. It says nothing about whether the pain exists.
- **Asking about the future.** "Would you use this?" produces rung 1 evidence. Ask what they did last time.
- **A segment you can't list.** If you can't name five real people in it, the segment is a guess.
- **Counting interest as demand.** Waitlist signups from a launch post are curiosity until someone commits time or money.
- **Friendly samples.** Friends, ex-colleagues and other founders are kind. Find strangers who have the problem.
- **Moving the goalposts.** Changing the pass number after the result arrives turns a test into a story.
- **Testing the easy assumption.** Founders pick tests they expect to pass. Pick the one whose failure would end the idea.
- **"No competitors."** Someone solves this today with a spreadsheet, an intern, or by living with it. Name the alternative.
- **Why now with no change behind it.** If the idea was equally possible five years ago, find out who tried and why it failed.
- **Ten assumptions at once.** A long test plan delays learning. One test, one deadline.
- **Stopping at a validated problem.** A real problem nobody pays to solve stays a research finding. Test payment early.

## Questions to ask the user

Ask one at a time. Skip any the repo already answers.

1. Who had this problem most recently, and what did they do about it on the day?
2. What does it cost them each time, in hours, money, or risk?
3. Which five people or companies would you call first? Why those?
4. What do they use today, including doing nothing? What would make them switch?
5. Which step of their current process disappears with your product?
6. What changed recently to make this possible or urgent now?
7. Who else has tried this? What happened to them?
8. How many buyers like this exist, counted from the bottom up, and what would each pay per year?
9. What is the strongest evidence you hold today? Which rung is it on?
10. Which single belief, if wrong, ends this idea?
11. What result in the next two weeks would make you stop?
12. How many interviews are saved in `.productmap/06_data/interviews/`, and from which segment?

## Artifact skeletons

**Idea stress-test summary**

```markdown
# Idea stress test: <idea name> (YYYY-MM-DD)

## Idea in one sentence
<who> has <problem> and gets <outcome> with <product>.

## Verdict per challenge
| # | Challenge | Verdict (holds / holds with gaps / fails) | Strongest evidence (rung, source path, date) | Gap |
|---|---|---|---|---|
| 1 | Problem definition | | | |
| 2 | Audience specificity | | | |
| 3 | Solution-problem fit | | | |
| 4 | Market dynamics and why now | | | |
| 5 | Validation experiments | | | |

## Riskiest assumption
<statement> | impact <1-5> | evidence gap <1-5> | risk <score> | why the others wait

## First test
Type, sample, start and end dates, pass number, fail number, action on each outcome.

## Open questions
- <unknown, and who can answer it>
```

**Assumption map**

```markdown
| # | Assumption | Type (problem / customer / solution / payment / reach) | Impact if wrong (1-5) | Evidence rung (1-4) and source | Evidence gap (1-5) | Risk | Test |
|---|---|---|---|---|---|---|---|
| 1 | | | | | | | |
```

**Hypothesis backlog row** (same columns as `experiments.md`)

```markdown
| # | Hypothesis | Riskiest Assumption | Experiment Type | Success Criterion | Status |
|---|-----------|---------------------|-----------------|-------------------|--------|
| 1 | We believe <segment> will <behaviour> because <reason> | <what must be true> | <Interviews / Landing page / Concierge / Wizard-of-Oz / Presale> | <pass number, fail number, by YYYY-MM-DD> | Planned |
```

**Problem statement** (fields from `problem-framing.md`)

```markdown
**Context:** <trigger that surfaces the problem>
**Who:** <segment, narrow enough to list>
**Goal:** <what they are trying to do>
**Problem:** <what gets in the way>
**Root Cause:** <why it exists>
**Impact:** <cost per occurrence, frequency>
**How do we know this is real?** <rung, quote, source path, date> or "Assumption, tested by hypothesis #<n>"
```

## Storage conventions

- Problem statement and How Might We questions: `.productmap/02_discovery/user-research/problem-framing.md`. Fill the template in place.
- Idea comparison and scores: the Opportunity Assessment Table and Decision Notes in `.productmap/01_strategy/product-market-fit/opportunity-assessment.md`. Set Evidence Level from the ladder.
- Hypotheses and results: Hypothesis Backlog and Experiment Log in `.productmap/02_discovery/experiments/experiments.md`. Order the backlog by risk.
- Flip Lean Canvas blocks from Assumed to Validated in `.productmap/01_strategy/business-model/business-model.md` only when rung 3 or 4 evidence exists.
- Interview notes: `.productmap/06_data/interviews/` as `YYYY-MM-DD-[name-or-alias].md`, per the interview guide.
- A full stress-test write-up, if the founder wants one kept: `.productmap/02_discovery/experiments/idea-stress-test-YYYY-MM-DD.md`.
- Use absolute dates everywhere. "Last week" means nothing in three months.

## Quality bar

- Every claim carries a label: evidence with a rung, a source path and a date, or assumption with a test.
- The customer is narrow enough for the founder to list named people.
- The alternative used today is named, including doing nothing.
- One riskiest assumption is chosen, with a reason the others wait.
- The first test has a sample, an end date, and pass and fail numbers written before it runs.
- No number is invented. Unknowns sit under Open questions.
- The repo files are updated, and the summary cites the paths it changed.
- The founder leaves with one next action and a date.

## Related on Product Map

- Agent: **[Validate startup idea](https://app.productmap.io/agents/startup-idea-validation)** — challenge your startup idea and shape vision.
- Workflow: **[Product idea to MVP scope](https://app.productmap.io/workflows/product-idea-to-mvp-scope)** — validate the product idea, define strategy and roadmap, then scope and challenge the MVP.

More AI PM agents from Product Map: https://www.productmap.io/
