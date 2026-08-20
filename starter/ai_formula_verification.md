# AI Formula Verification

`ai_integration_notes` for this module is explicit: ask an AI assistant to
suggest a KPI or XLOOKUP formula, then **manually verify it against a
small hand-checked sample** before accepting it into your workbook — the
same verify-before-trust habit this curriculum has already asked for with
SQL (Module 3) and Python (Module 4), just not yet under its own graded
skill_id.

## The prompt you gave the AI assistant

TODO — paste your real prompt, verbatim. Something like: "Write an Excel
XLOOKUP formula that looks up `community_number` from my Claims sheet in
my Communities reference table and returns `community_name`."

## What it suggested

TODO — paste the raw formula it gave you, unedited, even if it turned out
wrong.

## Your manual check

Pick 3–5 rows **by hand** — pick the actual row, look up the actual
answer yourself (scroll to the reference sheet, find the match, read the
value), and compare:

| Row | Expected (you found it manually) | Formula's actual result | Match? |
|-----|-----------------------------------|--------------------------|--------|
| TODO | TODO | TODO | TODO |
| TODO | TODO | TODO | TODO |
| TODO | TODO | TODO | TODO |

## What you found

TODO — did it work as-given, or did you have to fix something (a wrong
range, a missing `_xlfn.` compatibility quirk if writing it outside the
UI directly, an absolute-vs-relative reference mistake, a data-type
mismatch between the two sheets)? Real AI-suggested formulas commonly get
close but not quite right on the exact match column/range — say what was
actually wrong, not just "it worked."
