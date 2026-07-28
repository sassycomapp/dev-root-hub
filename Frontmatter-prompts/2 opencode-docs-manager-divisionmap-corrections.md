Task: Correct backup-path inconsistency and a missing folder entry across
Docs Manager and division-map documents.
This is a plain documentation-correction task — it does not invoke either
Docs Manager or mb-align-docs as a skill, and does not depend on either
skill's own outputs. Scope is strictly limited to:
C:\dev\dev-root\docs-manager-README.md
C:\dev\dev-root\docmap.md
Do not touch any other file. Do not invent, extend, or "improve" anything
beyond what is explicitly described below.

---

## Part A — Fix the backup-path inconsistency

Three different backup paths currently exist across the corpus for what
should be one unified convention:
  - `C:\backups-general\backup-mb-align-docs_<timestamp>\` — correct,
    already the standard, used consistently in mb-align-docs' own files.
  - `C:\backup-docs-manager\<timestamp>\` — stale, used in
    docs-manager-README.md.
  - `C:\mybizz\backup-mybizz\` — stale, used in docmap.md's own File
    Placement Rules table.

The correct, unified convention for Docs Manager's backups, matching the
naming pattern already established for mb-align-docs, is:
`C:\backups-general\backup-docs-manager_<timestamp>\`

Step A1 — In docs-manager-README.md, propose replacing every occurrence
of `C:\backup-docs-manager\<timestamp>\` with
`C:\backups-general\backup-docs-manager_<timestamp>\`. Show every location
found and the exact proposed replacement text before writing anything.

Step A2 — In docmap.md's Section 6 "File Placement Rules" table, the row
for "Backups" currently reads `C:\mybizz\backup-mybizz\ (new folder per
backup exercise)`. Propose replacing this with the unified convention:
`C:\backups-general\` (one subfolder per tool/run, e.g.
`backup-docs-manager_<timestamp>\`, `backup-mb-align-docs_<timestamp>\`).
Show the exact proposed replacement text before writing anything.

---

## Part B — Add the missing mb-align-docs folder to docmap.md's logs tree

File: docmap.md, Section 1 "Division Root — C:\mybizz\"

The `C:\mybizz\logs\` tree currently lists `docs-manager/`,
`github-logs/`, and `gbrain-logs/`, but omits `mb-align-docs/` entirely,
despite it being an established, actively-used folder with four
confirmed subfolders:
  C:\mybizz\logs\mb-align-docs\learnings
  C:\mybizz\logs\mb-align-docs\in-progress
  C:\mybizz\logs\mb-align-docs\last-completed-run
  C:\mybizz\logs\mb-align-docs\abandoned-runs

Step B1 — Propose adding an `mb-align-docs/` entry to the `logs/` tree in
Section 1, at the same indentation level as `docs-manager/`, listing its
four subfolders (learnings, in-progress, last-completed-run,
abandoned-runs), matching the style already used for `docs-manager/`'s
own `Learnings/` sub-entry. Show the exact proposed tree text and its
insertion point before writing anything.

---

Step 1 — Precondition check.
Confirm the git working tree is clean for the repo containing
C:\dev\dev-root\ before proceeding. If dirty, stop and report — do not
proceed.

Step 2 — Backup.
Take a full backup of C:\dev\dev-root\ before any write. Save to
C:\backups-general\backup-mb-align-docs_<timestamp>\ (this correction
task itself is being run via the mb-align-docs backup convention since
Docs Manager's own corrected convention doesn't exist as a folder yet —
use this path for this task's own safety backup only), timestamp per the
mandatory method in
C:\dev\project-library-global\adr-global\timezone-utc-storage-display-conversion.md,
format YYYY-MM-DDTHHMMSS+0200.

Step 3 — Present all proposed changes (Parts A and B) together, before
any write.

Step 4 — Approval.
Part A and Part B each get their own separate explicit approval.

Step 5 — Apply.
Only after approval, apply each approved change, one file at a time.
Re-read each file immediately after writing to confirm the change was
applied correctly and no other content was altered.

Step 6 — Report.
Confirm what was changed in each file, quote the final corrected text for
each change, and confirm nothing else was altered.

---

Hard constraints:
  - No writes before Step 1 and Step 2 are complete.
  - No writes without the Step 4 approval, per part.
  - This task makes text corrections only — no file renames, no folder
    changes, no front-matter or register actions of any kind.
  - Do not touch any file other than the two named in Scope above.
  - Do not touch any mb-align-docs or Docs Manager skill file itself —
    this task only corrects the two human-facing documents named above.
