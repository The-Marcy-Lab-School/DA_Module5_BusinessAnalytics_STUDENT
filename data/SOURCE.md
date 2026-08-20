# Data Sources

Every domain's raw data is already built into its starter dashboard
(`starter/<domain>_dashboard.xlsx`) — this file documents where it's
really from and each domain's real, documented cleaning issue. Pick one
domain in `SCENARIOS.md`; you don't need to touch this file directly.

## finance_insurance — real South Carolina NFIP flood claims (2021–2026)

**Source:** OpenFEMA API v2, `FimaNfipClaims` dataset
(`fema.gov/api/open/v2/FimaNfipClaims`), filtered to South Carolina,
`dateOfLoss >= 2021-01-01`. **License:** U.S. Government Work, public
domain under 17 U.S.C. §105. Pulled live from the API, not a static
download. **Note for future maintainers:** FEMA's own API response flags
this v2 dataset for removal around **October 2026** in favor of a
successor `NfipRedactedClaims` v3 dataset — re-pull from the v3 endpoint
if rebuilding this after that date.

- `Claims` (3,041 rows — 16 rows with a `community_number` not present
  in `Communities` were excluded, see below) — `claim_id`,
  `community_number` (FK to `Communities`), `date_of_loss`,
  `cause_of_damage`, `occupancy_type`, `amount_paid_building`,
  `amount_paid_contents`, `building_damage_amount`,
  `net_building_payment`, `rated_flood_zone`, `zip_code`.
- `Policies` (900 sampled rows, seed 42) and `Communities` (131 rows,
  the XLOOKUP reference table) reused as-is from Module 3's own
  finance_insurance domain — see
  `Module3_SQLRelational/student/data/SOURCE.md` for their full
  citation.

**Real wrinkle (the cleaning issue this domain gives you):** this is
genuinely event-driven data, not a smooth trend — claim volume spikes
hard around real storms: **1,121 claims in September 2022** (Hurricane
Ian), **390 in August 2024** and **360 in September 2024** (the 2024
Atlantic season), **336 in December 2023**. Most other months have
single- or low-double-digit counts. This isn't something to "clean away"
— it's the real signal your time-series KPI should surface — but it does
mean a naive average-per-month figure is deeply misleading without
checking for this skew first.

## professional_services — synthetic (clearly labeled), same as Module 3

Same synthetic data as Module 3's own professional_services domain
(`numpy`/`pandas`, seed 42 — no real firm publishes billable-hours data).
`TimeEntries` here is the **full 4,000-row file** (not a sample, for
real monthly time-series density); `Engagements` (220 rows) and
`Clients` (60 rows) are the full tables, unchanged.

**Real wrinkle (the cleaning issue this domain gives you):** `hours` is
drawn from a right-skewed (lognormal) distribution — most entries are
small, a few are large. **6 rows have a negative `hours` value** (planted
data-entry errors) and **160 rows (~4%) have a missing `hours` value**.
Both need to be excluded from any KPI that sums or averages `hours` —
included by mistake, they will quietly distort your North Star and
Leading indicator numbers.

## healthcare_operations — Synthea synthetic patient records, same as Module 3

Same real source as Module 3's healthcare_operations domain (Synthea,
Apache 2.0, entirely synthetic — see
`Module3_SQLRelational/student/data/SOURCE.md` for the full citation).
`Encounters` (900 rows, the 40 facilities with the most encounters) and
`Facilities` (40 rows) reused as-is. `CareUnitBenchmarks` (6 rows, the
XLOOKUP reference table) maps each `encounter_class` to a target
nurse-to-patient ratio — the `inpatient` row's 1:2 target is a real,
cited state mandate (Massachusetts General Laws Chapter 111, Section 231,
1:1/1:2 ICU ratio by acuity), genuinely applicable because this pull's
Synthea facility data is itself Massachusetts-based (confirmed: all 804
source facilities list `state = MA`). The other 5 rows are internal
targets, not state-mandated — Massachusetts has no ratio law outside the
ICU.

**Real wrinkle (the cleaning issue this domain gives you):** `start_time`/
`stop_time` are genuine timestamps spanning each simulated patient's
whole lifetime (some back to the early 1900s) — filtering to a real,
recent, usable date range (2019–2021, where this sample's real density
actually is) is itself a real cleaning step, not just a display choice.

## public_sector — real federal grant data, extended for this module

**Award-level data** (`Grants`, `Programs`) is unchanged from the
original build — see the original pull methodology below.
**`MonthlyObligations` is new for this dashboard redesign** — the
award-level `Grants` data has no real month-to-month activity signal
(award `start_date` clusters in January, a grant-issuance artifact, not
a spending pattern), so a genuinely different, coarser-grained real
dataset was pulled to support the time-series KPI.

**Source (Grants/Programs):** USASpending.gov API v2
(`api.usaspending.gov`), `spending_by_award` endpoint, SC place of
performance, EPA + HUD awarding agencies, FY2022–2024, the 10
most-represented CFDA programs, stratified-sampled to 249 rows.
**Source (MonthlyObligations, new):** the same API's
`spending_over_time` endpoint, same filters, **grouped by month** — 36
real months (Jan 2022–Dec 2024) of aggregate SC grant-obligation totals.
**License (both):** U.S. Government Work, public domain, DATA Act.

- `Grants` (249 rows) — `award_id`, `grantee`, `awarding_subagency`,
  `cfda_number` (FK to `Programs`), `award_amount`, `total_outlays`,
  `pct_outlaid`, `start_date`, `end_date`, `description`.
- `Programs` (10 rows, the XLOOKUP reference table) — `cfda_number`,
  `program_name`, `category`, `awarding_agency`.
- `MonthlyObligations` (36 rows) — `calendar_month`, `obligations`.

**Real wrinkle (the cleaning issue this domain gives you):**
`total_outlays` can slightly exceed `award_amount` on a handful of
`Grants` rows (`pct_outlaid` > 1.0) — real federal reporting artifact,
not a data-entry error. `MonthlyObligations` is itself lumpy (real
obligation timing, not smooth activity — e.g. $130M in one single month
from a large award being obligated) — the same "don't average away a
real spike" lesson as finance_insurance's data, on a different domain.
