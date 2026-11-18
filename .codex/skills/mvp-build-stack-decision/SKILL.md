---
name: mvp-build-stack-decision
description: Produce a decision record that chooses between no-code, low-code, AI-assisted coding, and a custom build for the MVP, with weighted criteria, consequences, and a revisit trigger.
---

# MVP build stack decision — Skill

## Name

`mvp-build-stack-decision` — Pick how to build the MVP from the assumption it must test, and write the decision down so you know when to revisit it.

## When to use

- The MVP scope is agreed and the next question is what to build it with.
- A non-technical founder is choosing between a no-code tool, an agency, and an AI coding assistant.
- A technical founder wants to start with a custom stack and nobody has asked whether that's the fastest route to a first user.
- The prototype outgrew its tool and you're deciding whether to migrate now or later.
- A customer or regulator has a data requirement that rules some options out.
- Use a sibling skill instead when the scope itself is too large (`.gemini/skills/mvp-scope-cut-review/SKILL.md`).

## Inputs (ask user for these)

- Product name:
- Artifact date (YYYY-MM-DD) (use today's date unless the founder gives another):
- The riskiest assumption the MVP must test, and the smallest product that tests it:
- Must-have capabilities for the first release (5 to 10 lines):
- Team skills (who can code, in what, hours per week each):
- Budget to first user and monthly budget after launch:
- Target date for the first real user (`YYYY-MM-DD`):
- Data you'll store (personal, payment, health, customer confidential) and where customers are located:
- Integrations you need on day one:
- Expected usage in the first three months (users, records, requests, AI calls):
- Tools you already use or have ruled out, and why:

## Outputs

- Build stack decision record (Markdown) containing:
  - Context: the assumption to test, the first release, constraints
  - Hard gates and which options they remove
  - Options compared: no-code, low-code, AI-assisted coding, custom build
  - Weighted scoring matrix and a sensitivity check
  - Cost at today's usage and at 10 times usage
  - Decision, consequences, lock-in and migration notes
  - Revisit triggers with numbers and a review date
- Where to store it:
  - `.productmap/04_delivery/development/development.md`, as a new section `Build stack decision (YYYY-MM-DD)` below `Key Artefacts`
  - Vendor pricing pages you saved: `.productmap/06_data/research/`

## Repo knowledge to pull

- Start here: `.productmap/INDEX.md`
- Target file: `.productmap/04_delivery/development/development.md`
- Scope and first release: `.productmap/04_delivery/backlog-requirements/backlog.md`, `.productmap/01_strategy/mvp-roadmap/roadmap.md`
- The assumption being tested: `.productmap/02_discovery/experiments/experiments.md`, `.productmap/00_company/product/onepager.md`
- Who builds: `.productmap/00_company/team.md`
- Budget and runway: `.productmap/05_operations/finance/runway-burn.md`
- Data and compliance: `.productmap/05_operations/legal/privacy-compliance.md`
- Code ownership and contractor terms: `.productmap/05_operations/legal/ip-and-contracts.md`

## Detailed prompt (copy/paste)

```
You are a pragmatic technical advisor to an early-stage founder. Compare four ways to build the MVP below and write a decision record. The goal is the fastest route to testing the riskiest assumption, with a known exit. Read the repo first and cite every path you used.

Repo-first context to consult:
- Start at: .productmap/INDEX.md
- Read: development.md, backlog.md, roadmap.md, experiments.md, onepager.md, team.md, runway-burn.md, privacy-compliance.md, ip-and-contracts.md
- Read any path the founder lists.

Constraints:
- Write every date as YYYY-MM-DD.
- Invent nothing. Tool prices and limits come from the founder or from a vendor page you read, cited with URL and access date. Otherwise write "price to confirm" and list it as an open question.
- Label each claim (evidence: <repo path or source>) or (assumption: <test>).
- Name tool categories first. Name specific tools only when the founder listed them or you can cite a source.
- You are not a lawyer. For data protection, security certifications, and who owns contractor-written or AI-generated code, list the questions and tell the founder to confirm with a lawyer.

Build context (founder-provided):
- Product:
- Artifact date (YYYY-MM-DD):
- Riskiest assumption and the smallest product that tests it:
- Must-have capabilities:
- Team skills and hours per week:
- Budget to first user and monthly budget:
- Target date for first user:
- Data stored and customer locations:
- Day-one integrations:
- Expected usage, first three months:
- Tools in use or ruled out:

Steps:
1) Context. State the assumption, the first release in one paragraph, and the constraints. End with one sentence: "The stack must let us learn X by YYYY-MM-DD for under <budget>."
2) Hard gates. List requirements that remove an option outright: data location, a compliance need, a must-have capability the option cannot deliver, an integration it lacks. Table: Gate | Source | Options removed.
3) Describe the four options for this product, 4 to 6 lines each: what gets built with what, who builds it, what it cannot do.
   - No-code: visual builders and automation tools, no source code
   - Low-code: a platform plus custom code where the platform ends
   - AI-assisted coding: real source code written with an AI coding assistant, owned and deployed by the team
   - Custom build: hand-written code by the founder, a hire, or an agency
   Add a hybrid only if the founder named one.
4) Score each surviving option 1 to 5 on six criteria. 1 = poor fit. 3 = workable with known gaps. 5 = strong fit.
   - Fit to the riskiest assumption (can it test the assumption with real users)
   - Time to first user (calendar weeks from today)
   - Team skills (can the current team build and fix it without outside help)
   - Budget (cost to first user plus monthly cost, against the stated budget)
   - Lock-in and migration (can you export data and logic, and what gets rewritten)
   - Cost at 10 times usage
   Default weights, summing to 100: fit 30, time 25, skills 15, budget 15, lock-in 10, cost at 10 times 5. The founder can change them. Show the weights used.
   Matrix columns: Criterion | Weight | one column per option. Last row: weighted total = sum of (score x weight) / 5, out of 100.
5) Cost table. Columns: Option | Pricing driver (seat, record, request, token, hosting) | Cost at expected usage | Cost at 10 times usage | Source.
6) Decision rule. The highest weighted total wins. If the top two are within 5 points, pick the one with the shorter time to first user. Run a sensitivity check: move 10 weight points from the top criterion to lock-in, and say whether the winner changes.
7) Decision. One sentence: "We will build with <option> because <reason>." Then:
   - Consequences: what gets easier, what gets harder, what you give up
   - Lock-in and migration: what you can export, what you would rewrite, estimated effort
   - Risks with an owner each
8) Revisit triggers. Write 3 to 5 with numbers, plus one review date. Examples of trigger types: monthly platform cost above a set amount, a paying-customer count, a validated request the platform cannot serve, response time above a set limit, a customer security review you cannot pass.
9) Alternatives considered: one line per rejected option with the reason.
10) Next actions for the first 14 days, each with an owner and a date.

Output format (Markdown), in this exact order:
1. Title: <Product> build stack decision, YYYY-MM-DD
2. Status (Proposed / Accepted / Superseded)
3. Context
4. Hard gates
5. Options
6. Scoring matrix and sensitivity check
7. Cost at expected and 10 times usage
8. Decision
9. Consequences
10. Lock-in and migration
11. Revisit triggers
12. Alternatives considered
13. Next actions (14 days)
14. Open questions
15. Repo paths referenced
```

## Workflow (runbook)

1. Confirm the assumption. If the founder can't state what the MVP must prove, stop. Fix the scope first, then return.
2. Read the repo:
   - Start at `.productmap/INDEX.md`, then the backlog and `.productmap/02_discovery/experiments/experiments.md`.
   - Check `.productmap/05_operations/legal/privacy-compliance.md` for data rules before comparing any tools.
3. Apply the hard gates before scoring. An option that fails a gate gets no score.
4. Agree the weights with the founder before filling in scores. Changing weights after seeing totals defeats the method.
5. Run the prompt. Ask the founder for vendor pricing pages where a cost is marked "price to confirm".
6. Read the sensitivity check. If the winner flips, tell the founder the decision is close and let time to first user decide.
7. Write the revisit triggers as numbers the founder already tracks or can read from a bill.
8. Write back to `.productmap/04_delivery/development/development.md`:
   - Add the section `Build stack decision (YYYY-MM-DD)` below `Key Artefacts`.
   - Add one row to the `Key Artefacts` table that points to the section.
   - When a later decision replaces this one, set its status to Superseded and keep the text.
9. If contractors or an agency write code, record the contract in `.productmap/05_operations/legal/ip-and-contracts.md` and confirm IP assignment with a lawyer.
10. Review on the planned date or when a trigger fires, whichever comes first.

## Quality checklist

- The context names one assumption and ends with the learn-by sentence, with a date and a budget.
- Hard gates are applied first, and each removed option cites the gate.
- All four options are described for this product, and each says what it can't do.
- Scores use the 1 to 5 scale on the six criteria, weights sum to 100, and totals are computed correctly.
- Every price has a source with URL and access date, or is marked "price to confirm".
- The cost table shows expected usage and 10 times usage for each surviving option.
- The decision is one sentence, and the sensitivity check result is stated.
- Lock-in notes say what exports cleanly and what gets rewritten.
- 3 to 5 revisit triggers carry numbers, and a review date in `YYYY-MM-DD` is set.
- Data protection and code ownership questions are flagged for a lawyer.
- `Repo paths referenced` lists every file read, starting with `.productmap/INDEX.md`.

## Related on Product Map

- Agent: **[Scope and challenge MVP](https://app.productmap.io/agents/mvp-scope-decision)** — cut scope, build the backlog, pick the stack.
- Workflow: **[Product idea to MVP scope](https://app.productmap.io/workflows/product-idea-to-mvp-scope)** — validate the product idea, define strategy and roadmap, then scope and challenge the MVP.

More AI PM agents from Product Map: https://www.productmap.io/
