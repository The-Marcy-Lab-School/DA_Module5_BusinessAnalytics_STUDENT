# QA Dashboard Notes

Before your stakeholder-facing dashboard is "done," build a **separate,
non-stakeholder-facing sheet/dashboard in the same workbook** that
checks your own data actually loaded correctly. This is a real,
professional habit — the same reason you wrote a real before/after
`.isna().sum()` check every time you cleaned data in Modules 2/3/4/6,
just applied to a BI tool instead of pandas or Excel.

Real BI dashboards get rebuilt against refreshed data regularly — a real
analyst checks the refresh actually worked (right row count, right date
range, no unexpected blank fields) *before* trusting what the
stakeholder-facing charts show. Tableau Public workbooks are static
snapshots (no live server refresh the way a connected enterprise
dashboard would have), but the habit is the same: verify your data
before you publish, every time, not just the first time.

## What your QA dashboard/sheet must show

- [ ] **Row count** per data source/table you used.
- [ ] **Min/max date** for every date field a stakeholder-facing visual
      depends on.
- [ ] **Null count** (or % null) on every field a stakeholder-facing
      visual depends on.

## Document what you actually found

**Row counts:** TODO

**Date ranges:** TODO

**Null checks — anything surprising?** TODO (tie this back to the real
cleaning issue you documented in `kpi_notes.md` — did your QA check
actually catch it, or did you already know about it from inspecting the
raw data first?)
