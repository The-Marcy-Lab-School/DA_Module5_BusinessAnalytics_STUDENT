# Required Techniques

Every one of these 6 must be real and present in your published Tableau
Public workbook — not generic "≥1 filter," each is a specific, named
technique, checked individually. For each, fill in what you actually
built and why — this is graded alongside the dashboard itself.

## 1. Calculated field

**What you built:** TODO — the exact formula.
**What it computes, and why a raw column couldn't:** TODO

## 2. Context filter

Right-click a filter → "Add to Context." This changes *when* Tableau
applies it: a context filter runs first, so every other filter/
calculation operates on the already-filtered subset — this changes real
results (e.g. a Top N filter inside a context filter ranks *within* the
context, not across your whole dataset).

**What you built, and what it's set to:** TODO
**Why this specific filter needed to be context, not a regular filter**
(what would be wrong/different if it weren't): TODO

## 3. LOD expression (FIXED / INCLUDE / EXCLUDE)

**What you built:** TODO — the exact formula (`{FIXED [dimension] :
AGG([measure])}` or similar).
**What it computes that a plain aggregate on the view couldn't:** TODO
— be specific: what number would you get *without* the LOD, and why is
that number wrong/different from what you actually need?

## 4. Hierarchy

**What you built:** TODO — the dimension levels, in order.
**Where a viewer would actually use the drill-down:** TODO — which
sheet, and what real question does drilling down answer that the
top level alone couldn't?

## 5. Action filter

Dashboard → Actions → Add Action → Filter (not a plain filter card —
this has to be triggered by clicking/hovering a mark on one sheet, and
it has to filter a *different* sheet).

**What you built:** TODO — which sheet triggers it, which sheet(s) it
filters, and on what field.
**Why this makes the dashboard more useful than separate, unlinked
sheets:** TODO

## 6. Analytical / statistical sheet

A trend line, reference line, or forecast — not just a bar/line chart
with no analytical layer added.

**What you built:** TODO — which sheet, which analytical feature.
**What it tells the stakeholder that the raw chart alone wouldn't:**
TODO
