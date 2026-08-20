# Checklist & Timeline

**5 days, run as a sprint.** Real spreadsheet work is deceptively fast to
start and slow to finish cleanly — the goal isn't "get 3 numbers to show
up," it's a workbook that survives someone else touching it later.

## Day 1 — Pick the decision, not the spreadsheet

- [ ] Read `SCENARIOS.md`, pick one domain, delete the other 3 `.xlsx`
      files from `starter/`.
- [ ] Fill in `starter/kpi_definitions.md`'s first section: name your
      stakeholder and their decision in one sentence, *before* naming a
      single KPI.
- [ ] Open your workbook. Inspect the raw data sheet and the reference
      sheet — know what each column actually means before building
      anything.

## Day 2 — Build the Excel workbook

- [ ] Build 3+ KPIs on the "KPI Summary" sheet using real PivotTables
      (≥2 dimensions each).
- [ ] Build at least 1 XLOOKUP (or VLOOKUP) join to the reference sheet —
      zero `#N/A` errors.
- [ ] Test it: insert a row into your raw data sheet and confirm your
      PivotTables/lookups still work. Then undo, or re-verify your row
      counts are back to normal.
- [ ] If you copy/paste a formula into adjacent cells, check whether each
      reference should have shifted (relative) or stayed fixed
      (absolute, `$`) — a copied formula that silently shifted a
      reference it should have locked is a real, common way a workbook
      looks right until someone edits it.

## Day 3 — Mean-vs-median + AI-verification

- [ ] For each KPI, check the underlying variable's real distribution
      shape (skew, outliers) before deciding mean or median — write the
      reasoning in `kpi_definitions.md`, not just the final choice.
- [ ] Do the AI-formula-verification exercise
      (`starter/ai_formula_verification.md`) for real.

## Day 4 — Google Sheets + clarifying questions

- [ ] Rebuild the same KPI summary in a new Google Sheet.
- [ ] Share it view-access, confirm the link works in an incognito
      window.
- [ ] Write your ≥2 clarifying questions about the data's origin/
      completeness in `kpi_definitions.md`.

## Day 5 — Memo, finish, verify, submit

- [ ] Write `starter/memo.md` — lead with the recommended action.
- [ ] Paste your live Google Sheets link at the top of the memo.
- [ ] Final workbook QA pass: no `#REF!`/`#N/A` anywhere, references
      survive a row insert, KPI definitions are specific (formula/
      target/data source, not vague).
- [ ] Commit and push.

## Submission checklist

- [ ] `starter/<your-domain>_workbook.xlsx` — 3+ KPIs, PivotTable-based,
      ≥2 dimensions each, ≥1 working XLOOKUP/VLOOKUP, zero formula
      errors.
- [ ] `starter/kpi_definitions.md` — stakeholder/decision, each KPI's
      formula/target/data source, mean-vs-median reasoning, ≥2
      clarifying questions.
- [ ] `starter/ai_formula_verification.md` — real AI-suggested formula,
      real manual verification.
- [ ] A live, view-access Google Sheets link in `starter/memo.md`,
      confirmed working.
- [ ] `starter/memo.md` — one page, leads with the action.
- [ ] Other 3 domains' workbooks deleted from `starter/`.
