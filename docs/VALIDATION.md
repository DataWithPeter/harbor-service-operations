# Validation notes

Checked 18 October 2026 against the synthetic snapshot ending 30 September 2026.

## Native model checks

The unchanged native DAX runners passed 232 cases against reviewed reference outputs (35,059 compared values), plus five supplemental cases (62 values). Actual results came from the running Power BI engine and were compared on the Mac using the existing comparator. No substitute measures or Python-generated actual results were used.

The original frozen reference retains nine previously reviewed differences: seven format-string expectations and two build-specific sparse-date diagnostics. These are unchanged; the pass above refers to the reviewed reference, not the original frozen baseline.

## Queue compatibility

The public-compatible queue removes a numbered visual calculation and orders tickets by overdue status, priority, remaining working hours and ticket reference. The equivalent ordering was checked across 669 snapshot dates and 126,882 rows. Data, model measures and business rules were unchanged.

Native and signed-in browser checks confirmed both January P2 drillthrough routes return the same eight tickets in order, with 8 open, 4 overdue, 0 due soon and 1 awaiting a first response. Queue sorting, overdue filtering, Reset, Back and separation between ordinary pages and drillthrough destinations were also checked.

Anonymous publish-to-web validation also passed: all four normal pages rendered with expected defaults, the normal and selected queues supported Age sorting and Reset, All/Overdue toggles worked, and both January P2 drillthrough routes returned the same eight ticket IDs and urgency order. A fresh opening of the unchanged public URL returned the default Overview. The public endpoint initially served the prior definition after replacement; the corrected queue was observed working at 19:56 UTC, followed by these interaction checks.

## Accepted limitations

- An intermittent accessibility value can retain the previous Summary month after the year changes, while the visible slicer and analytical context correctly show All. No complete fix or root cause is claimed.
- Forward keyboard focus in Power BI Desktop can repeatedly reach More options. Reverse traversal and a sampled Ctrl+Enter navigation action worked, but complete keyboard and screen-reader accessibility is not certified. Mouse-based browser validation does not remove these observations.
- This is a fixed portfolio snapshot. External CSV paths require configuration before refresh in a different environment. No scheduled refresh, gateway or live service-desk integration is claimed.
- Response-time observations were bounded manual checks, not a controlled performance benchmark or service-level guarantee.

All business records are synthetic. These checks demonstrate consistency of the case study; they do not establish real operational impact.
