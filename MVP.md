# MVP — the real bar for "done"

This is what actually gets graded as Meets/Approaching/Below per skill.
See instructor `rubric.md` for the full rubric if your instructor has
shared it — this is the same bar in checklist form.

## Dashboard (Excel)

- [ ] One domain chosen, its `.xlsx` kept, the other 3 deleted from
      `starter/`.
- [ ] 3 KPI cards, each explicitly labeled North Star / Leading /
      Lagging, built with real formulas (not pasted values).
- [ ] At least one of the 3 is a genuine normalized/rate metric (a real
      ratio with a real denominator — not just a raw count, and not just
      a mean-vs-median call).
- [ ] At least 2 real charts, built from live cell references.
- [ ] A working "as of month" dropdown (Data Validation) driving the
      Leading indicator's trailing-3-months-vs-same-3-months-prior-year
      comparison and its chart — **tested with 2+ different months**,
      not just left at the default.
- [ ] At least 1 XLOOKUP or VLOOKUP join to a reference sheet, **zero
      `#N/A` errors**.
- [ ] References correct enough that formulas survive a row being
      inserted — actually test this, don't assume it.
- [ ] A real, domain-specific data-cleaning issue found and handled
      (see `data/SOURCE.md`), with a real before/after check.

## Written work

- [ ] `kpi_definitions.md`: stakeholder + decision (one sentence), each
      KPI's role/formula/reasoning, the normalized-metric reasoning, the
      cleaning writeup, ≥2 real clarifying questions about the data's
      origin/completeness.
- [ ] `ai_dashboard_review.md`: **both** parts completed for real — a
      genuine AI-suggested improvement with your own assessment of
      whether to adopt it, and a genuine AI diagnosis of the given
      misleading chart with your own verification of whether the AI was
      right and complete.
- [ ] `memo.md`: one page, **opens with the recommended action**, frames
      the finding in business terms (revenue/cost/risk), free of
      unexplained jargon.

## What "Below" looks like, concretely

- KPI cards that aren't actually labeled North Star/Leading/Lagging, or
  where the labels don't match how the metric actually behaves.
- Every KPI is a raw count — nothing normalized/rate-based anywhere.
- A dropdown that exists but was never tested against more than one
  value, so nobody actually confirmed it drives anything.
- Charts that are really just formatted tables, or pasted-in images.
- A memo that opens with "I analyzed the dataset and found..." instead of
  the recommendation.
- The AI exercise's "verification" step just restates what the AI said,
  without the student actually checking it against the real data/chart.
