# Data Sources

Every domain's raw data is already built into its starter workbook
(`starter/<domain>_workbook.xlsx`) — this file documents where it's
really from. Pick one domain in `SCENARIOS.md`; you don't need to touch
this file directly, it's here for transparency about what you're working
with.

## finance_insurance — FEMA NFIP flood insurance (South Carolina)

Same real source as Module 3's own finance_insurance domain: OpenFEMA API
v3 (`NfipPolicies`/`NfipClaims`), filtered to South Carolina — U.S.
Government Work, public domain. This workbook's `Claims` and `Policies`
sheets are each a real 900-row sample (seed 42) of Module 3's own
3,000/4,000-row files; `Communities` (131 rows) is the full reference
table, unchanged. See `Module3_SQLRelational/student/data/SOURCE.md` for
the full pull methodology and known real wrinkles (missing
`amount_paid_*` values, the community-grain-only link between claims and
policies).

## professional_services — synthetic (clearly labeled)

Same synthetic data as Module 3's own professional_services domain
(`numpy`/`pandas`, seed 42 — no real firm publishes billable-hours data).
`TimeEntries` is a real 900-row sample of Module 3's 4,000-row file;
`Engagements` (220 rows) and `Clients` (60 rows) are the full tables,
unchanged.

## public_sector — real federal grant awards to South Carolina (new for this module)

**Module 3's own public_sector domain (NYC 311 service requests) doesn't
support this module's grant-spend-vs-budget framing** — 311 data has no
budget/spending concept at all. Real, different data was pulled instead.

**Source:** USASpending.gov API v2 (`api.usaspending.gov`, no auth
required), `spending_by_award` endpoint. **License:** U.S. Government
Work, public domain under 17 U.S.C. §105, per the DATA Act.

**Pull methodology:** assistance awards (grants) with place of
performance in South Carolina, awarded by the Environmental Protection
Agency or the Department of Housing & Urban Development, with an action
date in FY2022–FY2024 (2021-10-01 through 2024-09-30) — 1,223 real
awards matched. Filtered to the **10 CFDA programs** with the most SC
awards in that pull (1,072 of the 1,223 — the long tail of one-off
programs was dropped for a cleaner teaching set), then stratified-sampled
by program (seed 42) down to **249 rows** so the smaller programs stay
represented rather than getting drowned out by the largest one (Public
Housing Operating Fund, CFDA 14.850).

- `Grants` sheet (249 rows) — `award_id`, `grantee`, `awarding_subagency`,
  `cfda_number` (FK to `Programs`), `award_amount` (the real award
  ceiling — treat as "budget"), `total_outlays` (real cumulative
  disbursement as of the pull — treat as "spend"), `pct_outlaid`
  (`total_outlays / award_amount`, computed here), `start_date`,
  `end_date`, `description`.
- `Programs` sheet (10 rows, the XLOOKUP reference table) — `cfda_number`,
  `program_name` (the real CFDA program title, looked up per-award via
  USASpending's award-detail endpoint, not invented), `category` (Housing
  Assistance / Community & Economic Development / Environmental — a
  grouping judgment made for this project based on each program's real
  purpose, not an official CFDA field), `awarding_agency`.

**Real wrinkle:** `total_outlays` can slightly exceed `award_amount` on a
handful of rows (`pct_outlaid` > 1.0) — real federal award data, not a
data-entry error; outlays and award ceilings are reported through
somewhat different processes and can be briefly out of sync. `start_date`
is null on many rows in the raw API response (a real gap in this
particular data slice, not something scrubbed).

## healthcare_operations — Synthea encounters + a cited real staffing benchmark (new reference table)

Raw encounter/facility data is the same real Synthea source as Module 3's
healthcare_operations domain (synthetic patient records, Apache 2.0,
`synthea.mitre.org`) — see
`Module3_SQLRelational/student/data/SOURCE.md` for the full source
citation. `Encounters` here (900 rows) is a sample of the **40 facilities
with the most encounters** in Module 3's 5,000-row file (`patient_id`
dropped — not needed for a facility/care-setting KPI); `Facilities` (40
rows) is those same 40, in full.

**`CareUnitBenchmarks`** (the XLOOKUP reference table, 6 rows) is new for
this module — it doesn't exist in Module 3. It maps each of Synthea's 6
`encounter_class` values to a care-setting label and a target
nurse-to-patient ratio:

- **The `inpatient` row's 1:2 target is a real, cited state mandate** —
  Massachusetts General Laws Chapter 111, Section 231 (enacted via
  Chapter 155 of the Acts of 2014, effective 2014-09-28), which requires
  a 1:1 or 1:2 ICU nurse-to-patient ratio depending on patient acuity, in
  all Massachusetts acute-care hospitals. This module's Synthea facility
  data is genuinely Massachusetts-based (confirmed: all 804 facilities in
  the source file list `state = MA`), so this citation is real and
  actually applies to this data. Synthea's `inpatient` class is broader
  than "ICU specifically" (Synthea doesn't break out unit-level acuity),
  so this row is mapped as the highest-acuity tier actually present in
  the data, not a literal claim every `inpatient` encounter happened in
  an ICU bed.
- **The other 5 rows (emergency, urgentcare, outpatient, ambulatory,
  wellness) are internal targets, not state-mandated** — Massachusetts
  has no ratio law outside the ICU (a 2018 ballot measure to extend
  ratios to all units was rejected by voters). Their target ratios are
  commonly-cited industry benchmark ranges, presented as the kind of
  internal target a real hospital operations team would set for itself,
  clearly labeled in the `basis` column as not legally mandated.

**Real wrinkle:** `start_time`/`stop_time` are genuine timestamps
spanning each simulated patient's whole lifetime (some back to the early
1900s) — same as Module 3's own note on this data.
