# Project Estimator

An instruction-only agent skill for reviewing Word or Excel service requests and producing effort estimates for an existing Azure data/API platform.

The agent clarifies scope, proposes task and role hours, reviews contingency, and creates a compact four-sheet estimate with a relative-week Gantt chart. This repository contains Markdown guidance and skill metadata, with no Python, custom estimator engine or bundled runtime scripts.

## Install in Codex

Ask Codex to install the skill from its GitHub folder:

```text
$skill-installer install https://github.com/rajesh3007/project-estimator/tree/main/skills/project-estimator
```

Installation requires access to the repository. Codex discovers installed skills; if the skill does not appear, restart Codex.

Alternatively, copy the complete `skills/project-estimator` folder into `.agents/skills/project-estimator` in your own project. Open Codex in that project so the repository-local skill can be discovered. Keep all of the skill's referenced files together.

## Prerequisites

- An agent that can read the skill and the supplied Word `.docx` or Excel `.xlsx` request, through available document tools or native Office package operations.
- A spreadsheet writer or native Office file-writing capability to create the `.xlsx` output. The agent checks input reading and output writing separately; a connector is not mandatory for accessible local Office files.
- A scope/estimate reviewer and productive weekly capacity for the relevant roles before a weekly forecast is produced.
- A separate project folder for requests, review notes and outputs. Do not store confidential project content inside this reusable skill folder.

No API key or Python setup is required by this skill. The host still needs permission to access your files. If a particular reading/writing capability is unavailable, the agent should identify the limitation and continue with supported inputs or reviewed tables rather than claim an uncreated workbook exists.

## Use

```text
Use $project-estimator to estimate this service request: [DOCX or XLSX path].
Save notes and output in [project folder]. Confirm scope and ownership with
me before drafting hours. Propose a separate contingency with reasons.
Ask for productive weekly capacity before planning Week 1, Week 2 and so on.
```

The workflow pauses for scope and estimate decisions. You answer in ordinary language; the agent records the project inputs and performs the calculations/checks. No commands or JSON forms are needed to use the estimator.

The starter [platform profile](skills/project-estimator/platform-reference.md) targets Databricks, ODS/data layers, .NET APIs and related Azure services. Confirm it against your environment or supply your own profile. Existing example assumptions are not facts about every user's platform.

## Output

| Sheet | Content |
| --- | --- |
| Summary | Two-column project/status/scope and base/contingency/total effort summary. |
| Task Detail | Tasks, applicable role hours and totals. |
| Assumptions and Risks | Project-relevant assumptions, risks, role capacity and external dependencies. |
| Gantt Chart | Relative weeks, task/reserve effort, start/finish labels and weekly work bars. |

Hours and contingency require review. Scheduling respects confirmed capacity and dependencies; it does not infer staffing or force effort to fit a deadline. The agent keeps source evidence and detailed allocations in separate project notes.

## Skill files

The installable skill is self-contained in [skills/project-estimator](skills/project-estimator):

- [SKILL.md](skills/project-estimator/SKILL.md): entrypoint and routing.
- [INSTRUCTIONS.md](skills/project-estimator/INSTRUCTIONS.md): estimation workflow.
- [platform-reference.md](skills/project-estimator/platform-reference.md): adaptable starter platform profile.
- `references/`: document access and compact workbook-layout guidance.
- `templates/`: project brief, scope review and quality review.
- `agents/openai.yaml`: Codex UI and invocation metadata.

No real service requests, client data, output workbooks or historical project hours are distributed here. Update the workflow from demonstrated feedback without turning one project's hours, staffing or contingency into universal defaults.

## License

Licensed under the [MIT License](LICENSE), copyright 2026 rajesh3007. The installable skill also includes the license notice so it stays with downloaded copies.
