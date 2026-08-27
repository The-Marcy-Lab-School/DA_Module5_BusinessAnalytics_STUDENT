# Project Overview: Business Analytics — Excel KPI Dashboard

## The objective

Pick one of 4 real stakeholder domains (`SCENARIOS.md`), then build a
real, interactive **Excel dashboard** — not a static report — for the
specific decision that stakeholder needs to make. Your dashboard needs:

- **3 KPI cards**, each explicitly labeled as a **North Star**, a
  **Leading indicator**, or a **Lagging indicator** — a real business-
  analytics framework, not three arbitrary numbers. At least one must be
  a genuine **normalized/rate metric** (a ratio with a real denominator
  — a utilization rate, a payout ratio, a cost-per-unit — not just a raw
  count, and not just "pick mean or median").

  **What North Star/Leading/Lagging actually mean:** a North Star is the
  one number that best answers "is this decision going well right now."
  A Leading indicator moves early, giving warning before the North Star
  does — useful because it's still possible to act on it. A Lagging
  indicator confirms a past outcome after the fact, once it's already
  too late to change it. Example: for a subscription business, trial
  signups this week are a Leading indicator (an early signal), Monthly
  Recurring Revenue is the North Star (the current state of the
  business), and last quarter's churn rate is Lagging (a confirmed
  outcome you can no longer undo). See `starter/kpi_definitions.md` for
  how to apply this to your own dashboard.
- **At least 2 real charts** (a trend line, a dimension breakdown bar
  chart, etc.) built from live formulas, not pasted-in images.
- **One real interactive control** — a dropdown that lets a user pick an
  "as of" month, which drives your Leading indicator's **trailing
  3-months-vs-the-same-3-months-one-year-prior** comparison and its
  chart.
- **At least one XLOOKUP or VLOOKUP** joining your raw data to a
  reference table, zero `#N/A` errors.
- **Real data cleaning** — every domain's data has a genuine, documented
  issue (see `data/SOURCE.md`); find it, handle it, show your work.
- **A 2-part AI exercise**: ask an AI assistant for a real improvement
  to your dashboard and assess it; then ask an AI assistant to identify
  what's misleading about a given chart and verify its answer yourself.
- **A one-page stakeholder memo** that leads with the recommended
  action, not the methodology.

This is **Excel only** — no parallel Google Sheets build this time.

## Why it matters

A dashboard someone can actually open, click through, and trust is a
different skill than a one-time analysis. Choosing the right North Star/
leading/lagging framing for a real decision, picking a metric that's
genuinely comparable (not just a raw count that happens to be biggest),
and building something that survives a stakeholder clicking the dropdown
themselves — that's the real, portfolio-worthy skill this project tests.
**Module 6** builds a dashboard from data shaped exactly like what you
build here, on a different tool (Tableau/Power BI) — the underlying
KPI-framing skill carries directly.

## Deliverables at a glance

- One domain chosen from `SCENARIOS.md`, its dashboard `.xlsx` kept, the
  other 3 deleted.
- 3 KPI cards (North Star, Leading, Lagging), at least one a real
  normalized/rate metric, each defined in `kpi_definitions.md` with a
  formula, and reasoning for why it fills that role.
- At least 2 real charts sourced from live formulas.
- A working "as of month" dropdown driving the trailing-3-month-vs-
  prior-year comparison and its chart — tested with more than one
  selected month.
- At least 1 XLOOKUP/VLOOKUP, zero `#N/A` errors, references that
  survive a row being inserted.
- A real, documented data-cleaning fix specific to your domain's actual
  issue.
- `starter/ai_dashboard_review.md` completed for real: an AI-suggested
  dashboard improvement (assessed, not just accepted), and an AI-
  identified misleading-chart diagnosis (verified, not just trusted).
- At least 2 specific, real clarifying questions about your data's
  origin/completeness.
- `starter/memo.md`: one page, leads with the recommended action.

## Skills you'll practice

- **Excel** — real dashboard-building: KPI cards, native charts, a
  working interactive control, XLOOKUP/VLOOKUP, reference discipline
  that survives a row insert.
- **KPI Development** — the North Star/leading/lagging framework, and
  choosing the right denominator for a metric to actually be comparable.
- **Business Acumen** — framing a finding in terms of revenue, cost, or
  risk.
- **Attention to Detail** — zero formula errors, correct references, an
  interactive control that actually works when tested.
- **Stakeholder Communication** — a memo that leads with the action.
- **Critical Thinking** — questioning your data's origin/completeness,
  and verifying an AI assistant's visual-design judgment instead of
  trusting it outright.

## Timeline

7 days. See `CHECKLIST_TIMELINE.md` for the day-by-day sprint pace and
the full submission checklist.

## Where to start

Go to `README.md`, then `GETTING_STARTED.md` for free Excel setup.
