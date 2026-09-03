# Data Sources

Two data shapes per domain, one per part of this project:

- **Part A (Excel)**: raw data is already built into
  `starter/<domain>_dashboard.xlsx` — you don't need to touch this file
  directly for that half.
- **Part B (Tableau)**: raw data is the `.hyper` extract plus mirrored
  CSVs in `data/<domain>/` (this folder).

For `finance_insurance` and `professional_services`, Parts A and B use
the **same underlying real data** — just two different stakeholders'
questions asked of it (see `SCENARIOS.md`). For `healthcare_operations`
and `public_sector`, Parts A and B use **genuinely different real
datasets** — two different departments within the same broader domain
(see `SCENARIOS.md` for why).

## finance_insurance — real South Carolina NFIP flood claims

**Source:** OpenFEMA API, `FimaNfipClaims` dataset, South Carolina,
`dateOfLoss >= 2021-01-01`. **License:** U.S. Government Work, public
domain. Same source and same rows in both parts — see
`Module3_SQLRelational/student/data/SOURCE.md` for the full citation.
**Note for future maintainers:** FEMA's own API response flags the v2
dataset for removal around October 2026 in favor of a v3 successor.

- `Claims` — real claim-level rows: `claim_id`, `community_number` (FK
  to `Communities`), `date_of_loss`, `cause_of_damage`,
  `occupancy_type`, `amount_paid_building`, `amount_paid_contents`,
  `building_damage_amount`, `net_building_payment`, `rated_flood_zone`,
  `zip_code`.
- `Policies` and `Communities` (the reference/join table) reused as-is
  from Module 3's own finance_insurance domain.

**Real wrinkle (the cleaning issue this domain gives you, both parts):**
genuinely event-driven data — claim volume spikes hard around real
storms (1,121 claims in September 2022 alone, Hurricane Ian; 390 and
360 in August/September 2024; 336 in December 2023). Not something to
"clean away" — it's the real signal your time-series KPI should
surface — but a naive average-per-month figure is deeply misleading
without checking for this skew first.

**Part B only, a real data-availability limit:** the NFIP claims schema
has no claim-settlement-date field, only `date_of_loss` — there's no
real way to compute a literal "average settlement time." Reframe
honestly (claim aging as of a fixed snapshot date, or a different real
KPI the data actually supports) and document the choice.

## professional_services — synthetic (clearly labeled), same source both parts

Same synthetic data as Module 3's own professional_services domain
(`numpy`/`pandas`, seed 42 — no real firm publishes billable-hours
data). `TimeEntries` (the full 4,000-row file), `Engagements` (220
rows), `Clients` (60 rows) — identical in both parts.

**Real wrinkle (the cleaning issue this domain gives you, both parts):**
`hours` is right-skewed (lognormal); 6 rows have a planted negative
`hours` value, and ~160 rows (~4%) have a missing `hours` value. Both
need to be excluded from any KPI that sums or averages `hours`.

**A real, honest limitation worth naming in either part:** this dataset
has no distinct "standard rate vs. actual billed rate" concept —
`hourly_rate` functions as both, so a literal "realization rate" can't
be computed as genuinely different from utilization rate here. Document
this if you choose that framing, rather than presenting two numbers as
if they measured different things.

## healthcare_operations — two real, different departments

**Part A (Excel) — hospital `Encounters`:** Synthea synthetic patient
records (Apache 2.0), same source as Module 3's healthcare_operations
domain. `Encounters` (900 rows, the 40 facilities with the most
encounters) and `Facilities` (40 rows). `CareUnitBenchmarks` (the
reference/join table) maps each `encounter_class` to a target
nurse-to-patient ratio — the `inpatient` row's 1:2 target is a real,
cited state mandate (Massachusetts General Laws Chapter 111, Section
231), genuinely applicable because this pull's facility data is itself
Massachusetts-based.

**Real wrinkle, Part A:** `start_time`/`stop_time` span each simulated
patient's whole lifetime (some back to the early 1900s) — filtering to
a real, recent, usable date range (2019–2021) is itself a real cleaning
step.

**Part B (Tableau) — clinic `Appointments`:** the same real Synthea
encounter source, 900 of the same sampled records, renamed
`Appointments` here, **augmented** with two new columns not in Part A's
data: `wait_minutes` and `no_show` — synthetic, but grounded in real
citations (`wait_minutes` for the `emergency` class calibrated to CMS's
real Timely and Effective Care data, ~143-minute median ED time;
`no_show` adds 199 synthetic scheduled-but-unattended rows at a ~20%
rate, grounded in a real, commonly-cited 23-33% outpatient no-show
range). `Facilities` (40 rows) reused.

**Real wrinkle, Part B:** the synthetic no-show rows have
`stop_time`/`total_claim_cost`/`wait_minutes` genuinely blank (`NaN`) —
intentional (a no-show never happened, so there's no duration/cost/wait
to report), not missing data to fill in.

**Why two different datasets for one domain**: Part A's hospital
`Encounters` data has no wait-time/no-show concept at all — a hospital
operations director staffing by care setting and a clinic operations
manager triaging wait times are two genuinely different real
departments asking two genuinely different real questions of two
genuinely different (though related) datasets.

## public_sector — two real, different agencies

**Part A (Excel) — state `Grants`:** real federal grant awards to South
Carolina recipients. **Source:** USASpending.gov API, SC place of
performance, EPA + HUD awarding agencies, FY2022–2024, stratified-
sampled to 249 rows. `Programs` is the reference/join table.
`MonthlyObligations` (36 real months) supports the time-series KPI,
since award-level `start_date` clusters in January (an issuance
artifact, not a spending pattern).

**Real wrinkle, Part A:** `total_outlays` can slightly exceed
`award_amount` on a handful of rows (`pct_outlaid` > 1.0) — a real
federal reporting artifact, not a data-entry error.
`MonthlyObligations` is itself lumpy (real obligation timing) — the
same "don't average away a real spike" lesson as finance_insurance's
data.

**Part B (Tableau) — city `Permits`:** real NYC Department of Buildings
permit-issuance data. **Source:** NYC Open Data, "DOB Permit Issuance"
(Socrata `ipu4-2q9a`), filtered to `permit_status = 'IN PROCESS'` and
the last 3 years (1,109 real records). **License:** NYC Open Data
Law — public domain. Non-PII columns only. `PermitTypes` is the
reference table.

**Real wrinkle, Part B:** the full "IN PROCESS" dataset (before this
starter's 3-year filter) has a heavily long-tailed age distribution —
median age ~15 years, mostly administratively stale filings, not an
active backlog. This starter data is pre-filtered for a genuinely
active-backlog framing (median age ~1.8 years).

**Why two different datasets for one domain**: Module 3/6's own
public_sector data (grants) has no permit-backlog concept at all, and
the reverse is also true — state grants-management and city
permit-review are two genuinely different real public-sector agencies,
asking two genuinely different real questions of two genuinely
different real datasets.
