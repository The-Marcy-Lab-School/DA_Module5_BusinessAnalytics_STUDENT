# Project Overview: Business Analytics — Excel & KPI Development

## The objective

Pick one of 4 real stakeholder domains (`SCENARIOS.md`), then build a KPI
summary workbook for the specific decision that stakeholder needs to make:
**3+ KPIs**, each with a PivotTable-based calculation spanning at least 2
dimensions, and **at least one XLOOKUP/VLOOKUP join** to a reference table
with zero `#N/A` errors. For each KPI, decide whether a mean or median
framing actually represents the underlying variable — check its real
distribution shape first (the Module 2 habit), don't default to mean out
of convention. Build the **same summary a second time in Google Sheets**
(a native pivot table or `QUERY`, your choice) — not a from-scratch
redesign, a platform-transfer rep of a KPI logic you've already solved
once. Then write a one-page stakeholder memo that **leads with the
recommended action**, not the methodology.

## Why it matters

This is the first project in the program where the deliverable isn't code
at all — it's a real spreadsheet, the tool most stakeholders outside a
data team will actually open. Being able to build a trustworthy PivotTable
summary and a lookup formula that survives someone else editing the sheet
later is a distinct skill from writing a script that does the same thing
once and never gets touched again — and knowing when a recurring report
*should* graduate from a workbook to a script (a real tradeoff, not just a
tool preference) is worth understanding directly. **Module 6** builds a
dashboard from data shaped exactly like the KPI summary you build here.

## Deliverables at a glance

- One domain chosen from `SCENARIOS.md`, its starter workbook kept
  (`starter/<domain>_workbook.xlsx`), the other 3 domains' workbooks
  deleted.
- 3+ KPIs built with real PivotTable-based calculations (≥2 dimensions
  each) in the given `.xlsx`.
- At least 1 XLOOKUP or VLOOKUP formula joining your raw data sheet to the
  given reference sheet — zero `#N/A` errors, and correct enough
  relative/absolute references that the formula still works if a row is
  inserted above it.
- Each KPI's mean-vs-median framing justified in writing, tied to the
  variable's actual checked distribution shape.
- `starter/kpi_definitions.md` filled in: formula, target, and data
  source for each KPI — not just "a metric I could calculate."
- The AI-formula-verification exercise done for real
  (`starter/ai_formula_verification.md`): a real AI-suggested formula,
  manually checked against a small hand-computed sample before trusting
  it in the workbook.
- The same KPI summary reproduced in a real Google Sheet, submitted as a
  live, view-access share link (see `GETTING_STARTED.md` for exactly how).
- At least 2 specific, real clarifying questions about your data's
  origin/completeness, posed before trusting the KPI built on it.
- A one-page stakeholder memo (`starter/memo.md`) that opens with the
  recommended action, free of unexplained jargon.

## Skills you'll practice

- **Excel** — PivotTables spanning real dimensions, XLOOKUP/VLOOKUP joins,
  and cell-reference discipline that survives a row being inserted.
- **Google Sheets** — reproducing the same summary logic on a second real
  platform, not re-deriving it from scratch.
- **KPI Development** — turning a raw number into something with a
  formula, a target, and an owner tied to a real decision.
- **Business Acumen** — framing a finding in terms of revenue, cost, or
  risk, not just the statistic itself.
- **Attention to Detail** — a workbook with zero formula errors, correct
  references, that survives being edited after you hand it off.
- **Stakeholder Communication** — a memo that leads with the action.
- **Critical Thinking** — questioning a dataset's origin and completeness
  before building a decision on top of it.

## Timeline

See `CHECKLIST_TIMELINE.md` for the day-by-day sprint pace and the full
submission checklist.

## Where to start

Go to `README.md`, then `GETTING_STARTED.md` — they walk through getting
your own copy of this repo, setting up free Excel Online / Google Sheets
access, and exactly how to submit a live Google Sheets link.
