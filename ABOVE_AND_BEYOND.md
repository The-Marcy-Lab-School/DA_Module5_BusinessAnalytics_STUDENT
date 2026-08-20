# Above & Beyond

Optional. Do these **after** MVP is genuinely solid — a shaky MVP with
extra features isn't the goal. Pick 1-2, not all of them.

## A 4th KPI

A genuinely new KPI, not a trivial variant of one you already built (e.g.
not just "the same ratio, but for a different line of business" — a KPI
that answers a different real question for your stakeholder).

## A second reference-table join

A second XLOOKUP/VLOOKUP against a different join key than your first
one — real practice with the mechanic, not a repeat of the same formula
copy-pasted.

## When should this graduate from a spreadsheet to a script?

`process_tradeoffs` for this module names a real tradeoff: a spreadsheet
is fast for a one-off answer but doesn't scale or reproduce well as the
same question recurs. Write a short case (half a page, no code — code
authorship isn't in scope for this module) for **your specific KPI
workbook**: if this same report had to run every week instead of once,
what would actually break or become painful about the spreadsheet
version, and at what point would it be worth rebuilding as a script? Be
concrete about *this* workbook, not a generic answer. (This same tradeoff
gets revisited for real, with actual code, in **Module 8**'s ETL/
orchestration work.)

## A given-code cross-check back to Module 4

If you still have your Module 4 `db_connect.py`/notebook working: read
the same underlying data for your chosen KPI via `psycopg2` or
SQLAlchemy into pandas, and compute that one KPI as a cross-check against
your spreadsheet's number. Do they match? If not, which one do you
trust, and why? (This is a preview of what this exact workflow looks like
once it graduates to a script — not a requirement to rebuild the whole
workbook in Python.)
