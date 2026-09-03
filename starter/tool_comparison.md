# Tool Comparison: Excel vs. Tableau

Complete this **after** both dashboards are done — this is a real
comparison of two things you actually built, not a hypothetical. Be
specific to *your* domain's two decisions, not a generic "Tableau has
more features" writeup.

## 1. One concrete moment the same kind of question was easier in one tool

Pick a specific mechanic — not "Tableau was harder overall." Example
shape: "Building the trailing-3-month comparison in Excel was a single
formula referencing the dropdown cell; the equivalent in Tableau needed
a LOD expression plus a parameter, because Tableau's aggregation model
recalculates per-view by default." Name the actual mechanic, not a
vibe.

## 2. One concrete moment the same kind of question was easier in the other tool

Same bar as above, the other direction. Example shape: "Publishing a
shareable, clickable link for Stakeholder B took one step in Tableau;
the equivalent in Excel would mean either sharing the raw file (anyone
can edit it) or exporting static images (losing the interactivity
entirely)."

## 3. When would you recommend each tool?

For **your specific two stakeholders and decisions** — not tools in the
abstract:

- Audience's technical comfort — would Stakeholder A/B rather receive a
  file they can edit themselves, or a link they just click?
- Does the decision need a live, shareable, public-facing artifact, or
  is a private file handed to one person enough?
- Iteration speed — which tool let you go from "I have an idea for a
  new cut of this data" to "I can see it" faster, for *this* data?
- What would break, or become painful, if this dashboard had to refresh
  every week instead of being built once? (Same tradeoff
  `ABOVE_AND_BEYOND.md` names for Excel alone — now compare both tools
  against it directly.)

## 4. What the two-stakeholder framing itself revealed

You built two dashboards from data that's the same or closely related,
for two different real audiences. Name one specific way the "right"
KPI, chart, or cut of the data genuinely depended on *who* was asking —
not just which tool you happened to be using at the time.
