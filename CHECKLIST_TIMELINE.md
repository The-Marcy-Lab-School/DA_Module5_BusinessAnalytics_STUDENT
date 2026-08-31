# Checklist & Timeline

**7 days, run as a sprint.** A real interactive dashboard is more work
than it looks — cards, charts, and a working dropdown all have to stay
correct together, not just look right once.

## Day 1 — Pick the decision and domain, not the dashboard

- [ ] `.gitignore`/`LICENSE`/git history confirmed already present;
      `LICENSE`'s `[YOUR NAME]` placeholder replaced with your actual
      name, committed.
- [ ] Read `SCENARIOS.md`, pick one domain, delete the other 3 `.xlsx`
      files from `starter/`.
- [ ] Fill in `starter/kpi_definitions.md`'s "The decision" section —
      name your stakeholder and their decision in one sentence, *before*
      naming a single KPI.
- [ ] Inspect the raw data. Identify your domain's real cleaning issue
      (see `data/SOURCE.md`).

## Day 2 — Data cleaning + the XLOOKUP/VLOOKUP join

- [ ] Handle the real cleaning issue; document a real before/after check.
- [ ] Build your XLOOKUP/VLOOKUP join to the reference sheet — zero
      `#N/A` errors.

## Day 3 — North Star + Lagging KPI cards

- [ ] Build the North Star card's formula — make sure it's a real
      normalized/rate metric if it's the one you chose for that role.
- [ ] Build the Lagging indicator card's formula.
- [ ] Style both as real KPI cards (a clear label, a large number, a
      short sub-label) — not a bare formula in a cell.

## Day 4 — The interactive Leading indicator

- [ ] Build the "as of month" dropdown (Data Validation → List).
- [ ] Build the trailing-3-months / same-3-months-prior-year formulas
      referencing the dropdown cell.
- [ ] **Test it**: change the dropdown to 2+ different months, confirm
      the Leading card's number actually changes each time.

## Day 5 — Charts

- [ ] Build a trend-line chart for your Leading indicator's monthly
      history.
- [ ] Build a second chart — a dimension breakdown (by category,
      program, partner, care setting, etc.).
- [ ] Confirm both charts are built from live cell references, not
      pasted-in images or hardcoded values.

## Day 6 — The AI exercise + written KPI reasoning

- [ ] Complete `starter/ai_dashboard_review.md` Part 1 (a real
      AI-suggested improvement, assessed) and Part 2 (a real AI-diagnosed
      misleading chart, verified yourself against
      `misleading_chart_example.xlsx`).
- [ ] Finish `starter/kpi_definitions.md` — every KPI's role, formula,
      and reasoning; the normalized-metric reasoning; ≥2 clarifying
      questions about the data.

## Day 7 — Memo, finish, verify, submit

- [ ] Write `starter/memo.md` — lead with the recommended action.
- [ ] Re-read your own `memo.md` (and `kpi_definitions.md`) as if you
      were the stakeholder, not the analyst: flag any term a
      non-technical reader wouldn't understand (`XLOOKUP`, "structured
      Table," "normalized metric," etc.) and either cut it or explain it
      in plain language.
- [ ] Final QA pass: no `#REF!`/`#N/A` anywhere; insert a test row into
      your raw data and confirm formulas/references still work; re-test
      the dropdown one more time.
- [ ] Commit and push.

## Day 8 — Share-out

Your instructor schedules this once every submission is in — usually a
few days after Day 7, not necessarily the next calendar day. Real
session, not optional: after a brief group readout of each memo's
recommendation, you'll work in groups of 3, reading 2-3 anonymized
classmates' `memo.md` and dashboard `.xlsx` as the stakeholder they're
addressed to — opening the actual dashboard, testing the "as of month"
dropdown, and filling in a shared peer-review doc before reporting
patterns back to the room. Nothing extra to prepare beyond your own
submission — see your instructor for the exact date.

## Submission checklist

- [ ] `starter/<your-domain>_dashboard.xlsx` — 3 labeled KPI cards
      (North Star/Leading/Lagging, ≥1 a real normalized/rate metric), ≥2
      real charts, a working interactive dropdown, ≥1 XLOOKUP/VLOOKUP
      with zero errors.
- [ ] `starter/kpi_definitions.md` — stakeholder/decision, each KPI's
      role/formula/reasoning, the real data-cleaning writeup, ≥2
      clarifying questions.
- [ ] `starter/ai_dashboard_review.md` — both parts completed with real
      prompts/responses and your own verification.
- [ ] `starter/memo.md` — one page, leads with the action.
- [ ] Other 3 domains' dashboards deleted from `starter/`.
- [ ] **Delete `PROJECT_OVERVIEW.md` and `SCENARIOS.md`** — they explain
      the assignment, not your project; a real portfolio repo shouldn't
      have "here's what you were asked to build" sitting in it.
- [ ] **Replace `README.md`'s content with your own real project README**
      — an Excel file isn't browsable on GitHub, so this is what a
      visitor actually reads:
  - **Business Problem** — the decision and domain you picked.
  - **KPI Definitions & Rationale** — your North Star/Leading/Lagging
    picks and why.
  - **Key Findings** — what the dashboard actually shows.
  - **Recommendations** — the action from `memo.md`, restated here.
