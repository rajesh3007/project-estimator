# Estimate quality review

The agent completes this for each actual estimate. This is a review checklist, not proof that a check has passed. Record evidence, failures and unresolved limitations.

## Scope and source

- The supplied local file was checked using available file-reading methods; a missing connector was not treated as proof that the file could not be read.
- Source reading preserved the original. Relevant Word tables/paragraphs, form checks and supporting parts, or Excel cells/formulas, were checked with coverage limitations recorded.
- Each included requirement maps to tasks and relevant document section/table/row/cell or workbook/sheet/cell evidence in working notes.
- Excluded/deferred requirements attract no hours; exclusions and ownership boundaries are recorded.
- Scope confirmation is real and blocking unknowns are resolved before hours are drafted.
- No unrelated project tasks, hours, staffing or assumptions entered the estimate.

## Effort and arithmetic

- Tasks have explicit role mappings, nonnegative finite hours, rationale and predecessor IDs; positive work is not silently dropped.
- Task IDs are unique, predecessor IDs exist, and there are no self-dependencies or cycles.
- Role totals reconcile to task hours and the overall base effort.
- Contingency is project-specific, separately explained and calculated consistently.
- Base plus contingency equals total effort; scheduled role effort reconciles to that total under the stated contingency treatment.
- Spreadsheet formulas reference the intended cells and ranges. Record whether recalculation was actually verified; do not claim it based on formula text alone.
- If the user edited the workbook, actual current task/role values and formula results were read afresh. Changed reviewer hours update role totals, base effort, contingency and Gantt effort; no earlier fixed allowance is silently restored.

## Weekly plan

- Productive weekly capacity is confirmed for each role and recorded as project availability, not inferred staffing.
- No role exceeds its available capacity in any week or overlapping interval.
- Dependencies and external readiness are respected using the underlying allocation, not just the rounded week labels.
- Fractional-week work is preserved; task rounding does not inflate effort or introduce unnecessary waits.
- Independent work overlaps where allowed; shared-role conflicts are resolved.
- Alternative feasible sequences were considered where useful; explain the selected plan without claiming unproven optimality.
- Week 1 and any initial waiting weeks are preserved. A task's Start is its first positive-work week and Finish its last; Start cannot be later than Finish and no work appears outside that span.
- Weekly hours for each task/reserve reconcile to its effort, and the weekly column totals reconcile to the planned total. Positive work has the intended bar; zero/blank weeks do not look active.
- Role-level allocations support the weekly totals. Per-role and whole-team capacity limits are not confused; the treatment of SME reviews as gating or advisory is explicit.
- A requested completed Gantt actually contains weekly bars, not just task names and blank week cells. Missing capacity is resolved before calling the full planning deliverable complete.
- Missing capacity produces blank week assignments and a clear question, not an invented forecast.

## Deliverable and review

- Workbook has exactly Summary, Task Detail, Assumptions and Risks, and Gantt Chart.
- Preferred compact layout is followed: two-column summary, task/role-hour matrix with totals, project-relevant assumptions, and a compact weekly chart. Rationale, dependency ledgers, raw review/source evidence and internal verification commentary stay in working notes unless requested in the export.
- Gantt uses relative weeks, with no delivery calendar dates or extra detailed sheets.
- Row heights and column widths fit the content without excessive blank space; wrapped and merged text is readable. Distinguish actual visual inspection from structural layout checks.
- Project status and any synthetic example labeling are clear.
- Actual review records support marking the estimate reviewed. Changed effort, contingency, capacity or dependencies trigger renewed review where needed.
- Previous output versions are preserved and the new workbook can actually be opened using available tools.
- If the workbook cannot be opened/recalculated or visually inspected in the current host, distinguish the structural and arithmetic checks performed from those unverified checks.
- Final response states checks performed and any remaining limitation. Do not reuse the archived Python test count as validation of this workflow.
