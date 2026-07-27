Task: Front-matter retrofit — project-library-global.
Scope is strictly limited to: C:\dev\project-library-global\
Do not touch any other repo or folder.

Context: No document in this repo currently has a front-matter block. Every
in-scope document needs one added. This is a one-time retrofit to prepare
this repo for the mb-align-docs skill, which enforces front-matter-based
rules going forward but does not yet run against real content.

Front-matter fields to add, per front-matter-schema.md
(C:\projects-reference\custom-skills-store\mb-align-docs\front-matter-schema.md):
  - document: the document's title (use the file's first heading if one
    exists, otherwise derive a reasonable title from the filename)
  - doc-id: assigned sequentially as "global-0001", "global-0002", etc.,
    in the order documents are listed (alphabetical by relative path)
  - state: Live (every in-scope document is Live — see exclusions below)
  - date-created: use the file's actual filesystem creation date if
    available; if not available, use today's date and mark it in the
    report as "assumed, not actual"

In scope: all .md documents inside project-library-global's content
folders (adr-global, checklists-global, docs-standard-global, guides,
policy-global, specifications-global, standard-operating-procedures-global,
templates-global, register-global).

Excluded from this task entirely — do not add front matter, do not list:
  - Anything inside a folder named "obsolete" (retired content is outside
    front-matter scope)
  - Anything inside Quarantine (currently empty, but excluded on principle)
  - .git, .gstack, .opencode, .scratch, gstack-outputs, matt-skills-output,
    opencode-outputs, workspace, or any other tool/operational folder —
    these are not canonical documents
  - Any file that is not a document (binaries, images, etc.)

Step 1 — Precondition check.
Confirm the project-library-global git working tree is clean before
proceeding. If dirty, stop and report — do not proceed.

Step 2 — Backup.
Take a full backup of project-library-global before any write.

Step 3 — Detect and propose, no writes yet.
List every in-scope document with its proposed front-matter block
(document, doc-id, state, date-created). Present as a single table:
relative file path | document | doc-id | state | date-created.

Step 4 — Approval.
Present the full list for one batch approval, since every entry receives
the same uniform treatment (all Live, no exceptions expected). Flag
separately, for individual attention, any file where a title could not be
reasonably derived, or where filesystem creation date was unavailable.

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
