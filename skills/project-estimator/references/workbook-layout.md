# Preferred estimate workbook presentation

Use this compact presentation for new estimate workbooks unless the user requests another format. It reflects the user's edited output. It defines presentation and consistency checks, not default project hours, staffing, contingency rates or task counts.

## Summary

Use a short "Project Summary" title and two columns: measure and value. The core rows are Project, Status, Scope, Base effort (hours), Contingency rate, Contingency (hours) and Total effort (hours).

Link the effort figures to Task Detail and calculate contingency/total with spreadsheet formulas where supported. Format percentages and hours clearly, with sensible precision. Highlight the total. Keep the summary focused; do not add a third notes column, duplicate role totals or extensive review/tool commentary by default. The schedule is visible on Gantt; add a summary completion field only when useful or requested.

## Task Detail

Use one row per task, with these columns:

`Task ID | Task | applicable role-hour columns | Base hours`

For a four-role project this might mean Data Engineer, Data Analyst, .NET Developer and Technical SME between Task and Base hours. Use the roles actually agreed for the project; do not force all examples into that role set. Keep stable IDs across revisions, including gaps left by removed tasks.

Sum each task's role hours and provide a final totals row by role and overall. Preserve zero allocations consistently; they do not imply work by that role. Keep task names short and readable. Detailed rationale, requirement/source references and dependencies belong in working notes unless the user asks to export them.

Use the user's review-role label Technical SME when applicable. SME allocations are task-specific. A correction to one task's SME hours must update every affected total and schedule; it must not become a global rule for all future tasks.

## Assumptions and Risks

Use three columns: Type, Description, Status / basis. Include only information that helps the reader judge scope, delivery and uncertainty. Typical relevant rows are Population, Data assumption, API assumption, Release assumption, Risk, Weekly capacity and External dependency; add others only when material.

Avoid exporting raw hashes, chat quotations, task-removal history, internal validation logs, file-reading mechanics, formula-cache explanations or repeated ownership/scope prose. Keep that traceability in project notes. Do not hide a material exclusion, unknown data condition or dependency merely to make the sheet shorter.

## Gantt Chart

Use a short title, a compact header and these columns:

`ID | Task / reserve | Effort (h) | Start | Finish | Week 1 | Week 2 | ...`

Use one row per task, followed by a separate contingency-reserve row if that is the agreed scheduling treatment, then an effort-by-week total. Link task/reserve effort to the authoritative effort cells. Use blue for positive scheduled task work and amber for the reserve, with one concise legend. Zero or blank weeks should not look like active work. Avoid long explanatory banners; keep capacity and readiness assumptions on Assumptions and Risks, and the allocation ledger in working notes.

Derive start/finish labels from the first/last week with positive work where supported, or explicitly validate them after every edit. A task cannot start after it finishes, have work outside its stated span, or keep a Week 1 finish while containing Week 2 work. Its weekly hours must sum to its effort, and weekly column totals must reconcile to the full planned effort including the stated contingency treatment.

Weekly task totals alone do not prove role capacity or dependency feasibility. Keep a role-level within-week allocation in the project notes. Check the correct capacity basis (per role versus whole-team limits) and whether SME review is a completion gate or advisory. If user edits make those semantics unclear, flag the specific question; do not invent a new dependency model to make the displayed weeks fit.

## Formatting

- Use a consistent font, readable colored headers, light cell borders and a highlighted total row. Treat these as style preferences, not requirements for a particular theme color or font family.
- Prefer normal/automatic body-row heights and fit wrapped text only where needed. Do not add padding to every row or apply one tall height across the sheet.
- Fit column widths to content. Role names and task labels must remain readable; wider text columns should not turn every sheet into a wide commentary report.
- Left-align descriptive text and keep numerical alignment consistent with the user's workbook. Avoid arbitrary mixed alignment.
- Hide gridlines when borders provide the table structure. Freeze the actual headers; account for a title row above the table instead of freezing a hardcoded first row.
- Reuse the layout, not client content: do not bundle a real project's corrected workbook into the reusable skill as a default input or copy its hours into another estimate.

## Learning from edited workbooks

Read the current file's cells, formulas, sheet structure and stored formatting before updating the skill. Compare with the last generated record where available. Separate three kinds of changes: reusable presentation preferences, current-project hour/scope decisions, and inconsistencies needing review. Adopt the first, record the second in project notes, and flag the third without overwriting the user's workbook unless asked.
