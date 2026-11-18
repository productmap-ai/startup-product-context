---
name: pricing-page-audit
description: Score an existing pricing page out of 150 across five pillars, add an unscored test backlog, and return a rating band, strengths, critical gaps, and prioritized fixes in a dated audit file.
---

# Pricing page audit — Skill

## Name

`pricing-page-audit` — Score a live or draft pricing page against 30 fixed criteria and leave with an ordered list of fixes.

## When to use

- Your pricing page is live and visitors leave it without picking a plan.
- Prospects ask "which plan is for me?" or "what does it cost in total?" on calls.
- You're about to change prices or tiers and want a baseline score first.
- A draft pricing page is ready and you want a review before it ships.
- You redesigned the page and want to compare the new score with the last audit.
- Use a sibling skill instead when the pricing model or the tiers are undecided (`.claude/skills/monetization-pricing/SKILL.md`) or you have willingness-to-pay research to read (`.gemini/skills/pricing-research-synthesis/SKILL.md`).

## Inputs (ask user for these)

- Product name:
- Artifact date (YYYY-MM-DD) (use today's date unless the founder gives another):
- Pricing page URL, or the full page text pasted, plus screenshots if you have them:
- Whether the reviewer can open the URL (yes / no, paste instead):
- Target segment the page must convert:
- Current plans, prices, billing periods, and trial or free plan terms:
- The plan you want most buyers to choose:
- Conversion data if any (visits to the page, plan clicks, signups, paid conversions, date range):
- Objections heard on sales calls or in support:
- Competitor pricing pages to compare (URLs):
- Constraints (what you can't change this month):

## Outputs

- Pricing page audit (Markdown) containing:
  - Overall score out of 150, percentage, and rating band
  - Pillar scores A to E (each out of 30) with a score and a one-line reason for all 30 criteria
  - Pillar F: unscored test backlog
  - Key strengths and critical gaps
  - Prioritized fixes with impact, effort, and the criterion each one moves
  - What could not be assessed and what is needed to assess it
- Where to store it:
  - New dated file: `.productmap/01_strategy/business-model/pricing-page-audit-YYYY-MM-DD.md`
  - Tests chosen from pillar F: `Hypothesis Backlog` in `.productmap/02_discovery/experiments/experiments.md`
  - Saved page text and screenshots: `.productmap/06_data/research/`

## Repo knowledge to pull

- Start here: `.productmap/INDEX.md`
- Pricing model and revenue streams: `.productmap/01_strategy/business-model/business-model.md`
- Who the page must convert: `.productmap/01_strategy/segmentation/icp-b2b.md`, `.productmap/01_strategy/segmentation/icp-b2c.md`
- Value claims to check the page against: `.productmap/00_company/product/value-proposition.md`
- Competitive price anchors: `.productmap/01_strategy/competitors/competitor-matrix.md`
- Price reactions from calls: `.productmap/02_discovery/growth-sales/founder-led-sales.md`, `.productmap/06_data/interviews/`
- Margin limits on discounts and free plans: `.productmap/03_analysis/unit-economics/unit-economics.md`
- Earlier audits in `.productmap/01_strategy/business-model/`

## Detailed prompt (copy/paste)

```
You are a pricing and conversion reviewer. Audit the pricing page below against the fixed criteria, score it, and return fixes in priority order. Read the repo first and cite every path you used.

Repo-first context to consult:
- Start at: .productmap/INDEX.md
- Read: business-model.md, icp-b2b.md or icp-b2c.md, value-proposition.md, competitor-matrix.md, founder-led-sales.md, unit-economics.md
- Read any earlier pricing-page-audit file in .productmap/01_strategy/business-model/ and compare scores.
- If you can browse, open the URL before scoring. If you cannot, score only what the founder pasted.

Constraints:
- Write every date as YYYY-MM-DD.
- Invent nothing. Do not guess conversion rates, competitor prices, or what a screenshot would show.
- Score what is on the page. Quote the page text that supports each score.
- Label each finding (evidence: <page quote, repo path, or URL with access date>) or (assumption: <test>).
- A criterion you cannot see is "n/a", not a low score.
- Audit the page. Do not redesign the pricing model here.

Audit context (founder-provided):
- Product:
- Artifact date (YYYY-MM-DD):
- Pricing page URL or pasted content:
- Target segment:
- Plans, prices, billing, trial terms:
- Plan most buyers should choose:
- Conversion data and date range:
- Objections heard:
- Competitor pricing pages:
- Constraints:

Steps:
1) Describe the page as found: plans, prices, units, billing options, calls to action, proof, FAQ. Quote, do not paraphrase.
2) Score all 30 criteria from 0 to 5.
   0 = missing or misleading. 1 = present but confusing. 3 = clear and adequate. 5 = clear, specific to the target segment, and backed by something visible. Use 2 and 4 for in-between cases.
   A. Strategy and research
   A1 The unit you charge for matches how customers get value
   A2 Price is framed against an outcome or a cost the buyer already has
   A3 Position against alternatives is consistent with competitor-matrix.md
   A4 Price points rest on willingness-to-pay evidence in the repo
   A5 Each plan maps to a segment or stage in the ICP files
   A6 The model on the page matches Revenue Streams in business-model.md
   B. Information architecture
   B1 Two to four plans, readable in one screen
   B2 Each plan has a name and a "who it is for" line
   B3 The reason to upgrade from each plan to the next is obvious
   B4 Features are grouped and written in the customer's words
   B5 Limits and units are stated (seats, usage, overage)
   B6 Buyers who fit no plan have a path (contact, custom, free)
   C. Psychology and persuasion
   C1 One plan is recommended, with a reason
   C2 Plan order and annual versus monthly framing guide the choice honestly
   C3 Real, attributable proof sits near the decision
   C4 Plan copy leads with outcomes, then features
   C5 Urgency or scarcity appears only where true. Score 0 for a fake countdown or invented limit.
   C6 Risk reversal is visible (trial, guarantee, cancel any time)
   D. UX and visual design
   D1 The eye lands on plans and prices first
   D2 The billing toggle is clear and states the saving
   D3 Each plan has one call to action whose label says what happens next
   D4 The page and its comparison table work on a phone
   D5 Text is readable (contrast, size, no prices inside images)
   D6 Each call to action leads to the matching plan with no dead end
   E. Trust and friction
   E1 The FAQ answers the top objections the founder listed
   E2 Total cost is transparent (taxes, fees, overage, currency)
   E3 Cancellation and refund terms are stated
   E4 Security, privacy, or compliance cues match what this segment asks for
   E5 A human is reachable from the page
   E6 Trial or free plan terms are clear (card needed, what happens at the end)
3) Pillar score = sum of its six criteria, out of 30. If some criteria are n/a: pillar score = sum / (5 x criteria assessed) x 30, rounded. Overall = A + B + C + D + E, out of 150.
4) Rating band: 0 to 59 Rebuild. 60 to 82 Weak. 83 to 104 Workable. 105 to 127 Strong. 128 to 150 Excellent.
5) Key strengths: 3 to 5 bullets, each tied to a criterion.
6) Critical gaps: every criterion scored 0 or 1, plus anything misleading. Misleading items come first.
7) Prioritized fixes. Columns: # | Fix | Criterion | Impact (High / Medium / Low) | Effort (S / M / L) | Evidence. Order: misleading items, then High impact with S effort, then the rest by impact.
8) Pillar F, optimisation opportunities, unscored. List 5 to 8 changes that need data or a split test to judge. Columns: Hypothesis | Change | Metric | Data needed | Effort.
9) List what you could not assess and what the founder must supply.

Output format (Markdown), in this exact order:
1. Title: <Product> pricing page audit, YYYY-MM-DD
2. Overall score and rating band
3. Page as found
4. Pillar scores (A to E, all 30 criteria)
5. Key strengths
6. Critical gaps
7. Prioritized fixes
8. Pillar F: optimisation opportunities
9. Not assessed
10. Change since last audit
11. Repo paths referenced
```

## Workflow (runbook)

1. Get the page. If the reviewer can't open the URL, ask the founder to paste the full text, top to bottom, and attach desktop and phone screenshots.
2. Save the page text to `.productmap/06_data/research/` so the next audit can compare against it.
3. Read the repo:
   - Start at `.productmap/INDEX.md`, then `.productmap/01_strategy/business-model/business-model.md` and the ICP file for the target segment.
   - Pull price objections from `.productmap/02_discovery/growth-sales/founder-led-sales.md`.
4. Run the prompt. Score every criterion before writing any fix.
5. Check the arithmetic: six criteria per pillar, five pillars, 150 points. Recompute any pillar with n/a rows.
6. Review the fixes with the founder. Remove any fix that breaks a stated constraint and note it under open items.
7. Handle risky wording. Refund terms, guarantees, auto-renewal, and tax display are legal topics. Confirm the final wording with a lawyer or accountant.
8. Save the audit as `.productmap/01_strategy/business-model/pricing-page-audit-YYYY-MM-DD.md`.
9. Move the pillar F tests the founder picks into `Hypothesis Backlog` in `.productmap/02_discovery/experiments/experiments.md`, each with a success criterion.
10. Re-run after the fixes ship and fill in `Change since last audit`.

## Quality checklist

- All 30 criteria have a score from 0 to 5 or `n/a`, each with a page quote or a reason.
- Pillar and overall arithmetic is right, and the rating band matches the total.
- No criterion was scored from a guess about content the reviewer couldn't see.
- A fake countdown, invented scarcity, or hidden cost scores 0 and leads the critical gaps.
- Every fix names the criterion it moves, an impact level, and an effort size.
- A4, A5, and A6 were scored against repo files, and those files are cited.
- Pillar F holds 5 to 8 testable items and carries no score.
- The audit stays on the page. Model and tier redesign is handed to the monetization skill.
- Legal wording (refunds, renewal, taxes) is flagged for a lawyer or accountant.
- `Repo paths referenced` lists every file read, starting with `.productmap/INDEX.md`.

## Related on Product Map

- Agent: **[Define monetization strategy](https://app.productmap.io/agents/monetization-pricing)** — pick the right model, pricing, and packaging.

More AI PM agents from Product Map: https://www.productmap.io/
