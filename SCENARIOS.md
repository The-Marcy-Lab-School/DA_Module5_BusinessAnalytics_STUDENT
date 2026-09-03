# Scenarios

Pick **one** domain. Every domain now has **two real stakeholders** —
one for your Excel dashboard (Part A), one for your Tableau dashboard
(Part B) — deciding two genuinely different things, not the same
decision twice in two tools. See `data/SOURCE.md` for exactly where
each part's data is really from.

## Finance & Insurance

**Part A — Excel.** File: `starter/finance_insurance_dashboard.xlsx`.
**Stakeholder:** VP of Underwriting, deciding whether next quarter's
reserves need adjusting.
**Example KPIs:**
- *North Star* — Payout Ratio: `SUM(amount_paid_building +
  amount_paid_contents) / SUM(building_damage_amount)`.
- *Leading* — monthly claim volume, trailing 3 months vs. same 3
  months one year prior. Try centering around **August–October 2024**
  vs. the same months in 2023.
- *Lagging* — Total Amount Paid.

**Part B — Tableau.** Data: `starter/finance_insurance_extract.hyper`
(or `data/finance_insurance/`).
**Stakeholder:** VP of Claims Operations, deciding where to route
additional claims-adjuster staffing capacity ahead of next storm
season — a genuinely different decision than Part A's reserve call,
from the same real claims data.
**Business questions:**
1. Which communities have the highest claim frequency — where is
   adjuster capacity most needed right now? (geography — map by
   `zip_code`)
2. How has monthly claim volume trended, and where are the real spikes
   that would require surge staffing? (trend)
3. How does claim severity vary by occupancy type and community
   together — which claims need a senior adjuster, not a generalist?
   (relationship)
4. What is the loss ratio by occupancy type — which claim types take
   the most adjuster time per dollar? (comparison)
**Technique ideas:** calculated field = claims per adjuster-week
proxy (claim count); LOD = total claims per community, independent of
whatever dimension the view is sliced by; hierarchy = Community → Zip
Code; context filter = fix to one occupancy type, then rank communities
within it.

## Professional Services

**Part A — Excel.** File: `starter/professional_services_dashboard.xlsx`.
**Stakeholder:** Managing partner, deciding which practice area to
staff up next hiring cycle.
**Example KPIs:**
- *North Star* — Billable Utilization Rate: billable hours ÷ total
  hours logged.
- *Leading* — monthly billable hours, trailing 3 months vs. same 3
  months prior year.
- *Lagging* — Realized Revenue (billable hours × hourly rate, summed).

**Part B — Tableau.** Data: `starter/professional_services_extract.hyper`
(or `data/professional_services/`).
**Stakeholder:** VP of Business Development, deciding which client
industry to prioritize for new-business outreach next quarter — a
sales-facing decision, distinct from Part A's internal staffing call,
from the same real time-entry data.
**Business questions:**
1. What is revenue by client industry — which industries generate the
   most billable revenue today? (comparison)
2. How has utilization trended month over month — is there real spare
   capacity to take on new clients? (trend)
3. How does a partner's utilization relate to their realized revenue —
   which partners are best positioned to lead new-industry pitches?
   (relationship — scatter)
4. What is client concentration within each industry (e.g. top-client
   share of that industry's revenue) — a real diversification-risk
   read for a BD target list? (comparison)
**Technique ideas:** calculated field = utilization rate, realized
revenue; LOD = each client's first engagement date, independent of the
view's date filter; hierarchy = Service Type → Partner → Client;
context filter = fix to one service type, then rank partners within it.

## Healthcare Operations

**Part A — Excel.** File: `starter/healthcare_operations_dashboard.xlsx`.
**Stakeholder:** Hospital operations director, deciding where to shift
staffing hours next scheduling cycle. Data: hospital `Encounters`.
**Example KPIs:**
- *North Star* — Cost per Encounter, by care setting.
- *Leading* — monthly encounter volume, trailing 3 months vs. same 3
  months prior year (data ends Nov 2021 — frame as "as of the most
  recent data in this file").
- *Lagging* — Total Claim Cost.

**Part B — Tableau.** Data: `starter/healthcare_operations_extract.hyper`
(or `data/healthcare_operations/`).
**Stakeholder:** Clinic operations manager, deciding where to shift
staffing hours next scheduling cycle — a genuinely different real
department (outpatient clinic, not inpatient hospital) with genuinely
different data (`Appointments`, with real wait-time/no-show fields
hospital `Encounters` doesn't have).
**Business questions:**
1. What is average wait time by care setting and hour of day?
   (comparison)
2. What is the no-show rate by care setting? (comparison)
3. How has appointment volume trended by month? (trend)
4. Where are the facilities located? (geography — map by
   `Facilities.state`/`city`)
**Technique ideas:** calculated field = no-show rate, a wait-time
bucket; LOD = each facility's average wait time, independent of the
view's care-setting filter; hierarchy = State → City → Facility;
context filter = fix to one care setting, then rank facilities within
it.

## Public Sector

**Part A — Excel.** File: `starter/public_sector_dashboard.xlsx`.
**Stakeholder:** State grants management director, deciding whether to
flag a federal grant program for reallocation before its award period
closes out. Data: state `Grants`.
**Example KPIs:**
- *North Star* — % of Grant Funds Outlaid: `total_outlays /
  award_amount`, by program (already in `Grants` as `pct_outlaid`).
- *Leading* — monthly grant obligations (from `MonthlyObligations`),
  trailing 3 months vs. same 3 months prior year.
- *Lagging* — Total Outlays.

**Part B — Tableau.** Data: `starter/public_sector_extract.hyper` (or
`data/public_sector/`).
**Stakeholder:** City planning director, deciding whether to reallocate
review staff toward a specific permit type or borough with a growing
backlog — a genuinely different real agency (city permitting, not
state grants-management) with genuinely different data (`Permits`).
**Business questions:**
1. How many open (in-process) permits are there by age bucket?
   (comparison)
2. Which boroughs/community boards have the largest backlog?
   (geography/comparison)
3. How has new permit-filing volume trended? (trend)
4. What's the permit-type breakdown of the current backlog?
   (comparison)
**Technique ideas:** calculated field = permit age in days
(`TODAY() - [filing_date]`), an age bucket; LOD = each community
board's average backlog age, independent of the view's borough filter;
hierarchy = Borough → Community Board; context filter = fix to one
borough, then rank permit types within it.

## Once you've picked

Delete the other 3 domains' Excel `.xlsx` files, `.hyper` files, and
`data/` subfolders. Start with `starter/kpi_definitions.md` (Part A)
**and** `starter/kpi_notes.md` (Part B) — define both stakeholders'
decisions on Day 1, before opening either tool. See
`CHECKLIST_TIMELINE.md` for pacing.
