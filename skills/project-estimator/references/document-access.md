# Reading requests and writing workbooks

## Instruction-only package and agent operations

This skill packages guidance, not an executable estimator. Do not ship Python, reusable parser/generator scripts, dependencies or a custom scheduling engine. Existing agent tools and transient native file-reading/writing commands are permitted to handle the actual documents. The agent still owns interpretation, calculations, planning and review. Do not ask the user to run those commands.

## Check actual capabilities first

1. Identify the supplied source: local path, attachment, document link or pasted text. Check that the specified file exists and is readable. Do not search unrelated folders for alternative project content.
2. Use an available tool that can read that source. Connected document sessions are useful when present, but are not required for local Office package reading.
3. For a readable local `.docx` or `.xlsx`, use existing native archive/XML operations if no suitable document tool is available. On Windows, PowerShell's existing .NET compression and XML facilities can inspect these formats without Python, installing a package, launching Office or changing the source. Keep any working files in the project area; do not create reusable scripts in the skill.
4. Ask for an alternative representation only after the applicable available methods fail. Report the actual failure: inaccessible path, protected/encrypted package, unsupported format, missing document part or content that requires visual inspection. Do not treat a missing connector as a missing file.

Do not execute document macros or embedded objects. Open source packages read-only and leave them unchanged. Parse XML with external entity resolution disabled and DTD processing prohibited. Do not follow linked files or download private linked sources silently; keep unread linked material explicit. Avoid exposing unrelated local files.

## Word `.docx`

Inspect the Office package and its main `word/document.xml` part. Preserve body order, paragraph breaks, headings, tables and row/cell boundaries rather than flattening the entire XML into one string. Decode text and preserve checked versus unchecked form values. Use readable references such as the section title and `Table 5 / Row 1 / Cell 2`. Record that table/paragraph ordinals refer to the source package structure, not fabricated Word page numbers.

Check for comments, tracked insertions/deletions, text boxes, headers/footers, footnotes/endnotes, pictures and embedded files. Read relevant text-bearing parts; distinguish substantive requirements from repeated header/footer text. Do not silently assume that a main-part text read captures content stored only in images or embedded files. Flag tracked changes for interpretation rather than silently treating both old and new text as final scope.

Detect hyperlinks and list relevant unread dependencies in the working notes. A link in the intake does not establish the contents of the linked document. Preserve source identity; a native file hash can help verify that reading did not change the original.

## Excel `.xlsx`

Inspect `xl/workbook.xml` and workbook relationships to identify sheet names and their actual part targets. Resolve shared-string indices through `xl/sharedStrings.xml` when present and also support inline strings. Keep cell addresses, worksheet names, merged-range context, stored formulas and cached values distinct. Do not interpret a missing formula cache as zero or claim to have recalculated Excel formulas merely by reading their text. Interpret dates using the workbook date system and cell number formats rather than mistaking every numeric value for a date.

Check hidden sheets, comments, drawings, external links and embedded content for requirements needing attention. Confirm scope from the actual evidence, not just the first visible sheet. Native package reading may not reproduce calculated values or visual layout; state the limits that matter for the supplied request.

## Output and validation

Check for a supported spreadsheet writer or available native Office file-writing operations early. A document reader and workbook writer are separate capabilities. When using native package writing, create a real Office Open XML workbook, not CSV/HTML renamed to `.xlsx`. Use the four-sheet specification from `INSTRUCTIONS.md`, version the output and preserve previous workbooks.

Verify the package contains the expected workbook, worksheet and relationship parts, correct sheet names, literal input text and intended formulas or labeled calculated values. Inspect values, source-to-task coverage, role totals, contingency, dependency order, capacity and weekly bars. Use a spreadsheet tool to open/recalculate or visually inspect when available. Distinguish structural/arithmetic checks from actual spreadsheet-engine recalculation and visual inspection.

If a specific capability is absent, continue scope and estimate review with project notes and reviewed tables where possible. Report what was actually produced and the exact remaining limitation. Never promise that instructions can supply file access or tools absent from the host environment.
