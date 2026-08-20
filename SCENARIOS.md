# Scenarios

Pick **one** domain. Each one names a real stakeholder and the decision
they need your KPI summary to inform — write that decision down first
(`exemplar_guidance`'s own advice), then work backward to which 3 KPIs
actually answer it. See `data/SOURCE.md` for exactly where each domain's
data is really from.

## Finance & Insurance

**Workbook:** `starter/finance_insurance_workbook.xlsx`
**Stakeholder:** VP of Underwriting, deciding whether next quarter's
reserves and premiums need adjusting for a specific line of business.
**Raw data sheet:** `Claims` (900 claims) and `Policies` (900 policies).
**Reference sheet (for your XLOOKUP):** `Communities` — community-level
attributes to join against a `community_number` on your claims/policies.
**Framing:** loss-ratio and budget-variance by line of business. A high
loss ratio on one line, or a claim volume badly out of line with what was
budgeted for it, is exactly the kind of finding that changes a premium or
reserve decision next quarter.

## Healthcare Operations

**Workbook:** `starter/healthcare_operations_workbook.xlsx`
**Stakeholder:** Hospital operations director, deciding where to shift
staffing hours next scheduling cycle.
**Raw data sheet:** `Encounters` (900 real encounter records) and
`Facilities` (the 40 real facilities they occurred at).
**Reference sheet (for your XLOOKUP):** `CareUnitBenchmarks` — join on
`encounter_class` to bring in each care setting's target nurse-to-patient
ratio and its basis (see `data/SOURCE.md` — the ICU-tier ratio is a real,
cited Massachusetts state mandate; the rest are internal targets, clearly
labeled as such).
**Framing:** patient-census and staffing-utilization by care setting. A
setting running consistently above its target ratio is understaffed
relative to demand — the kind of finding that should move real hours.

## Public Sector

**Workbook:** `starter/public_sector_workbook.xlsx`
**Stakeholder:** State grants management director, deciding whether to
flag any federal grant program for reallocation before the award periods
close out.
**Raw data sheet:** `Grants` — 249 real federal grant awards to South
Carolina recipients (EPA and HUD, FY2022–2024, from usaspending.gov).
**Reference sheet (for your XLOOKUP):** `Programs` — join on
`cfda_number` to bring in each program's real name and category (Housing
Assistance / Community & Economic Development / Environmental).
**Framing:** grant-spend-vs-budget by program. `award_amount` is the
budget; `total_outlays` is what's actually been spent so far. A program
running well behind its `pct_outlaid` pace late in its award period is a
real reallocation-risk signal.

## Professional Services

**Workbook:** `starter/professional_services_workbook.xlsx`
**Stakeholder:** Managing partner, deciding which practice area to staff
up next hiring cycle.
**Raw data sheet:** `TimeEntries` (900 logged time entries, joined to
`Engagements` via `engagement_id`) and `Engagements` (220 client
engagements).
**Reference sheet (for your XLOOKUP):** `Clients` — from the
`Engagements` sheet, join on `client_id` to bring in client
industry/region.
**Framing:** billable-utilization and revenue-per-consultant. A practice
area with high utilization *and* strong revenue-per-consultant is the
one worth staffing up first — the kind of comparison a managing partner
actually needs across areas, not just one number in isolation.

## Once you've picked

Delete the other 3 domains' `.xlsx` files from `starter/`. Start with
`starter/kpi_definitions.md`, not the spreadsheet.
