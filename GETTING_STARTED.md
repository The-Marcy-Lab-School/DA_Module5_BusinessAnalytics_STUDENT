# Getting Started

## "Use this template" vs. Fork vs. Clone

Same rule as every project: **"Use this template"** on this repo's GitHub
page (not Fork) creates your own independent copy. Clone *that* copy, not
this template directly.

## Set up free Excel access

You don't need a paid Microsoft 365 license. Go to
[office.com](https://www.office.com), sign in with (or create) any free
Microsoft account, and open **Excel Online** from the app launcher.
XLOOKUP, native charts, and data-validation dropdowns all work in the
free web version — everything this project needs is covered. (You don't
need PivotTables for this project — the dashboard is built from KPI
cards, charts, and a dropdown, not a PivotTable summary.)
If you already have desktop Excel through school or work, that's fine
too; just make sure whatever you use actually supports XLOOKUP (a
genuinely recent function — if yours doesn't have it, use `VLOOKUP`
instead, allowed everywhere this project says XLOOKUP).

**Uploading the starter dashboard:** in Excel Online, `File → Open →
Upload and Open`, then pick your chosen `starter/<domain>_dashboard.xlsx`
from your cloned repo. Work on it there, then `File → Save As →
Download a Copy` back into `starter/` before you commit — Excel Online
saves to OneDrive by default, not your local repo folder, so this step is
easy to forget.

**A real, common Excel Online gap worth knowing about upfront:** some
advanced chart formatting or axis-scaling options are easier to reach in
desktop Excel than the web version. If you hit something Excel Online
won't let you do, that's a real, known limitation — note it in your own
writeup rather than assuming you did something wrong.

## What's next

Once Excel is set up, go back to `README.md`'s "Your domain and data"
section, pick a domain from `SCENARIOS.md`, and start with
`starter/kpi_definitions.md` before opening the spreadsheet.
