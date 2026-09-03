# KPI Definitions

Fill this in **before** you build the dashboard — name the decision
first, work backward to which KPIs actually inform it.

## The decision

**Stakeholder (role, not a name — Stakeholder A, see `SCENARIOS.md`):** TODO
**Decision this dashboard needs to inform:** TODO — one sentence.

## Your 3 required KPI cards

Every dashboard needs exactly these 3 roles filled — a **North Star**
(the one number that best answers "is this decision going well"), a
**Leading indicator** (moves early, before the North Star does — this is
also your interactive, trailing-3-months-vs-same-3-months-prior-year
metric, see below), and a **Lagging indicator** (confirms a past outcome
after the fact, once it's already too late to change it). Real
dashboards use all three because they answer different questions: North
Star = "how are we doing right now," Leading = "what's about to happen,"
Lagging = "what already happened and can't be undone."

### North Star

- **Name:** TODO
- **Formula:** TODO — exact.
- **Why this is the North Star and not just "a metric":** TODO — what
  decision changes if this number moves?
- **Is this a normalized/rate metric, or a raw count?** TODO — a raw
  count (total claims, total encounters) is rarely a good North Star on
  its own, because it isn't comparable across time periods or
  categories of different sizes. Explain the denominator you chose and
  why it's the right one — this is a broader judgment call than just
  "mean vs. median," it's "what's the right basis for comparison at
  all." (At least one of your 3 KPIs must be a real rate/normalized
  metric — this is the natural place for it.)

### Leading indicator (= your time-series KPI)

- **Name:** TODO
- **Formula:** TODO
- **Why this moves before the North Star does:** TODO
- **Time window:** trailing 3 months vs. the same 3 months one year
  prior, driven by the "as of month" dropdown on your dashboard.
- **Mean or median, if relevant:** TODO — check the underlying
  variable's real distribution shape before choosing, same Module 2
  habit as always, if this KPI involves averaging individual values
  rather than summing a total.

### Lagging indicator

- **Name:** TODO
- **Formula:** TODO
- **Why this only confirms the outcome, rather than predicting it:** TODO

## Data cleaning

**What real issue did you find in your raw data, and how did you handle
it?** Every domain's data has at least one genuine, documented issue
(check `data/SOURCE.md` for your domain's specific one) — don't assume
it away. Name the issue, show a real before/after check (a row count, a
sum, a null count), and explain what you did about it and why.

TODO

## Clarifying questions about the data

Before trusting a dashboard built on this data, what would you actually
want to ask whoever originally collected/exported it? At least 2, real
and specific to your dataset.

1. TODO
2. TODO
