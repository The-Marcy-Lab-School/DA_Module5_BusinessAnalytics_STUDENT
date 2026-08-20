# About the starter workbooks

There are 4 files here, one per domain in `../SCENARIOS.md`:

- `finance_insurance_workbook.xlsx`
- `healthcare_operations_workbook.xlsx`
- `public_sector_workbook.xlsx`
- `professional_services_workbook.xlsx`

**Pick one, delete the other 3.** Each workbook has the same 3-sheet
shape:

1. **KPI Summary** (empty) — where your real work goes: PivotTables,
   XLOOKUP/VLOOKUP, KPI calculations.
2. **A raw data sheet** (or two) — real transactional data, already
   formatted as an Excel Table so PivotTables can source from it cleanly.
3. **A reference/lookup sheet** — what your required XLOOKUP/VLOOKUP
   joins against. Not optional decoration; the join key really is needed
   to answer your domain's framing question.

Nothing on the "KPI Summary" sheet is given — no PivotTable, no formula,
no KPI definitions. That's the actual project. See `kpi_definitions.md`
in this same folder for what to define **before** you open the
spreadsheet, and `../SCENARIOS.md` for your domain's stakeholder framing
and exact sheet/column names.
