Task: Fix ADR references in mb-align-docs skill files.
Scope is strictly limited to:
C:\projects-reference\custom-skills-store\mb-align-docs\
Do not touch any other repo or folder.

Context: The mb-align-docs skill package cites the timestamp standard ADR
by doc-id ("global-0037") only, in at least these five files: SKILL.md,
front-matter-schema.md, register-template.md, alignment-log-template.md,
quarantine-provenance-template.md. The agreed fix is to reference the
ADR's real file path directly, so an agent doesn't need a working register
lookup to find the mechanism:
C:\dev\project-library-global\adr-global\timezone-utc-storage-display-conversion.md

Step 1 — Scan first, do not assume the file list above is complete.
Search every file in scope (including mb-align-docs-function-scope.md,
finding-report-format.md, mb-align-docs-detector.md,
mb-align-docs-writer-text.md, mb-align-docs-writer-structural.md,
mb-align-docs-logger.md, and anything in learnings\) for any reference to
"global-0037" or to the timestamp/ADR by name, not only the five files
named above. Report every match found, with file name and the exact line
of text, before making any change.

Step 2 — Propose the replacement, no writes yet.
For each match found, propose the replacement text: keep the doc-id
reference if useful for readability, but add the real file path
immediately alongside it, e.g. "the timestamp standard (global-0037,
C:\dev\project-library-global\adr-global\timezone-utc-storage-display-conversion.md)"
— or the closest natural phrasing that fits the surrounding sentence in
each file. Present all proposed changes as a table: file name | current
text | proposed text.

Step 3 — Approval.
Present the full list for one batch approval, since every entry receives
the same uniform treatment (add the real path alongside the existing
doc-id reference).

Step 4 — Apply.
Only after approval, apply each approved change, one file at a time.
Re-read each file immediately after writing to confirm the change was
applied correctly and no other content in the file was altered.

Step 5 — Report.
Confirm total files changed, list them, and confirm no matches were left
unaddressed. If Step 1 found matches beyond the five files named in
Context, call that out explicitly in the report — do not fold it in
silently as if it was expected.

Hard constraints:
  - No writes before Step 1 (scan) and Step 2 (proposal) are complete.
  - No writes without the Step 3 approval.
  - Never alter any content in a file other than the ADR reference itself.
  - Never touch any file outside
    C:\projects-reference\custom-skills-store\mb-align-docs\
