Task: Correct backup-path references — three distinct canonical folders,
not one unified convention.
Scope is strictly limited to:
C:\projects-reference\custom-skills-store\mb-align-docs\SKILL.md
C:\dev\dev-root\mb-align-docs-README.md
C:\dev\dev-root\docs-manager-README.md
C:\dev\dev-root\docmap.md
Do not touch any other file.

Context: an earlier task incorrectly assumed a single unified backup
convention (C:\backups-general\backup-<tool>_<timestamp>\) applied to
both skills. This was wrong. The actual, correct model — confirmed by the
developer — is three separate folders:

  C:\backup-docs-manager\<run-timestamp>\   — Docs Manager's own
                                               canonical backup folder,
                                               already in real use.
  C:\backup-mb-align-docs\<run-timestamp>\  — mb-align-docs' own
                                               canonical backup folder,
                                               to be used starting with
                                               its first real run.
  C:\backups-general\                       — general-purpose backups
                                               unrelated to either
                                               skill's own dedicated
                                               mechanism (this is what
                                               was used throughout this
                                               project's development/
                                               finalization phase, kept
                                               deliberately separate so
                                               it didn't pollute either
                                               skill's real backup
                                               history).

Docs Manager's own SKILL.md has already been corrected directly by the
developer to use C:\backup-docs-manager\<run-timestamp>\ throughout — do
not touch that file, it is not in this task's scope, and it is already
correct.

---

## Part A — mb-align-docs' own SKILL.md

File: C:\projects-reference\custom-skills-store\mb-align-docs\SKILL.md

Step A1 — Search the entire file for every occurrence of
`C:\backups-general\backup-mb-align-docs_<timestamp>\` or any variant
referencing that path (Phase 0 backup step, the Folders table, any other
mention). Report every location found before proposing anything.

Step A2 — Propose replacing every occurrence with
`C:\backup-mb-align-docs\<timestamp>\` — matching the exact format
Docs Manager's own corrected SKILL.md now uses for its own canonical
folder (a timestamped subfolder directly under the dedicated backup
folder, no `backup-<tool>_` prefix inside the folder name, since the
folder itself already names the tool). Show every proposed replacement
before writing anything.

---

## Part B — mb-align-docs-README.md

File: C:\dev\dev-root\mb-align-docs-README.md

Step B1 — Search for every occurrence of the same stale
`C:\backups-general\backup-mb-align-docs_<timestamp>\` path (the "If
something goes wrong" table, Section C, and anywhere else it appears).
Report every location found.

Step B2 — Propose replacing each with `C:\backup-mb-align-docs\<timestamp>\`,
matching Part A's corrected format. Show the exact proposed text before
writing anything.

---

## Part C — docs-manager-README.md revert

File: C:\dev\dev-root\docs-manager-README.md

Step C1 — This file was previously (incorrectly) changed from
`C:\backup-docs-manager\<timestamp>\` to
`C:\backups-general\backup-docs-manager_<timestamp>\`. Search for every
occurrence of the incorrect form and report each location found.

Step C2 — Propose reverting each occurrence back to
`C:\backup-docs-manager\<timestamp>\` — the original, correct form. Show
the exact proposed text before writing anything.

---

## Part D — docmap.md correction

File: C:\dev\dev-root\docmap.md, Section 6 "File Placement Rules"

Step D1 — The "Backups" row currently (incorrectly) reads something like
`C:\backups-general\ (one subfolder per tool/run, e.g.
backup-docs-manager_<timestamp>\, backup-mb-align-docs_<timestamp>\)`.
Report the exact current text of this row.

Step D2 — Propose replacing it with a row that correctly distinguishes
all three folders, for example:

  | Backups | Docs Manager: `C:\backup-docs-manager\<timestamp>\`.
  mb-align-docs: `C:\backup-mb-align-docs\<timestamp>\`. All other/general
  backups: `C:\backups-general\` (new folder per backup exercise). |

Adjust wording to fit the table's existing style. Show the exact proposed
text before writing anything.

---

Step 1 — Precondition check.
Confirm the git working tree is clean for both repos involved (the
skill-store repo, and the dev-root repo) before proceeding. If either is
dirty, stop and report that repo — continue checking the other.

Step 2 — Backup.
Take a full backup of both repos before any write. Save to
C:\backups-general\backup-mb-align-docs-path-correction_<timestamp>\ —
this task's own working backup, distinct from either skill's own
canonical folder, since neither skill's real mechanism should be invoked
just to back up a documentation-correction task. Timestamp per the
mandatory method in
C:\dev\project-library-global\adr-global\timezone-utc-storage-display-conversion.md,
format YYYY-MM-DDTHHMMSS+0200.

Step 3 — Present all proposals (Parts A through D) together, before any
write.

Step 4 — Approval.
Each part gets its own separate explicit approval.

Step 5 — Apply.
Only after approval, apply each approved change, one file at a time.
Re-read each file immediately after writing to confirm the change was
applied correctly and no other content was altered.

Step 6 — Report.
Confirm every part's outcome, quote the final corrected text for each,
and confirm no other content in any file was altered beyond what was
approved.

---

Hard constraints:
  - No writes before Step 1 and Step 2 are complete.
  - No writes without the Step 4 approval, per part.
  - Do not touch Docs Manager's own SKILL.md under any circumstance — it
    is already correct and out of scope for this task.
  - Do not touch any file other than the four named in Scope above.
  - Do not invent, add, or "improve" anything beyond the specific path
    corrections described in Parts A–D.
