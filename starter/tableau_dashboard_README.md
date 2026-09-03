# About the starter data

There are 4 domain data sets here, one per `SCENARIOS.md` domain:

- `finance_insurance_extract.hyper` / `data/finance_insurance/`
- `professional_services_extract.hyper` / `data/professional_services/`
- `healthcare_operations_extract.hyper` / `data/healthcare_operations/`
- `public_sector_extract.hyper` / `data/public_sector/`

**Pick one, delete the other 3** (both the `.hyper` file and the
`data/<domain>/` folder).

## Two ways to connect in Tableau Public

- **The `.hyper` file** — a real Tableau data extract, already built and
  verified. Tableau Public → Connect → "More..." → pick the `.hyper`
  file directly. Fastest way to start; all tables are already inside
  one file (Tableau will let you build relationships/joins between them
  in the data-source pane).
- **The CSVs in `data/<domain>/`** — the same data, as plain CSV files,
  if you'd rather connect to CSVs directly (e.g. to practice Tableau's
  own CSV-import/join flow) or inspect the raw data outside Tableau
  first.

Either is fine — the data is identical either way.

## What's given vs. what's yours to build

Nothing about the dashboard itself is given — no chart, no calculated
field, no filter, no worksheet. That's the actual project. See
`kpi_notes.md` for what to define before you open Tableau, and
`required_techniques.md` / `qa_dashboard_notes.md` for what your
finished workbook needs to demonstrate.
