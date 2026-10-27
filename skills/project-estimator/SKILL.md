---
name: project-estimator
description: Estimate Word or Excel service requests for an existing Azure data and .NET platform, review task and role hours, and prepare a four-sheet estimate with a relative-week Gantt plan. Use for project effort estimation or revising an estimate, including ROM estimates; keep the reusable package instruction-only.
---

# Project Estimator

License: [MIT](LICENSE).

Read [INSTRUCTIONS.md](INSTRUCTIONS.md) for the workflow and [platform-reference.md](platform-reference.md) for the confirmed platform baseline before estimating a request. Follow the user's current instructions if they change scope or preferences.

Use the explicitly supplied request and gather missing inputs through conversation. Accept a local Word `.docx`, Excel `.xlsx`, accessible attachment or supplied text. Ask for a request or accessible path only if none is supplied. Do not select a previous project's request or a synthetic example without the user's choice.

Record project inputs using [templates/project-brief.md](templates/project-brief.md). Confirm scope, ownership, exclusions and blocking unknowns with [templates/scope-review.md](templates/scope-review.md) before drafting hours. Propose explicit task/role hours with reasons and a separate project-specific contingency; review them with the user before finalizing.

Plan delivery as Week 1, Week 2, Week 3 using confirmed productive role hours/week and dependencies. Improve sequencing and overlap independent work without changing effort, inventing staffing or exceeding capacity. Keep week assignments blank until capacity is confirmed.

For local Office files, follow [references/document-access.md](references/document-access.md). Prefer available document tools; if no session is connected, use existing native file operations to read the Office package. A Word or Excel connector is not a prerequisite for readable local `.docx`/`.xlsx` files. Check actual file access and applicable fallbacks before asking the user to reconnect, upload or paste a file already supplied.

Keep this package Markdown/YAML-only: no Python files, reusable automation scripts, package installs, JSON inputs or custom estimator engine. The agent may use transient native file commands and existing document/spreadsheet tools for reading and writing files. The agent performs estimation, planning and review; a connector is optional. Explain a specific remaining capability or file limitation rather than claiming success without verifying the result.

Export exactly Summary, Task Detail, Assumptions and Risks, and Gantt Chart. Apply [templates/quality-review.md](templates/quality-review.md), preserve source evidence and detailed allocations in project notes, and save versioned outputs separately from this skill. Keep estimates provisional until the user's actual review. Existing services are normally extended, and historical estimates are examples rather than hour standards.

When creating or reviewing a workbook, follow [references/workbook-layout.md](references/workbook-layout.md) for the user's preferred compact presentation. If the user edits a workbook, read its current cells, formulas and layout before relying on earlier notes. Carry reusable presentation improvements into this skill; keep that project's hours and scheduling decisions project-specific, and flag inconsistencies without silently overwriting the user's file.
