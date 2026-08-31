# Business Analytics: Excel KPI Dashboard Project

Start with `PROJECT_OVERVIEW.md` for what you're building and why. This
file (`README.md`) is where the step-by-step setup lives.

**Due:** 7 days, run as a sprint, plus a required share-out session
scheduled after. See `CHECKLIST_TIMELINE.md` for the day-by-day pace and
the full submission checklist.

This repo is a **GitHub template** — a starting point, not something you
edit directly on Marcy's copy of it.

## Getting started

### Step 1: Get your own copy

On this repo's GitHub page, click **"Use this template" → "Create a new
repository"** (not Fork — Fork keeps a visible link back to this template,
which isn't what you want for a portfolio project). Name it something like
`business-analytics-dashboard`, keep it **public**, and create it.

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

### Step 4: Set up free Excel access

See `GETTING_STARTED.md` — Excel is new this module and gets its own
dedicated setup walkthrough. This project is **Excel only** — no Google
Sheets component.

## Your domain and data

See `SCENARIOS.md` and pick **one** of the 4 stakeholder domains. Each
domain's starter dashboard is already built at
`starter/<domain>_dashboard.xlsx` — real transactional data on one or
two sheets, a reference/lookup table, and an empty "Dashboard" sheet
where your real work goes. **Delete the other 3 domains' files from
`starter/` once you've chosen** — same reasoning as every prior module's
"pick one, remove the rest."

## What to do

- Open your chosen `.xlsx` in Excel (Excel Online is fine — see
  `GETTING_STARTED.md`). The raw data and reference table(s) are given
  and already formatted as real Excel Tables; the "Dashboard" sheet is
  empty except for a prompt.
- Fill in `starter/kpi_definitions.md` **before** you build anything —
  name your stakeholder, their decision, and each of your 3 KPI cards'
  role (North Star / Leading / Lagging), formula, and reasoning.
- Build your dashboard: 3 KPI cards, at least 2 real charts, at least 1
  XLOOKUP/VLOOKUP (zero `#N/A`), and one interactive "as of month"
  dropdown driving your Leading indicator's trailing-3-month-vs-prior-
  year comparison. Test the dropdown with more than one month and
  confirm the cards/chart actually update.
- Do the real data cleaning your domain's data needs — see
  `data/SOURCE.md` for the specific real issue, and document your fix in
  `kpi_definitions.md`.
- Do the 2-part AI exercise (`starter/ai_dashboard_review.md`) — a real
  AI-suggested improvement, assessed; a real AI-diagnosed misleading
  chart (using the given `starter/misleading_chart_example.xlsx`),
  verified yourself.
- Write `starter/memo.md` — one page, leads with the recommended action.

`CHECKLIST_TIMELINE.md` has the suggested day-by-day pace and the full
sequenced checklist.

**Where's the exact bar for "done," and what are the optional stretch
goals?** This repo (your own copy) doesn't include `MVP.md` (your **M**inimum **V**iable **P**roduct —
the required baseline) or `ABOVE_AND_BEYOND.md` on purpose — they're not something to keep sitting
in your portfolio repo. Ask your instructor for the link to this
template's `project-scope` branch to read them, or check the checklist
your instructor shares through the classroom, which covers the same
ground.
