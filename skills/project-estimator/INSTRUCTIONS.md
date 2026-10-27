# Project estimation instructions for the agent

Use these instructions when the user asks to estimate a service request against the existing Azure platform. The agent performs the work using supplied documents, conversation and available file/document tools. Keep the reusable skill instruction-only: do not add Python files, reusable automation scripts, package installs, JSON inputs or a custom estimator engine. The agent may issue transient native file-reading/writing commands and use existing document/spreadsheet tools. The user does not write code, run commands or configure a connector to make an accessible local Office file readable. Follow the user's current scope and preferences.

## Read the request and confirm scope

Read `platform-reference.md` and the explicitly supplied service request. Keep every project's evidence, notes and outputs separate. Do not import business content, staffing, hours or assumptions from unrelated projects. If previous estimates are explicitly supplied, use them as examples to discuss, not established hour standards.

Accept Word `.docx` and Excel `.xlsx` requests, attachments or explicitly supplied text. Follow `references/document-access.md` for capability checks and native local file fallbacks. An empty list of connected document sessions does not mean the local file is unreadable. Preserve file identity and references in working notes: workbook/sheet/cell for Excel, or section/paragraph/table/row/cell for Word. Include cross-cell context and checked/unchecked form values. Try the applicable permitted fallback before asking the user to upload or paste an accessible file. If reading remains impossible, explain the specific cause and request only what is missing. Do not invent extracted requirements.

Use `templates/project-brief.md` to record the user's answers through conversation; do not make the user fill it out unless they prefer that. Identify affected components, included scope, exclusions, deferred work, owning teams, ownership boundaries, testing and release responsibilities, dependencies, assumptions, risks and important unknowns.

Shared platform services already exist. Projects normally extend them. Include new platform construction only when explicitly needed by the confirmed scope. Treat unconfirmed platform patterns as questions rather than facts. Add a newly confirmed reusable pattern to the platform reference only with the user's confirmation; keep project-specific assumptions in that project's notes.

Confirm scope with the user before drafting hours. Use `templates/scope-review.md` to make the review concrete. Resolve unknowns that prevent meaningful estimation, and record remaining questions with their impact. Never manufacture a confirmation or reviewer record.

## Draft and review effort

Break the confirmed scope into reviewable tasks. Give each task an ID, description, affected components, role hours, rationale and predecessor task IDs. Keep its source requirement references in working notes; preserve useful requirement IDs in Task Detail when relevant, without creating a Requirements sheet.

Relevant default roles are Data Engineer, Data Analyst, .NET Developer, DevOps Engineer and Technical SME. Use the user's preferred review-role label; do not add Solution Architect as a duplicate of Technical SME. Include only applicable roles. Confirm any additional or ambiguous role rather than silently remapping it. Team ownership is separate from role.

Allocate hours to the roles actually doing each task, rather than spreading effort across every role. Analyst discovery, Engineer dataset implementation and .NET response changes may have different owners; combined testing may involve all of them. Confirm the ownership for the project. Review/SME hours can vary by task: preserve the user's latest allocations rather than applying an example's fixed one- or two-hour allowance universally. Keep task rationale and dependencies in working notes even when they are omitted from the exported table.

Explain proposed hours in terms of the actual changes and necessary verification, integration and release work. Include testing/reconciliation when it belongs in scope. Do not substitute sample tasks when project information is missing. Every included requirement needs task coverage; excluded or deferred work must not attract hours.

Propose contingency separately for this project, explaining the uncertainty it addresses. Show base effort, contingency effort and total effort separately. Do not assume a universal rate or hide contingency inside unexplained hours. Review tasks, role hours, rationale, dependencies and contingency with the user. Keep the estimate PROVISIONAL until reviewed.

## Plan delivery in relative weeks

Use Week 1, Week 2, Week 3 rather than delivery calendar dates. Ask for confirmed productive hours per week available to this project for each relevant role. Role capacity is the total available capacity after other commitments, not an assumed headcount or a universal 40-hour week. Show these values in Assumptions and Risks.

Record whether a capacity limit is per role, shared across the whole team, or both. An aggregate weekly total can exceed an individual role's limit when different roles work in parallel; do not silently reinterpret a confirmed per-role limit as a team-wide cap. Confirm whether SME review is advisory, may overlap, or gates the next task instead of automatically making every review a serial dependency.

Estimated hours alone do not establish duration: 80 role hours at 20 available hours/week requires four weeks of that role's work before contingency and dependencies. If weekly capacity is missing, present effort only and leave week assignments blank with a clear capacity question.

If the user requests a completed weekly Gantt, gather missing capacity before delivering a workbook described as complete. An approved effort estimate alone does not complete the weekly-plan deliverable. Once capacity is confirmed, populate start/finish weeks and actual weekly bars, with a separate contingency allowance and explicit external-readiness assumptions.

Build a working allocation that accounts for each task's hours by role, predecessor completion and available capacity. Include the proposed/reviewed contingency consistently and explain its treatment; the default planning treatment is to distribute the allowance proportionally across role effort while keeping it separately reported in Summary. Allow fractional weeks internally so short tasks do not each consume a whole week.

Optimize the plan by running independent work in parallel, filling usable capacity gaps and prioritizing tasks that unblock longer chains of dependent work. Compare feasible alternative sequences where shared roles compete. Choose the shorter feasible completion, without reducing estimated hours, inventing staff, removing dependencies or fitting effort to a requested deadline. Explain any tradeoff. Do not claim a mathematically shortest plan without evidence.

Respect finish-to-start task dependencies and any confirmed external readiness week. A dependent task can begin within the same displayed week when its predecessor actually finishes and capacity remains. Separate tasks when handoffs between roles require stricter order. Different roles within a task may work in parallel only where the work allows it.

Preserve initial waiting weeks. Model a task's externally constrained earliest start explicitly. Do not quietly omit external wait times. Assume constant weekly capacity only if the user accepts it; represent varying capacity and blocked weeks explicitly when supplied. Week labels round the presentation, not the underlying effort. Work filling the first week's capacity finishes in Week 1; work starting after that capacity finishes starts in Week 2.

## Create the four-sheet workbook

Use available spreadsheet tools or existing native Office file-writing operations. Do not add Python or reusable runtime scripts to this instruction package. Check output capability early, separately from input reading; do not interrupt scope review merely because no connector is active. If no permitted way to create a valid workbook is available, explain the specific limitation and provide reviewed tables while retaining the project notes. Never label another file format as `.xlsx` or claim an uncreated workbook exists.

Export exactly these sheets:

| Sheet | Content |
| --- | --- |
| Summary | Compact two-column project/status/scope and base effort, contingency rate/hours and total effort. Avoid a long explanatory notes column or duplicate role-total section. |
| Task Detail | One task per row; Task ID, Task, applicable role-hour columns and Base hours, with role/overall totals. Keep rationale, source mappings and dependencies in working notes unless specifically requested in the export. |
| Assumptions and Risks | Concise project-relevant population, data/API/release assumptions, material risks, weekly capacity and external dependencies, using Type / Description / Status or basis. |
| Gantt Chart | Compact task/reserve rows, effort, start/finish weeks and weekly hours shown in colored bars, with totals and one concise legend. |

Do not export separate Requirements, Planning, Daily Allocation or Source Cells sheets. Keep detailed evidence and allocation checks in project working notes. A Gantt bar means some work occurs in that week, not necessarily full-week utilization. Do not imply a task works continuously through gaps without explaining the display.

Keep effort totals connected to Task Detail with spreadsheet formulas where supported. Use clearly labeled calculated values when formulas cannot be verified. Preserve literal user text instead of treating it as spreadsheet formulas. Format the workbook for readability and label synthetic examples clearly.

Use compact, content-based row heights and moderate column widths; avoid applying a tall fixed height to every body row. Shorten display labels where helpful while preserving rationale in the project notes. Check wrapped/merged text for clipping. Weekly Gantt bars must match the actual allocation; distinguish task work from any separately planned contingency and explain what bar values represent.

Apply `references/workbook-layout.md` for the preferred presentation. Keep hashes, verbatim chat approvals, revision history, generator/tool limitations and detailed verification logs in project notes rather than filling the workbook with internal process commentary. Retain material uncertainties and exclusions wherever the reader needs them to interpret the estimate.

## Check, review and preserve versions

Apply `templates/quality-review.md` before sharing each workbook. Check coverage, role mappings, hours, totals, contingency, formula ranges, dependency cycles/order, per-role capacity and Gantt consistency. State what was checked and any unverified calculations or tool limitations. Report only checks actually performed on the current artifact; earlier checks do not validate a changed estimate.

Review the concrete estimate, contingency, staffing/capacity and dependencies with the user before marking it reviewed. Record actual review evidence only after confirmation. If any of these change, identify the affected review and keep the revision provisional until reviewed again.

Use versioned filenames such as `<project-id>_provisional_v001.xlsx` and preserve existing versions. Explain remaining uncertainty without presenting assumptions as facts. The skill entrypoint is `SKILL.md`; estimating a request does not itself authorize Git publication or changes to installed skills.

When reviewing user-edited output, inspect the actual file and discover the current headers and ranges; rows/columns may have moved or been removed. Treat explicit edited task hours as the current project input and reconcile totals, contingency, weekly allocations, labels and notes. Report ambiguous changes or inconsistent schedules instead of silently retaining obsolete numbers or calling contradictory data correct. A request to learn from a workbook does not authorize changing that workbook: preserve it and update only the requested guidance and review notes.
