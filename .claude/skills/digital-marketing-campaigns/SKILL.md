---
name: digital-marketing-campaigns
description: Use this skill when the user is planning digital marketing for an early product, choosing channels, generating campaign ideas, writing messaging by segment, or building a 30-day content and campaign calendar. Triggers — "marketing plan", "campaign ideas", "which channels should we use", "content calendar", "marketing brief", "messaging for each segment", "4P marketing mix", "should we run ads", "how do we get the word out".
---

# Digital marketing campaigns — Claude skill

Use this skill to turn a product and a segment into a marketing plan a small team can run: a one-page brief, a marketing mix, an intent map, a channel shortlist, 10 to 15 ranked campaign ideas, messaging per segment, and a 30-day calendar. Read `.productmap/` first. Positioning and price are inputs here. This skill uses them and leaves their design to other skills.

## When this skill applies

- A founder asks how to get the product in front of the right people with little money.
- The team posts on several channels with no brief, no metric, and no stopping rule.
- A launch is done and regular marketing has to start.
- Someone proposes ads and nobody has checked whether the landing path converts.
- The founder needs campaign ideas tied to a segment and a metric.
- Two segments need different messages and currently get the same one.
- The next month needs a calendar with owners.

## When not to use this skill (hand off instead)

- **Positioning and the core promise are missing.** Use `.claude/skills/value-proposition-positioning/SKILL.md`. Until then, state the assumption you draft on.
- **Price and packaging.** Use `.claude/skills/monetization-pricing/SKILL.md`.
- **A first launch plan with channel test cards.** Use `.codex/skills/launch-channel-test-cards/SKILL.md`.
- **Landing page copy and a smoke test.** Use `.codex/skills/landing-page-smoke-test/SKILL.md`.
- **Funnel bottleneck, loops, and engine of growth.** Use `.claude/skills/growth-loops-engine/SKILL.md`.
- **A four-week experiment sprint.** Use `.codex/skills/growth-experiment-sprint/SKILL.md`.
- **One-to-one outreach and sales calls.** Use `.claude/skills/founder-led-sales/SKILL.md`.
- **Reading results 30 days after a launch.** Use `.gemini/skills/launch-retro-synthesis/SKILL.md`.

## Repo knowledge to consult first

- `.productmap/INDEX.md` for the map of the tree.
- `.productmap/02_discovery/marketing/marketing.md`: Key Artefacts and Early-Stage Focus (positioning, messaging, first channels). The plan is written here.
- `.productmap/02_discovery/marketing/gtm-launch.md`: Beachhead Segment, Positioning Statement, Channel Shortlist with statuses, Launch Goals. Its rule of two channels at once applies.
- `.productmap/00_company/product/value-proposition.md`: ranked pains and gains, the named alternative.
- `.productmap/01_strategy/segmentation/icp-b2b.md` and `.productmap/01_strategy/segmentation/icp-b2c.md`: who the segment is, where they discover tools, who decides.
- `.productmap/03_analysis/kpis-metrics/metrics-tracking.md`: North Star Metric and Events to Track, so campaigns measure events that exist.
- `.productmap/06_data/interviews/`: verbatim customer phrases for hooks and headlines.
- `.productmap/05_operations/legal/privacy-compliance.md`: cookie consent and data rules affecting tracking and email.

## One-page growth brief

Write the brief before any channel or idea. It starts from the business goal and works toward the channel. A plan starting from "we should be on TikTok" has no way to judge itself.

| Row | Content |
|---|---|
| Business goal | The outcome the company needs this quarter, such as ten paying customers |
| Marketing objective | What marketing contributes, such as 40 qualified conversations |
| Target segment | One segment from the ICP, with its trigger |
| Customer problem | In the customer's words, from an interview |
| Promise | The outcome you offer, from the positioning statement |
| Proof | What makes the promise believable: a result, a demo, a customer quote |
| Offer and call to action | What the person is asked to do next |
| Channel hypothesis | Where this segment pays attention, and why you believe it |
| Landing path | The page or product flow the click arrives at, through to the wow moment |
| Events to track | The events proving each step happened |
| Success metric | One downstream number: activated users, booked calls, paying customers |
| Guardrail metric | What must stay healthy: cost per result, unsubscribe rate, support load |
| Learning question | What you will know in 30 days |

Mark unknown rows `Assumption:` followed by your best guess. Any market size, benchmark, or cost figure without a source is marked `UNVERIFIED`.

## Marketing mix from 4P to 7P

The mix checks that the four parts tell one story. Product and price come from their own files. Record them here in a line each.

| P | Questions | Source |
|---|---|---|
| Product | Who needs it, for what problem, against which alternative, with what proof? | `value-proposition.md` |
| Price | Model, value metric, entry price, discount rules | `business-model.md` |
| Place | Where do people discover it, evaluate it, buy it, and use it? Include marketplaces, integrations, and surfaces inside the product | `gtm-launch.md` |
| Promotion | Which paid, earned, shared, and owned activities carry the message? | This plan |

Promotion by media type:

| Type | Examples | Early-stage note |
|---|---|---|
| Owned | Site, blog, email list, product notifications, docs | Start here. You control it and it accumulates |
| Shared | Social posts, communities, comments, partner co-posts | Founder voice works best. Give before asking |
| Earned | Press, podcasts, reviews, mentions, guest posts | Slow to start, strong for trust |
| Paid | Search ads, social ads, sponsorships, paid newsletters | After the landing path converts on unpaid traffic |

Extend to 7P when trust or experience decides the sale: services, marketplaces, high-priced B2B, health, finance, or anything touching sensitive data.

- **People.** Who the customer meets: founder, support, onboarding. Their response time is marketing.
- **Process.** The steps from interest to value: signup, onboarding, billing, cancellation.
- **Physical evidence.** The signs making an intangible product credible: case studies, security page, reviews, a public changelog.

Say in one line why the three were added or skipped.

## Intent mapping with See, Think, Do, Care

Sort audiences by intent, then match content and metric to each stage.

| Stage | Audience state | Content and format | Call to action | Metric |
|---|---|---|---|---|
| See | Fits the segment, not looking | Opinion posts, short video, stories from customers | Follow, read | Reach among the segment |
| Think | Aware of the problem, comparing options | Guides, comparison pages, calculators, templates | Subscribe, download, try the free tool | Engaged visits, signups to the list |
| Do | Ready to act | Landing page, demo, pricing, case study | Start trial, book a call, buy | Conversion to activation or payment |
| Care | Existing customers | Onboarding emails, tips, changelog, community | Use a feature, invite, review, refer | Retention, expansion, referrals |

Order of work for an early product: Do and Care first, since they sit closest to revenue and to people who already chose you. Then Think. See comes last and costs the most per result.

## Bullseye channel selection

A marketing type and a channel are different. Search engine optimisation is a type. Google organic results is a channel. Paid search is another type on the same engine. Name both.

1. **Brainstorm widely.** List 15 to 20 channels across owned, shared, earned, paid, and sales-assisted. Include ones you doubt.
2. **Shortlist.** Score each from 1 to 5 on audience fit, cost, speed to evidence, and confidence. Keep the top five or six.
3. **Test three.** Write a test brief for each. Run two at a time at most, per the rule in `gtm-launch.md`.
4. **Focus.** Put most of the effort into the one that works. Keep one small experiment alive beside it.

Channel test brief rows: who it targets, the promise and the offer, the channel, the budget in money and hours, the asset to produce, where the click lands, the metric that decides success, the metric that must not get worse, when to stop, what you expect to learn, and who owns it.

Judge a channel by what happens after the click: activation, retention, payback. A channel bringing cheap signups who never activate is a poor channel.

## Campaign ideas, messaging by segment, and the 30-day calendar

**Ideas.** Produce 10 to 15. Each carries a hook, a format, a call to action, and the metric it moves.

- Spread them across intent stages and media types.
- Prefer ideas only your product can produce: a template from your own workflow, a calculator, numbers from your usage data, a comparison page, a migration guide, an interactive demo, a customer's before-and-after.
- Rank by fit with the segment, cost, and speed to evidence. Name the top three to run first and say why.
- Outbound and stunt ideas are allowed. Deception, use of another company's trademark, and volume spam are excluded.

**Messaging by segment.** One row per segment or buyer role.

| Field | Source |
|---|---|
| Pain in their words | Verbatim from `06_data/interviews/` |
| Promise | Positioning statement |
| Proof | Result, quote, or demo |
| Likely objection | Objection log or interviews |
| Call to action | Matches their intent stage |

Test wording on a landing page or in outreach before spending on ads.

**30-day calendar.**

- Week 1: finish the brief, confirm tracking works, prepare assets for the top three ideas.
- Weeks 2 and 3: publish and run. Two or three pieces a week is sustainable for a founder. Reply to every response.
- Week 4: read results against success and guardrail metrics. Decide per idea and per channel: stop, change, or do more.

Each calendar row has a date, an owner, an asset, a channel, a call to action, and the metric.

Legal checks before publishing: claims you can prove, permission for customer names and quotes, consent for email and tracking. Rules differ by country. Confirm with a lawyer where unsure.

## Workflow

1. **Read the repo.** Positioning, ICP, channel shortlist, tracked events, interview phrases.
2. **Ask no more than two things, together:** who the product serves and what it does for them, and which business goal marketing has to move. Skip whatever the files already answer.
3. **Draft the growth brief** with assumptions labeled. End with two to four questions on the weakest rows.
4. **Fill the marketing mix.** Decide 4P or 7P and say why.
5. **Map intent stages.** Note which stages have content and which are empty.
6. **Run Bullseye.** Shortlist, pick three, write the test briefs.
7. **Generate 10 to 15 ideas.** Rank. Pick three.
8. **Write messaging per segment.**
9. **Build the 30-day calendar** with owners and dates.
10. **Set metrics.** Leading, lagging, and guardrails, tied to tracked events.
11. **Write into `marketing.md`.** List open assumptions and reference positioning and pricing by path.

Show the full updated draft after each change, then ask about one or two weak blocks.

## Pitfalls

- **Channels before segment and promise.** The channel list becomes the strategy.
- **A list with no test briefs.** Without a stopping rule, nothing ever stops.
- **Activity metrics alone.** Impressions, clicks, and followers tied to nothing downstream.
- **Paid before the path converts.** Ads multiply what the page already does, good or bad.
- **Generic content.** A post any company could publish earns no attention.
- **Skipping Care.** Existing customers are the cheapest source of retention and referrals.
- **Same message for every segment.**
- **Six channels at once.** A two-person team does none of them well.
- **Invented numbers.** Unsourced benchmarks and market sizes presented as facts.
- **A calendar no one owns.**
- **Treating separate channels as one experience.** Channels count as connected only when they share identity, consent, and customer state.

## Questions to ask the user

1. What business result does marketing have to support this quarter?
2. Which one segment comes first?
3. Where do those people spend attention, and how do you know?
4. What words did the last five customers use for their problem?
5. What proof do you hold today: results, quotes, a demo?
6. Where does a click land, and what share reach the wow moment?
7. Which channels have you tried, and what happened after the click?
8. How many hours and how much money per week can marketing use?
9. Who creates the content, and who replies to responses?
10. Which events are tracked today?
11. What can you publish from your product or data that nobody else can?
12. What would make you stop a channel?

## Artifact skeletons

**Growth brief**

```markdown
## Growth brief (YYYY-MM-DD)
- Business goal:
- Marketing objective:
- Target segment:
- Customer problem (their words, source):
- Promise:
- Proof:
- Offer and call to action:
- Channel hypothesis:
- Landing path:
- Events to track:
- Success metric:
- Guardrail metric:
- Learning question:
```

**Channel scoring and test brief**

```markdown
| Channel | Type | Intent stage | Audience fit (1-5) | Cost (1-5, 5 = cheap) | Speed to evidence (1-5) | Confidence (1-5) | Total | Pick |
|---|---|---|---|---|---|---|---|---|

### Test brief: <channel>
Audience / Promise / Offer / Budget (money, hours) / Asset to produce / Landing destination /
Deciding metric / Metric to protect / When to stop / What we expect to learn / Owner / Dates (YYYY-MM-DD to YYYY-MM-DD)
```

**Campaign idea backlog**

```markdown
| # | Idea | Segment | Intent stage | Media type | Hook | Format | Call to action | Metric it moves | Cost (L/M/H) | Speed (days/weeks/months) | Rank |
|---|---|---|---|---|---|---|---|---|---|---|---|
```

**Messaging by segment**

```markdown
| Segment or role | Pain in their words (source) | Promise | Proof | Likely objection | Call to action |
|---|---|---|---|---|---|
```

**30-day calendar**

```markdown
| Date (YYYY-MM-DD) | Asset | Channel | Segment | Call to action | Metric | Owner | Status |
|---|---|---|---|---|---|---|---|
```

## Storage conventions

- The plan goes in `.productmap/02_discovery/marketing/marketing.md`. The file is an overview with no plan sections yet. Add `## Growth brief`, `## Marketing mix`, `## Channel plan`, `## Campaign backlog`, `## Messaging by segment`, and `## 30-day calendar` below Early-Stage Focus.
- Channel statuses stay in the Channel Shortlist in `.productmap/02_discovery/marketing/gtm-launch.md`. Update a status only with a measured result.
- Channel tests are logged in the Hypothesis Backlog and Experiment Log in `.productmap/02_discovery/experiments/experiments.md`.
- New tracking events are added to `.productmap/03_analysis/kpis-metrics/metrics-tracking.md`.
- Campaign result exports go in `.productmap/06_data/analytics/` with dated file names.
- A dated monthly plan, if kept apart: `.productmap/02_discovery/marketing/campaign-plan-YYYY-MM.md`.
- Dates are absolute.

## Quality bar

- The brief starts from a business goal and names one segment.
- Positioning and price are cited by path and left unchanged.
- The mix states why it is 4P or 7P.
- Three channels have test briefs with a stopping rule. No more than two run at once.
- 10 to 15 ideas, each with hook, format, call to action, and metric, and a ranked top three.
- Messaging uses customer phrases with their source.
- Every success metric maps to a tracked event downstream of the click.
- Unsourced figures are marked `UNVERIFIED` or `Assumption:`.
- The calendar has dates and owners.

## Related on Product Map

- Agent: **[Create digital marketing ideas](https://app.productmap.io/agents/digital-product-marketing)** — pick channels and draft marketing campaigns.
- Workflow: **[GTM strategy to growth loops](https://app.productmap.io/workflows/gtm-strategy-to-growth-loops)** — prepare the go-to-market strategy, generate digital marketing ideas, then plan growth loops.

More AI PM agents from Product Map: https://www.productmap.io/
