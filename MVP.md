# MVP — the real bar for "done"

This is what actually gets graded as Meets/Approaching/Below per skill.
See instructor `rubric.md` for the full rubric if your instructor has
shared it — this is the same bar in checklist form.

## Workbook (Excel)

- [ ] One domain chosen, its `.xlsx` kept, the other 3 deleted from
      `starter/`.
- [ ] 3+ KPIs built with real PivotTables, each spanning **at least 2
      dimensions**.
- [ ] At least 1 XLOOKUP or VLOOKUP join to the reference sheet, **zero
      `#N/A` errors**.
- [ ] References (relative/absolute) correct enough that formulas survive
      a row being inserted above them — actually test this, don't assume
      it.
- [ ] Each KPI's mean-vs-median framing justified in writing
      (`kpi_definitions.md`), tied to the variable's real, checked
      distribution shape — not defaulted to mean.

## Google Sheets

- [ ] The same KPI summary reproduced (native pivot table or `QUERY`) in
      a real Google Sheet.
- [ ] Shared "Anyone with the link" / Viewer, link confirmed working in
      an incognito window, pasted into `memo.md`.

## Written work

- [ ] `kpi_definitions.md`: stakeholder + decision (one sentence), each
      KPI's formula/target/data source, mean-vs-median reasoning, ≥2 real
      clarifying questions about the data's origin/completeness.
- [ ] `ai_formula_verification.md`: a real AI-suggested formula, a real
      manual check against 3-5 hand-verified rows, an honest account of
      what (if anything) needed fixing.
- [ ] `memo.md`: one page, **opens with the recommended action**, frames
      the finding in business terms (revenue/cost/risk), free of
      unexplained jargon.

## What "Below" looks like, concretely

- KPIs with no target or owner — a number with no action tied to it.
- Mean used everywhere by default, no distribution check.
- A memo that opens with "I analyzed the dataset and found..." instead of
  the recommendation.
- An XLOOKUP that only works because nothing was ever tested against a
  row insertion.
