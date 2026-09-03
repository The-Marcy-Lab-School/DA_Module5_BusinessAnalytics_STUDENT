# Above & Beyond

Optional. Do these **after** MVP is genuinely solid — a shaky MVP with
extra features isn't the goal. Pick 1-2, not all of them.

## Part A (Excel)

### A 4th KPI

A genuinely new KPI, not a trivial variant of one you already built — a
KPI that answers a different real question for Stakeholder A.

### A second interactive control

A second dropdown or control — e.g. a category filter that narrows
which rows your charts/cards reflect, on top of the existing "as of
month" selector.

### A second reference-table join

A second XLOOKUP/VLOOKUP against a different join key than your first
one.

## Part B (Tableau)

### A second action filter, or a second LOD expression

A genuinely different problem than your first one solves — not the
same mechanic copy-pasted onto a different field.

### Build Stakeholder B's core visuals in Power BI Desktop too

**Only if you have real Windows access** — Power BI Desktop doesn't run
on macOS at all, so this is genuinely optional. If you do this, add a
**third** tool to `tool_comparison.md`'s reasoning for this specific
data/decision, grounded in the real deployment tradeoff: Tableau Public
forces public data, Power BI Desktop stays private/local but has no
free path to org-wide sharing.

## Either part

### When should this graduate from a spreadsheet/one-time export to a script?

Write a short case (half a page, no code — code authorship isn't in
scope for this module) for **one of your two dashboards**: if it had to
refresh every week instead of being built once, what would actually
break or become painful about the current version, and at what point
would it be worth rebuilding as a script pulling from a live database
connection? Be concrete about *that* dashboard, not a generic answer.
(This same tradeoff gets revisited for real, with actual code, in
**Module 9**'s ETL/orchestration work.)

### A given-code cross-check back to Module 4

If you still have your Module 4 `db_connect.py`/notebook working: read
the same underlying data for one KPI via `psycopg2` or SQLAlchemy into
pandas, and compute that KPI as a cross-check against your dashboard's
number. Do they match? If not, which one do you trust, and why?
