# Scenarios

Pick **one** domain. Each one names a real stakeholder and the decision
they need your dashboard to inform, plus example North Star/leading/
lagging KPIs — real starting points, not fixed requirements. You can
design your own KPIs instead, as long as they fill the same 3 roles and
one is a genuine rate/normalized metric. See `data/SOURCE.md` for exactly
where each domain's data is really from and what real cleaning issue it
has.

## Finance & Insurance

**File:** `starter/finance_insurance_dashboard.xlsx`
**Stakeholder:** VP of Underwriting, deciding whether next quarter's
reserves need adjusting.
**Raw data:** `Claims` — 3,041 **real** South Carolina NFIP flood claims,
2021–2026 (`data/SOURCE.md` has the full pull methodology). This is
genuinely event-driven data: claim volume spikes hard around real storms
(1,121 claims in September 2022 alone — Hurricane Ian). `Policies` (900
sampled policies) and `Communities` (131 rows, the XLOOKUP reference
table, join on `community_number`).
**Example KPIs:**
- *North Star* — Payout Ratio: `SUM(amount_paid_building +
  amount_paid_contents) / SUM(building_damage_amount)` — what share of
  assessed damage NFIP is actually paying out. A real rate metric, not a
  raw count.
- *Leading (= your time-series KPI)* — monthly claim volume, trailing 3
  months vs. the same 3 months one year prior. Try centering your "as of
  month" dropdown around **August–October 2024** vs. the same months in
  2023 — the real difference is dramatic and means something for a
  reserving decision.
- *Lagging* — Total Amount Paid (confirms the actual cost outcome).

## Professional Services

**File:** `starter/professional_services_dashboard.xlsx`
**Stakeholder:** Managing partner, deciding which practice area to staff
up next hiring cycle.
**Raw data:** `TimeEntries` (4,000 real-shaped time entries, Jan
2023–Nov 2024 — clean, even monthly volume, the easiest domain for a
first attempt at the trailing-3-month comparison), `Engagements` (220
rows — join on `engagement_id` to bring `hourly_rate`/`partner_assigned`
into `TimeEntries`), `Clients` (60 rows).
**Example KPIs:**
- *North Star* — Billable Utilization Rate: billable hours ÷ total hours
  logged. A real rate metric.
- *Leading (= your time-series KPI)* — monthly billable hours, trailing
  3 months vs. same 3 months prior year.
- *Lagging* — Realized Revenue (billable hours × hourly rate, summed).

## Healthcare Operations

**File:** `starter/healthcare_operations_dashboard.xlsx`
**Stakeholder:** Hospital operations director, deciding where to shift
staffing hours next scheduling cycle.
**Raw data:** `Encounters` (900 real encounter records, 2019–2021) and
`Facilities` (the 40 real facilities they occurred at). Reference sheet:
`CareUnitBenchmarks` — join on `encounter_class` to bring in each care
setting's target nurse-to-patient ratio (the ICU-tier figure is a real,
cited Massachusetts state mandate — see `data/SOURCE.md`).
**Example KPIs:**
- *North Star* — Cost per Encounter: `SUM(total_claim_cost) /
  COUNT(encounter_id)`, by care setting. A real rate metric.
- *Leading (= your time-series KPI)* — monthly encounter volume,
  trailing 3 months vs. same 3 months prior year (data ends Nov 2021 —
  frame this as "as of the most recent data in this file").
- *Lagging* — Total Claim Cost (confirms the actual outcome).

## Public Sector

**File:** `starter/public_sector_dashboard.xlsx`
**Stakeholder:** State grants management director, deciding whether to
flag a federal grant program for reallocation before its award period
closes out.
**Raw data:** `Grants` — 249 real federal grant awards to South Carolina
recipients (EPA/HUD, FY2022–2024). Reference sheet: `Programs` — join on
`cfda_number` to bring in each program's real name/category.
`MonthlyObligations` — 36 real months of aggregate SC grant-obligation
totals (a genuinely different, coarser-grained real dataset — see
`data/SOURCE.md` — this is what supports your time-series KPI, since the
award-level `Grants` data doesn't have real month-to-month granularity).
**Example KPIs:**
- *North Star* — % of Grant Funds Outlaid: `total_outlays /
  award_amount`, by program. A real rate metric, already in `Grants`
  as `pct_outlaid`.
- *Leading (= your time-series KPI)* — monthly grant obligations (from
  `MonthlyObligations`), trailing 3 months vs. same 3 months prior year.
- *Lagging* — Total Outlays (confirms actual spend).

## Once you've picked

Delete the other 3 domains' `.xlsx` files from `starter/`. Start with
`starter/kpi_definitions.md`, not the dashboard.
