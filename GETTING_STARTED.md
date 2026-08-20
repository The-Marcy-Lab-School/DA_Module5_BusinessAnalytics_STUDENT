# Getting Started

## "Use this template" vs. Fork vs. Clone

Same rule as every project: **"Use this template"** on this repo's GitHub
page (not Fork) creates your own independent copy. Clone *that* copy, not
this template directly.

## Set up free Excel access

You don't need a paid Microsoft 365 license. Go to
[office.com](https://www.office.com), sign in with (or create) any free
Microsoft account, and open **Excel Online** from the app launcher.
PivotTables and XLOOKUP both work in the free web version — everything
this project needs is covered. If you already have desktop Excel through
school or work, that's fine too; just make sure whatever you use actually
supports XLOOKUP (a genuinely recent function — if yours doesn't have it,
use `VLOOKUP` instead, allowed everywhere this project says XLOOKUP).

**Uploading the starter workbook:** in Excel Online, `File → Open →
Upload and Open`, then pick your chosen `starter/<domain>_workbook.xlsx`
from your cloned repo. Work on it there, then `File → Save As →
Download a Copy` back into `starter/` before you commit — Excel Online
saves to OneDrive by default, not your local repo folder, so this step is
easy to forget.

## Set up Google Sheets

Any free Google account works — [sheets.google.com](https://sheets.google.com).
No new setup beyond having an account.

## How you'll actually submit the Google Sheets side

This is the one real difference from every prior project's submission
mechanics: **your Google Sheets workbook is a live cloud document, not a
file that goes in this git repo.** Here's exactly what to do:

1. Build your KPI summary in a new Google Sheet (`File → Import` your
   `.xlsx` to bring in the raw data, or start fresh — your choice).
2. Once it's done, click **Share** (top right) → under "General access,"
   change it from "Restricted" to **"Anyone with the link"** → make sure
   the role is set to **Viewer** (not Editor — you don't want it edited
   after you submit).
3. Copy the link.
4. Paste that link at the top of `starter/memo.md`, under a clear
   **"Google Sheets version:"** heading — this is the one piece of your
   submission that lives outside this repo, so the memo is where a grader
   (or a future employer looking at your portfolio) finds it.

**Double-check the link actually works in a private/incognito browser
window before you submit** — "Anyone with the link" only works if you
picked that option, not "Restricted." A broken or restricted link is a
real, avoidable point loss here.

## What's next

Once both tools are set up, go back to `README.md`'s "Your domain and
data" section, pick a domain from `SCENARIOS.md`, and start with
`starter/kpi_definitions.md` before opening the spreadsheet.
