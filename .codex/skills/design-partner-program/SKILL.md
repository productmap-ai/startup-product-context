---
name: design-partner-program
description: Design a design-partner program with partner criteria from the ICP, a target number, the two-way offer, an agreement outline, a recruiting message, onboarding, success criteria, a path to paid, and exit rules.
---

# Design partner program — Skill

## Name

`design-partner-program` — Recruit a small group of ICP-fit customers to build with, and agree up front what each side gives, how success is measured, and how the pilot turns into a paid contract.

## When to use

- You sell to companies, the product is early, and you need real usage and feedback before a wider launch.
- A prospect offered to "try it and give feedback" and you want that to be a commitment with an end date.
- Earlier pilots ran for months with no decision and no payment.
- Partners keep asking for custom features and you need a rule for what gets built.
- You need the first reference customers and case studies for sales and fundraising.
- Use a sibling skill instead when the ICP or the outreach motion is undefined (`.claude/skills/founder-led-sales/SKILL.md`), or you're testing demand before any product exists (`.codex/skills/landing-page-smoke-test/SKILL.md`).

## Inputs (ask user for these)

- Product name:
- Artifact date (YYYY-MM-DD) (use today's date unless the founder gives another):
- Target segment and the ICP file to use:
- What the product does today, and what is missing:
- What you need to learn from partners (3 to 5 questions):
- Founder hours per week available for partners:
- Planned pilot length and start date (`YYYY-MM-DD`):
- Pilot price (free / discounted / paid) and the planned price after the pilot:
- Data the product touches at a partner (personal data, confidential business data):
- Prospects already interested (company, contact, how you know them):
- What you can offer partners (roadmap input, price lock, direct founder access, setup help):
- What you want back (feedback calls, usage, a reference, a case study, a logo):

## Outputs

- Design partner program (Markdown) containing:
  - Program goal and learning questions
  - Partner criteria and disqualifiers, drawn from the ICP
  - Target number of partners and the capacity math behind it
  - The offer: what partners get, what they give
  - Agreement outline (topics and choices, not legal text)
  - Recruiting message and a qualification call outline
  - Onboarding plan and feedback cadence
  - Success criteria per partner and for the program
  - Path to paid, feature-request rule, and exit rules
  - Partner tracker
- Where to store it:
  - `.productmap/02_discovery/growth-sales/founder-led-sales.md`, as a new section `Design Partner Program` below `Pricing Conversations`, with partners added to the deal tracker table in `Pipeline`
  - Signed agreements: the `Contract Register` in `.productmap/05_operations/legal/ip-and-contracts.md`
  - Call notes: `.productmap/06_data/interviews/`

## Repo knowledge to pull

- Start here: `.productmap/INDEX.md`
- Target file: `.productmap/02_discovery/growth-sales/founder-led-sales.md` (outreach templates, discovery call structure, pipeline, pricing conversations)
- Criteria: `.productmap/01_strategy/segmentation/icp-b2b.md` (`Qualification Criteria`, `Disqualifiers (B2B)`, `Buying Committee (optional)`), `.productmap/01_strategy/segmentation/segmentation.md`
- Value to promise: `.productmap/00_company/product/value-proposition.md`
- Price after the pilot: `.productmap/01_strategy/business-model/business-model.md`
- What to learn: `.productmap/02_discovery/experiments/experiments.md`, `.productmap/01_strategy/mvp-roadmap/roadmap.md`
- Questions for calls: `.productmap/02_discovery/user-research/interview-guide.md`
- Data and contracts: `.productmap/05_operations/legal/privacy-compliance.md`, `.productmap/05_operations/legal/ip-and-contracts.md`

## Detailed prompt (copy/paste)

```
You are an advisor to a B2B founder closing first customers. Design a design-partner program for the product below: who qualifies, what each side commits to, how success is measured, and how a pilot becomes a paid contract or ends. Read the repo first and cite every path you used.

Repo-first context to consult:
- Start at: .productmap/INDEX.md
- Read and keep the headings of: .productmap/02_discovery/growth-sales/founder-led-sales.md
- Read: icp-b2b.md, segmentation.md, value-proposition.md, business-model.md, experiments.md, roadmap.md, interview-guide.md, privacy-compliance.md, ip-and-contracts.md
- Read any path the founder lists.

Constraints:
- Write every date as YYYY-MM-DD.
- Invent nothing. Do not invent partner names, prices, or results. A missing price is an open question.
- Label each claim (evidence: <repo path or source>) or (assumption: <test>).
- The agreement section is an outline of topics and choices. Do not write contract clauses. Tell the founder to have a lawyer draft or review the agreement, especially confidentiality, data protection, IP in feedback, liability, and reference rights.
- Tell partners the truth about product maturity, pilot length, and the price after the pilot.
- Draft messages only. The founder sends them.

Program context (founder-provided):
- Product:
- Artifact date (YYYY-MM-DD):
- Target segment and ICP file:
- Product today and what is missing:
- Learning questions:
- Founder hours per week for partners:
- Pilot length and start date:
- Pilot price and price after pilot:
- Data touched at a partner:
- Interested prospects:
- What you can offer:
- What you want back:

Steps:
1) Program goal. One sentence, then the 3 to 5 learning questions. Map each question to an assumption in experiments.md.
2) Partner criteria. Take them from Qualification Criteria and Disqualifiers in the ICP file. Split into:
   - Must have (4 to 6): for example the pain is active now, a named champion with time, access to the real workflow or data, a buyer who can approve the paid price
   - Nice to have (2 to 4)
   - Disqualifiers (3 to 5): for example wants a custom build, no path to budget, outside the ICP
   Score each prospect: one point per must-have met. A prospect qualifies only with every must-have and no disqualifier.
3) Target number. Show the math: founder hours per week / hours per partner per week (calls, support, follow-up). Recommend a number the founder can serve with weekly contact, and a recruiting target above it to allow for drop-outs. Mark both "proposed".
4) The offer, as a two-column table: What partners get | What partners give. Every "give" is specific: hours per week, a named champion, real usage by a set date, a feedback call cadence, a reference or case study if success criteria are met.
5) Pilot pricing. Lay out the trade-off between free, discounted, and paid pilots in three lines. A paid pilot is the strongest evidence of demand. State the price after the pilot, or record it as an open question to settle before recruiting.
6) Agreement outline. Table: Topic | Options | Founder's choice | Lawyer check (yes / no). Topics: scope and what is excluded, pilot length and end date, feedback cadence, data handling and confidentiality, who owns feedback and ideas, price during and after the pilot, reference and logo rights, support level, early termination, what happens to data at the end.
7) Recruiting message, 90 words or fewer: the problem in the segment's words, what the program is, what you ask for, the pilot length, and a 20-minute call ask. Add a 20-minute qualification call outline that checks every must-have.
8) Onboarding. Kickoff call agenda (goals, baseline measurement, success metric, champion, calendar of feedback calls, conversion conversation date). Then a week-by-week plan for the pilot length.
9) Success criteria.
   - Per partner: one metric with a baseline and a target, agreed at kickoff
   - Program: partners who reach their target, partners who convert to paid, and learning questions answered. Leave the thresholds for the founder to fill, marked "set before the first kickoff".
10) Path to paid. The conversion conversation date is set at kickoff. Write the conversion offer, the decision date, and what happens on yes, no, and "not yet".
11) Feature-request rule. Build a request only when it fits the ICP, serves the job the product exists for, and at least two partners raised the same underlying need. Log every request with the partner and the job behind it.
12) Exit rules. End a partnership when: no usage for a set number of weeks, two missed feedback calls in a row, or requests keep pulling outside the ICP. Write a short, polite exit message and the data return or deletion step.
13) Partner tracker. Columns: Company | Champion | Buyer | Must-haves met | Stage | Kickoff date | Success metric (baseline -> target) | Last feedback call | Conversion date | Status.

Output format (Markdown), in this exact order:
1. Title: <Product> design partner program, YYYY-MM-DD
2. Program goal and learning questions
3. Partner criteria
4. Target number and capacity
5. The offer
6. Pilot pricing and price after pilot
7. Agreement outline
8. Recruiting message and qualification call
9. Onboarding and feedback cadence
10. Success criteria
11. Path to paid
12. Feature-request rule
13. Exit rules
14. Partner tracker
15. Open questions
16. Repo paths referenced
```

## Workflow (runbook)

1. Confirm the ICP. If `Qualification Criteria` in `.productmap/01_strategy/segmentation/icp-b2b.md` is blank, fill it first. Partner criteria come from there.
2. Read the repo, starting at `.productmap/INDEX.md`. Read `.productmap/02_discovery/growth-sales/founder-led-sales.md` for prospects already in the pipeline and price reactions already logged.
3. Do the capacity math before recruiting. A partner you can't speak with every week isn't a design partner.
4. Run the prompt. Settle the price after the pilot with the founder before any message goes out.
5. Take the agreement outline to a lawyer. Check data terms against `.productmap/05_operations/legal/privacy-compliance.md`. Sign before the partner sees real data.
6. Recruit warm paths first, using the message and the qualification call. Score each prospect on the must-haves the same day.
7. Run kickoffs. Agree the success metric, the baseline, and the conversion conversation date on the call. Save notes to `.productmap/06_data/interviews/`.
8. Write back to the repo:
   - Add the section `Design Partner Program` to `.productmap/02_discovery/growth-sales/founder-led-sales.md` below `Pricing Conversations`.
   - Add each partner to the deal tracker table in `Pipeline` with stage `Demo / Pilot`.
   - Record each signed agreement in the `Contract Register` of `.productmap/05_operations/legal/ip-and-contracts.md`.
9. Review the tracker weekly. Apply the exit rules as written. Hold each conversion conversation on its date and log the price reaction under `Pricing Conversations`.
10. Close the program. Count results against the program criteria, update `First 10 Customers` in the same file, and add learnings to `.productmap/02_discovery/experiments/experiments.md`.

## Quality checklist

- Partner criteria trace to the ICP file, with 4 to 6 must-haves and 3 to 5 disqualifiers.
- The target number shows its capacity math and fits the founder's weekly hours.
- Every item partners give is specific: hours, a named champion, a date, a cadence.
- The price after the pilot is stated or sits at the top of open questions, and partners hear it before they join.
- The agreement outline covers all ten topics, holds no contract wording, and flags the lawyer checks.
- The recruiting message is 90 words or fewer and states the pilot length and the ask.
- Each partner has one success metric with a baseline and a target, set at kickoff.
- The conversion conversation has a date in `YYYY-MM-DD` for each partner.
- The feature-request rule and the exit rules use counts, not judgment calls.
- No partner name, price, or result was invented.
- `Repo paths referenced` lists every file read, starting with `.productmap/INDEX.md`.

## Related on Product Map

- Agent: **[Define ICP and segments](https://app.productmap.io/agents/ideal-customer-profile-icp)** — clarify target customers and your positioning.

More AI PM agents from Product Map: https://www.productmap.io/
