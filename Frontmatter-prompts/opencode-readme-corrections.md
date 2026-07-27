Task: Correct two human-facing README documents.
Scope is strictly limited to:
C:\dev\dev-root\mb-align-docs-README.md
C:\dev\dev-root\dev-root-README.md
Do not touch any other file. Do not invent, extend, or "improve" anything
beyond what is explicitly described below. These are plain text
corrections — no renames, no moves, no front-matter or register changes
of any kind.

---

## Part A — mb-align-docs-README.md corrections

Two known issues:

1. **Stale `pdlf` project reference.** Section D's inventory table lists a
   project named `pdlf` with register/Quarantine paths under
   `C:\dev\dev-pdlf\`. This project was renamed to `dev-makepdlf` /
   `makepdlf-project-library` — already completed and confirmed
   elsewhere. This table row, and the "Open item" note beneath it about
   `dev-pdlf` having no `project-library` subfolder, are both stale and
   refer to a project name that no longer exists.

2. **Backup path inconsistency.** The "If something goes wrong" table and
   Section C both cite `C:\backup-mb-align-docs\<timestamp>\` as the
   backup/restore location. The actual convention used throughout this
   skill (confirmed in SKILL.md and every prior task) is
   `C:\backups-general\backup-mb-align-docs_<timestamp>\`. Both
   occurrences need correcting to match.

Step A1 — Before editing, confirm current reality for the renamed
project: verify `C:\dev\dev-makepdlf\makepdlf-project-library\` has
`register-local\` and `Quarantine\` folders in the normal position (same
structure as mb-3-cs, mb4ecom, mb5pdlf), matching the other three
projects — not the irregular structure the stale note described for the
old `dev-pdlf` name. Report what you find.

Step A2 — Propose the corrected Section D table row for makepdlf
(replacing the stale `pdlf` row), matching the format of the other three
project rows. Remove the now-moot "Open item" note about dev-pdlf's
irregular structure — it no longer applies now that the project has the
same structure as the others (only remove it if Step A1 confirms the
structure is now regular; if it's still irregular under the new name,
report that instead of removing the note).

Step A3 — Propose the corrected backup path in both locations (the "If
something goes wrong" table and Section C), replacing
`C:\backup-mb-align-docs\<timestamp>\` with
`C:\backups-general\backup-mb-align-docs_<timestamp>\`.

Show all proposed text changes for Part A before writing anything.

---

## Part B — dev-root-README.md review

This file explicitly flags itself as an unverified reconstruction: "this
file is a reconstruction. The original was overwritten during Docs
Manager's setup. Review closely and correct anything that doesn't match
what was actually here before."

Step B1 — Read the current, actual content of the two files this README
describes: `C:\dev\dev-root\docmap.md` and
`C:\dev\dev-root\project-inventory.md`. Compare their real current
structure and content against what dev-root-README.md currently claims
about them.

Step B2 — Report any discrepancy found between what the README describes
and what those two files actually contain or represent. Do not assume the
README is correct where it's silent or vague — check directly.

Step B3 — Propose corrected text for any discrepancy found. If, after
review, the README is found to accurately describe the current state of
both files, propose removing the "this file is a reconstruction... review
closely" caveat, since the review has now been done and confirmed
accurate. If discrepancies were found and corrected, keep a note that this
file was reconstructed and has now been verified/corrected, rather than
removing all trace of that history.

Show all proposed text changes for Part B before writing anything.

---

Step 1 — Precondition check.
Confirm the git working tree is clean for the repo containing
C:\dev\dev-root\ before proceeding. If dirty, stop and report — do not
proceed.

Step 2 — Backup.
Take a full backup of C:\dev\dev-root\ before any write. Save to
C:\backups-general\backup-mb-align-docs_<timestamp>\, timestamp per the
mandatory method in
C:\dev\project-library-global\adr-global\timezone-utc-storage-display-conversion.md,
format YYYY-MM-DDTHHMMSS+0200.

Step 3 — Present all proposed changes (Parts A and B) together, before
any write.

Step 4 — Approval.
Part A and Part B each get their own separate explicit approval — do not
bundle them, since Part B depends on a live comparison against other
files and may surface findings Part A doesn't.

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
  - Do not touch C:\dev\dev-root\docmap.md or
    C:\dev\dev-root\project-inventory.md themselves — Step B1 reads them
    for comparison only, it does not edit them.
