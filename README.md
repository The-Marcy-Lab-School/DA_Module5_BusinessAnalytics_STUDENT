# Business Analytics & Data Visualization: Excel & Tableau Dashboards for Two Stakeholders

Start with `PROJECT_OVERVIEW.md` for what you're building and why. This
file (`README.md`) is where the step-by-step setup lives.

**Due:** 8 days, run as a sprint, plus a required share-out session
scheduled after. See `CHECKLIST_TIMELINE.md` for the day-by-day pace and
the full submission checklist.

This repo is a **GitHub template** — a starting point, not something you
edit directly on Marcy's copy of it.

## Getting started

### Step 1: Get your own copy

On this repo's GitHub page, click **"Use this template" → "Create a new
repository"** (not Fork). Name it something like
`business-analytics-and-visualization`, keep it **public**, and create it.

### Step 2: Clone your new repo locally

```bash
git clone <the URL of your own new repo>
cd <your-repo-name>
```

### Step 3: Confirm your environment — the basics are already set up

`.gitignore`, `LICENSE`, and a real git history are already here:

```bash
ls -a          # should show .gitignore among the files
cat LICENSE    # should show the MIT License text
git log --oneline
```

**One real edit still needed:** open `LICENSE` and replace the placeholder
`[YOUR NAME]` on the copyright line with your actual name. Commit that
change alongside your other early commits.

### Step 4: Set up free Excel access *and* Tableau Public

See `GETTING_STARTED.md` — both tools get their own dedicated setup
walkthrough. Part A is **Excel only** (no Google Sheets); Part B is
**Tableau Public only** (not Power BI Desktop, which is Windows-only).

## Your domain and both stakeholders

See `SCENARIOS.md` and pick **one** of the 4 domains — each domain now
names **two** real stakeholders, one for Part A (Excel), one for Part B
(Tableau). **Part A's** starter dashboard is already built at
`starter/<domain>_dashboard.xlsx`. **Part B's** real data is already
built at `starter/<domain>_extract.hyper` and mirrored as plain CSVs at
`data/<domain>/`. **Delete the other 3 domains' files from `starter/`
and `data/` once you've chosen.**

## What to do

**Part A — Excel:**
- Fill in `starter/kpi_definitions.md` **before** you build anything —
  name Stakeholder A, their decision, and each of your 3 KPI cards'
  role (North Star/Leading/Lagging), formula, and reasoning.
- Build: 3 KPI cards, ≥2 real charts, ≥1 XLOOKUP/VLOOKUP (zero `#N/A`),
  one interactive "as of month" dropdown driving your Leading
  indicator's trailing-3-month-vs-prior-year comparison — tested with
  more than one month.
- Do the real data cleaning your domain needs (see `data/SOURCE.md`).
- Do the 2-part AI exercise (`starter/ai_dashboard_review.md`).
- Write `starter/memo.md` — one page, leads with the recommended action.

**Part B — Tableau:**
- Connect your chosen domain's data (see
  `starter/tableau_dashboard_README.md` for the two ways to connect).
- Fill in `starter/kpi_notes.md` **before** you build anything — name
  Stakeholder B (a genuinely different stakeholder than Part A's), their
  decision, your KPIs, and map each of your ≥4 business questions to a
  chart type.
- Build ≥4 coordinated visuals, **all 6 required techniques**
  (`starter/required_techniques.md`), and a separate **QA dashboard**
  (`starter/qa_dashboard_notes.md`).
- Do the real data cleaning this part's data needs.
- Do the AI chart-suggestion exercise (`starter/ai_chart_suggestion.md`).
- **Publish your workbook to Tableau Public** and get the real
  shareable link.
- Prepare and deliver (live or recorded) your stakeholder walkthrough.

**Part C — Tool comparison:**
- Complete `starter/tool_comparison.md` — a real, specific comparison of
  the two tools for the two decisions you just built, not a generic
  "Tableau has more features" writeup.

`CHECKLIST_TIMELINE.md` has the suggested day-by-day pace and the full
sequenced checklist.

**Where's the exact bar for "done," and what are the optional stretch
goals?** This repo (your own copy) doesn't include `MVP.md` or
`ABOVE_AND_BEYOND.md` on purpose — they're not something to keep sitting
in your portfolio repo. Ask your instructor for the link to this
template's `project-scope` branch to read them, or check the checklist
your instructor shares through the classroom, which covers the same
ground.
