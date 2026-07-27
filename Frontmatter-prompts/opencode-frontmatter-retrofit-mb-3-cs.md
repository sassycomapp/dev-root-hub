Task: Front-matter retrofit — mb-3-cs-project-library.
Scope is strictly limited to: C:\dev\dev-mb-3-cs\mb-3-cs-project-library\
Do not touch any other repo or folder.

Context: No document in this repo currently has a front-matter block. Every
in-scope document needs one added. This is a one-time retrofit to prepare
this repo for the mb-align-docs skill, which enforces front-matter-based
rules going forward but does not yet run against real content. This same
retrofit has already been completed for project-library-global.

Front-matter fields to add, per front-matter-schema.md
(C:\projects-reference\custom-skills-store\mb-align-docs\front-matter-schema.md):
  - document: the document's title (use the file's first heading if one
    exists, otherwise derive a reasonable title from the filename)
  - doc-id: assigned sequentially as "mb-3-cs-0001", "mb-3-cs-0002", etc.,
    in the order documents are listed (alphabetical by relative path)
  - state: Live (every in-scope document is Live — see exclusions below)
  - date-created: if the document already states its own creation date
    internally (e.g. a "**Date:**" line in the body), use that value in
    preference to the filesystem date. Otherwise use the file's actual
    filesystem creation date if available; if neither is available, use
    today's date in UTC+2 (the developer's local/PC time) and mark it in
    the report as "assumed, not actual"

Date format for date-created: YYYY-MM-DDTHHMMSS+0200 (Filename-Safe ISO
8601, UTC+2), per the timestamp standard in global-0037. A date-only value
(YYYY-MM-DD) is acceptable only where an internal document date was found
and no time was originally stated.

In scope: all .md documents inside mb-3-cs-project-library's content
folders (adr-local, checklists-local, docs-local, docs-standard-local,
policy-local, pre-project, screens, specifications-local,
standard-operating-procedures-local, templates-local, register-local,
agents, prompts-local, and any other genuine document-bearing folder not
listed in the exclusions below).

Excluded from this task entirely — do not add front matter, do not list:
  - Anything inside a folder named "obsolete" (retired content is outside
    front-matter scope)
  - Anything inside Quarantine (currently empty, but excluded on principle)
  - .git, .gstack, .opencode, .scratch, gstack-outputs, matt-skills-output,
    opencode-outputs, workspace, wip, V2, or any other tool/operational/
    output folder — these are not canonical documents
  - Historical/log files: output-opencode/, judgement-trail.md,
    devlog-index.md — valid historical records, not live documents
  - Any file that is not a document (binaries, images, etc.)

Step 1 — Precondition check.
Confirm the mb-3-cs-project-library git working tree is clean before
proceeding. If dirty, stop and report — do not proceed.

Step 2 — Backup.
Take a full backup of mb-3-cs-project-library before any write. Save the
backup to C:\backups-general\backup-mb-align-docs_<timestamp>\, where
<timestamp> is YYYY-MM-DDTHHMMSS+0200 (Filename-Safe ISO 8601, UTC+2).

Step 3 — Detect and propose, no writes yet.
List every in-scope document with its proposed front-matter block
(document, doc-id, state, date-created). Present as a single table:
relative file path | document | doc-id | state | date-created.

Step 4 — Approval.
Present the full list for one batch approval, since every entry receives
the same uniform treatment (all Live, no exceptions expected). Flag
separately, for individual attention, any file where a title could not be
reasonably derived, or where neither an internal date nor a filesystem
creation date was available.

Step 5 — Apply.
Only after approval, add the approved front-matter block to each document,
one file at a time. Re-read each file immediately after writing to confirm
the front matter was inserted correctly and no other content in the file
was altered.

Step 6 — Report.
Confirm total documents updated, and list any skipped or flagged items
with the reason.

Hard constraints:
  - No writes before Step 1 and Step 2 are complete.
  - No writes without the Step 4 approval.
  - Never alter any content in a document other than inserting the
    front-matter block at the top.
  - Never touch excluded folders under any circumstance.
