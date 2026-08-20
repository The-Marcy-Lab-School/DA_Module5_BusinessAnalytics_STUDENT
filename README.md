# Business Analytics: Excel & KPI Development Project

Start with `PROJECT_OVERVIEW.md` for what you're building and why. This
file (`README.md`) is where the step-by-step setup lives.

**Due:** 5 days, run as a sprint. See `CHECKLIST_TIMELINE.md` for the
day-by-day pace and the full submission checklist.

This repo is a **GitHub template** — a starting point, not something you
edit directly on Marcy's copy of it.

## Getting started

### Step 1: Get your own copy

On this repo's GitHub page, click **"Use this template" → "Create a new
repository"** (not Fork — Fork keeps a visible link back to this template,
which isn't what you want for a portfolio project). Name it something like
`business-analytics-kpi`, keep it **public**, and create it.

### Step 2: Clone your new repo locally

```bash
git clone <the URL of your own new repo>
cd <your-repo-name>
```

### Step 3: Confirm your environment — the basics are already set up

Like Module 1 and 3, `.gitignore`, `LICENSE`, and a real git history are
already here — git itself isn't being newly tested this module:

```bash
ls -a          # should show .gitignore among the files
cat LICENSE    # should show the MIT License text
git log --oneline
```

**One real edit still needed:** open `LICENSE` and replace the placeholder
`[YOUR NAME]` on the copyright line with your actual name. Commit that
change alongside your other early commits.

### Step 4: Set up free Excel and Google Sheets access

See `GETTING_STARTED.md` — both tools are new this module and get their
own dedicated setup walkthrough, including exactly how to submit a **live
Google Sheets link** (this project's one genuinely different submission
mechanic — nothing about Google Sheets lives in this git repo).

## Your domain and data

See `SCENARIOS.md` and pick **one** of the 4 stakeholder domains. Each
domain's starter workbook is already built at
`starter/<domain>_workbook.xlsx` — real transactional data on one sheet,
a reference/lookup table on a second sheet, and an empty "KPI Summary"
sheet where your real work goes. **Delete the other 3 domains' workbooks
from `starter/` once you've chosen** — same reasoning as every prior
module's "pick one, remove the rest."

## What to do

- Open your chosen `.xlsx` in Excel (Excel Online is fine — see
  `GETTING_STARTED.md`). The raw data and reference table are given and
  already formatted as real Excel Tables (ready for PivotTables to source
  from); the "KPI Summary" sheet is empty except for a prompt.
- Fill in `starter/kpi_definitions.md` **before** you build anything in
  the spreadsheet — name your stakeholder, their decision, and each KPI's
  formula/target/data source. `exemplar_guidance` is direct about this:
  pick the decision first, work backward to which 3 KPIs actually inform
  it.
- Build 3+ KPIs on the "KPI Summary" sheet using real PivotTables (≥2
  dimensions each) and at least 1 XLOOKUP/VLOOKUP join to the reference
  sheet. Test that your XLOOKUP survives a row being inserted above it —
  a formula that only works because nothing ever changes isn't done.
- For each KPI, check the underlying variable's real distribution shape
  (skew, outliers) before deciding mean or median — this is Module 2's
  own five-number-summary/skew habit, reused for real here.
- Do the AI-formula-verification exercise
  (`starter/ai_formula_verification.md`) — ask an AI assistant to suggest
  a KPI or XLOOKUP formula, then manually check it against a small
  hand-computed sample before trusting it.
- Rebuild the same KPI summary in a new Google Sheet (`File → Import` your
  `.xlsx`, or start fresh from the same raw data) using a native pivot
  table or `QUERY`. Share it view-access and record the link per
  `GETTING_STARTED.md`.
- Write `starter/memo.md` — one page, leads with the recommended action.

`CHECKLIST_TIMELINE.md` has the suggested day-by-day pace and the full
sequenced checklist.

**Where's the exact bar for "done," and what are the optional stretch
goals?** This repo (your own copy) doesn't include `MVP.md` or
`ABOVE_AND_BEYOND.md` on purpose — they're not something to keep sitting
in your portfolio repo. Ask your instructor for the link to this
template's `project-scope` branch to read them, or check the checklist
your instructor shares through the classroom, which covers the same
ground.
