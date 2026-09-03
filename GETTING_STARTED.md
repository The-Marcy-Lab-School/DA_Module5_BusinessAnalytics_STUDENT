# Getting Started

## "Use this template" vs. Fork vs. Clone

Same rule as every project: **"Use this template"** on this repo's GitHub
page (not Fork) creates your own independent copy. Clone *that* copy, not
this template directly.

## Set up free Excel access (Part A)

You don't need a paid Microsoft 365 license. Go to
[office.com](https://www.office.com), sign in with (or create) any free
Microsoft account, and open **Excel Online** from the app launcher.
XLOOKUP, native charts, and data-validation dropdowns all work in the
free web version. If you already have desktop Excel through school or
work, that's fine too; just make sure it actually supports XLOOKUP (use
`VLOOKUP` instead if not).

**Uploading the starter dashboard:** in Excel Online, `File → Open →
Upload and Open`, then pick your chosen `starter/<domain>_dashboard.xlsx`
from your cloned repo. Work on it there, then `File → Save As →
Download a Copy` back into `starter/` before you commit.

**A real, common Excel Online gap worth knowing about upfront:** some
advanced chart formatting or axis-scaling options are easier to reach in
desktop Excel than the web version. If you hit something Excel Online
won't let you do, note it in your own writeup rather than assuming you
did something wrong.

## Set up Tableau Public (Part B)

Go to [public.tableau.com](https://public.tableau.com), create a free
account, and download **Tableau Public Desktop** (available for both Mac
and Windows — this is why this project uses Tableau Public as the one
required tool, not Power BI Desktop, which only runs on Windows).

**The one real tradeoff to understand before you start**: Tableau Public
workbooks are **publicly visible to anyone** once published — there's no
private-publish option on the free tier. That's genuinely fine for every
domain's data in this project — but it's a real, professional habit
worth understanding for future work, and directly feeds
`starter/tool_comparison.md`'s own reasoning: if your actual employer's
data needed to stay private, Tableau Public wouldn't be the right tool
(Power BI Desktop's local-only free tier would be, or Tableau's paid
Server/Cloud tiers).

**Connecting your data:** see `starter/tableau_dashboard_README.md` —
two ways to connect (the given `.hyper` extract, or the plain CSVs),
same data either way.

**Publishing your workbook:** `Server → Tableau Public → Save to Tableau
Public`. Sign in with the free account you just created. This gives you
a real, public, shareable link — paste it in `starter/kpi_notes.md`'s
top line, and reference it in your walkthrough.

## What's next

Once both tools are set up, go back to `README.md`'s "Your domain and
both stakeholders" section, pick a domain from `SCENARIOS.md`, and start
with `starter/kpi_definitions.md` **and** `starter/kpi_notes.md` — both
stakeholders' decisions, defined before you open either tool.
