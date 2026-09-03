# Checklist & Timeline

**8 days, run as a sprint — genuinely tight.** Two real interactive
dashboards, for two different real stakeholders, in two different
tools, is more work than it looks. Nearly every day below compresses
2-3 days' worth of work from the standalone versions of this content —
budget your time against this checklist closely, not just the
deliverable list.

## Day 1 — Both decisions defined; data cleaning; Excel join

- [ ] `.gitignore`/`LICENSE`/git history confirmed already present;
      `LICENSE`'s `[YOUR NAME]` placeholder replaced, committed.
- [ ] Read `SCENARIOS.md`, pick one domain, delete the other 3 domains'
      Excel `.xlsx` files, `.hyper` files, and `data/` subfolders.
- [ ] Fill in `starter/kpi_definitions.md`'s "The decision" section
      (Stakeholder A) **and** `starter/kpi_notes.md`'s "The decision"
      section (Stakeholder B) — both, before building either dashboard.
- [ ] Inspect Part A's raw data (inside the `.xlsx`); identify the real
      cleaning issue (`data/SOURCE.md`).
- [ ] Build your XLOOKUP/VLOOKUP join in Excel — zero `#N/A` errors.

**Exit criterion**: both stakeholders' decisions are written down as
one sentence each, and they're genuinely different decisions, not the
same one relabeled.

## Day 2 — Excel: KPI cards + interactive Leading indicator

- [ ] Build the North Star card's formula — a real normalized/rate
      metric if it's the one you chose for that role.
- [ ] Build the Lagging indicator card's formula.
- [ ] Style both as real KPI cards.
- [ ] Build the "as of month" dropdown (Data Validation → List) and the
      trailing-3-months/same-3-months-prior-year formulas referencing
      it. **Test it**: change the dropdown to 2+ different months,
      confirm the Leading card's number actually changes each time.

**Exit criterion**: all 3 cards are real formulas, and the dropdown
demonstrably drives the Leading card when tested.

## Day 3 — Excel: charts + AI exercise + memo — Part A done

- [ ] Build 2 real charts (a trend line, a dimension breakdown), from
      live cell references.
- [ ] Complete `starter/ai_dashboard_review.md` (both parts).
- [ ] Write `starter/memo.md` — leads with the recommended action.
- [ ] Final Excel QA: no `#REF!`/`#N/A` anywhere; insert a test row and
      confirm formulas/references still work; re-test the dropdown.

**Exit criterion**: Part A (Excel) is fully done and could be submitted
on its own. Commit before moving to Part B — this is the natural
checkpoint if you're running behind.

## Day 4 — Tableau: connect, warm up, map charts, first calculated field

- [ ] Connect your data in Tableau Public (`.hyper` or CSVs).
- [ ] A brief guided warm-up: build the 3 core chart types (bar, line,
      scatter) — this should move faster than it would have standalone,
      since the chart-type/business-question mapping muscle is already
      built from Part A.
- [ ] Fill in `kpi_notes.md`'s KPI section (Stakeholder B's 3-4 KPIs)
      and chart-type-mapping table (your ≥4 business questions).
- [ ] Build your first calculated field.

**Exit criterion**: data connected, ≥4 business questions each mapped
to a justified chart type, one calculated field built.

## Day 5 — Tableau: QA dashboard + LOD + hierarchy + context filter

- [ ] Build a separate QA sheet/dashboard: row counts, date ranges, null
      checks (`starter/qa_dashboard_notes.md`) — **before** trusting
      your real dashboard's numbers.
- [ ] Build your LOD expression (document what it computes that a plain
      aggregate couldn't).
- [ ] Build your drill-down hierarchy (≥2 levels).
- [ ] Build your context filter (document *why* it needed to be
      context, not a regular filter).
- [ ] Handle the real domain-specific data-cleaning issue for this part
      (see `data/SOURCE.md`); document it in `kpi_notes.md`.

**Exit criterion**: QA dashboard shows real, checked numbers; all 3 of
these techniques are built and documented.

## Day 6 — Tableau: remaining visuals + analytical sheet + action filter

- [ ] Build all ≥4 stakeholder-facing visuals.
- [ ] Build the analytical/statistical sheet (trend line, reference
      line, or forecast).
- [ ] Build and test the action filter — click a mark on one sheet,
      confirm another sheet actually filters/highlights.

**Exit criterion**: all 6 required techniques present; ≥4 coordinated
visuals built.

## Day 7 — Publish + AI exercise + rehearse walkthrough

- [ ] Publish to Tableau Public; confirm the link is real and public
      (open it in a private/incognito window). Paste it into
      `kpi_notes.md`.
- [ ] Do the AI chart-suggestion exercise
      (`starter/ai_chart_suggestion.md`) for real.
- [ ] Rehearse your stakeholder walkthrough once out loud — cut any
      visual you can't explain in under 20 seconds.
- [ ] Field a real follow-up question during your walkthrough (live, or
      have someone ask you one before/after recording) — answer by
      pointing at a specific visual.
- [ ] Record or schedule your live walkthrough; write the one-paragraph
      takeaway free of dashboard-mechanics jargon.

**Exit criterion**: Part B (Tableau) is fully done — published,
documented, walkthrough delivered or scheduled.

## Day 8 — Tool comparison, final polish, submit

- [ ] Complete `starter/tool_comparison.md` — specific to *your* two
      dashboards, not generic.
- [ ] Re-read both parts against `SCENARIOS.md`/`required_techniques.md`;
      no placeholder `TODO` text left anywhere.
- [ ] **Delete `PROJECT_OVERVIEW.md` and `SCENARIOS.md`** — they explain
      the assignment, not your project.
- [ ] **Replace `README.md`'s content with your own real project
      README** — an Excel file isn't browsable on GitHub, and your
      Tableau dashboard lives on a separate site, so this is what a
      visitor actually reads first:
  - **Business Problem** — the domain, and both stakeholders' decisions.
  - **Part A — Excel Dashboard** — KPI definitions/rationale, key
    findings, the memo's recommendation.
  - **Part B — Tableau Dashboard** — the published link, what each
    visual shows, key insights, the walkthrough's takeaway.
  - **Tool Comparison** — your real finding from `tool_comparison.md`.
- [ ] Final commit, repo check.

## Day 9 — Share-out

Your instructor schedules this once every submission is in — usually a
few days after Day 8, not necessarily the next calendar day. Real
session, not optional: in groups of 3, you'll read 2-3 anonymized
classmates' submissions as the stakeholder each part addresses —
opening their Excel dashboard (testing the dropdown) and their
published Tableau link (clicking the action filter) — then trade
`tool_comparison.md` findings with another pair, and close with a group
reflection. Bring your finished submission — see your instructor for
the exact date.

## Submission checklist

- [ ] `starter/<your-domain>_dashboard.xlsx` — 3 labeled KPI cards, ≥2
      real charts, a working dropdown, ≥1 XLOOKUP/VLOOKUP with zero
      errors.
- [ ] `starter/kpi_definitions.md`, `starter/ai_dashboard_review.md`,
      `starter/memo.md` — Part A, all completed for real.
- [ ] A real, published, publicly-viewable Tableau Public link (in
      `kpi_notes.md`).
- [ ] `starter/kpi_notes.md`, all 6 techniques in
      `starter/required_techniques.md`, `starter/qa_dashboard_notes.md`,
      `starter/ai_chart_suggestion.md` — Part B, all completed for real.
- [ ] The stakeholder walkthrough delivered (live or recorded), a real
      follow-up question fielded.
- [ ] `starter/tool_comparison.md` completed for real.
- [ ] Other 3 domains' files deleted from `starter/` and `data/`.
- [ ] `PROJECT_OVERVIEW.md`/`SCENARIOS.md` deleted, `README.md`
      rewritten as your own real project README.
