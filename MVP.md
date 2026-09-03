# MVP — the real bar for "done"

This is what actually gets graded as Meets/Approaching/Below per skill.
See instructor `rubric.md` for the full rubric if your instructor has
shared it — this is the same bar in checklist form.

## Part A — Dashboard (Excel)

- [ ] One domain chosen, its `.xlsx` kept, the other 3 deleted from
      `starter/`.
- [ ] 3 KPI cards, each explicitly labeled North Star / Leading /
      Lagging, built with real formulas (not pasted values).
- [ ] At least one of the 3 is a genuine normalized/rate metric.
- [ ] At least 2 real charts, built from live cell references.
- [ ] A working "as of month" dropdown (Data Validation) driving the
      Leading indicator's trailing-3-months-vs-same-3-months-prior-year
      comparison and its chart — **tested with 2+ different months**.
- [ ] At least 1 XLOOKUP or VLOOKUP join to a reference sheet, **zero
      `#N/A` errors**.
- [ ] References correct enough that formulas survive a row being
      inserted — actually test this, don't assume it.
- [ ] A real, domain-specific data-cleaning issue found and handled,
      with a real before/after check.
- [ ] `kpi_definitions.md`: Stakeholder A + decision, each KPI's
      role/formula/reasoning, the normalized-metric reasoning, the
      cleaning writeup, ≥2 real clarifying questions about the data.
- [ ] `ai_dashboard_review.md`: both parts completed for real.
- [ ] `memo.md`: one page, opens with the recommended action, frames
      the finding in business terms, free of unexplained jargon.

## Part B — Dashboard (Tableau Public)

- [ ] Workbook **published and publicly viewable via a real shareable
      link** — confirmed open in a private/incognito window.
- [ ] ≥4 coordinated visuals, each mapped to a real stated business
      question, chart type justified against the real chart-selection
      framework.
- [ ] **All 6 required techniques**, each graded individually (see
      `required_techniques.md`): a calculated field; a context filter
      with a real written reason it needed to be context; a LOD
      expression with a real written explanation of what it computes
      that a plain aggregate couldn't; a drill-down hierarchy (≥2
      levels); an action filter, tested and confirmed by the student;
      an analytical/statistical sheet.
- [ ] A separate, non-stakeholder-facing QA dashboard/sheet: real row
      counts, date ranges, and null checks — genuinely checked, not a
      template left unfilled.
- [ ] `kpi_notes.md`: Stakeholder B (genuinely different from
      Stakeholder A) + decision, 3-4 KPIs labeled North Star/Leading/
      Lagging, the chart-mapping table, the real data-cleaning writeup,
      ≥2 real clarifying questions.
- [ ] `ai_chart_suggestion.md`: a real AI-suggested chart type,
      validated against the real framework.
- [ ] The stakeholder walkthrough delivered (live or recorded), opening
      with the finding; a written one-paragraph takeaway free of
      dashboard-mechanics jargon; ≥1 real follow-up question answered by
      pointing at a specific visual.

## Part C — Tool comparison

- [ ] `tool_comparison.md`: a specific, concrete moment each tool was
      genuinely easier for the same kind of question — not a generic
      feature-list comparison; a real recommendation for each
      stakeholder/decision; one specific thing the two-stakeholder
      framing revealed about how the "right" KPI depends on who's
      asking.

## What "Below" looks like, concretely

- KPI cards/visuals that aren't actually differentiated by role, or
  where the two "stakeholders" are really the same decision relabeled.
- A dropdown or action filter that was built but never actually tested
  against more than one value.
- Any of Part B's 6 techniques missing, or present but not doing
  anything a simpler alternative wouldn't.
- A memo or walkthrough that opens with methodology instead of the
  recommendation/finding.
- `tool_comparison.md` that lists generic tool features instead of a
  real, specific moment from *your own* two builds.
