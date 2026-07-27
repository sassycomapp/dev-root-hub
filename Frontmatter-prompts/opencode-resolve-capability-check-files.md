Task: Determine relevance and resolve two capability_check ping files.
Two files, two separate repos. Treat each independently; do not assume
one outcome applies to the other.

Files:
  1. C:\dev\dev-makepdlf\makepdlf-project-library\capability_check_2880.md
  2. C:\dev\dev-mb5pdlf\mb5pdlf-project-library\_capability_check_12056.md

Both files currently contain only front matter (an ingestion-tool stamp:
type, title, ingested_via, ingested_at, source_kind) and a single-word
body: "ping". File 2 additionally has a second, separate front-matter
block already applied (document, doc-id: mb5pdlf-0003, state: Live,
date-created) from an earlier retrofit run — this was applied in error
and must be removed as part of this task, not preserved.

Step 1 — Determine relevance.
For each file, check whether anything in its repo (README.md, INDEX.md,
AGENTS.md, any skill file, any script, any register entry, GBrain
configuration, or scaffold-initialization logic) references the file by
name or depends on its presence. Report findings per file before taking
any action. Do not assume relevance or irrelevance — check.

Step 2 — Backup.
Take a full backup of each affected repo before any write. Save to
C:\backups-general\backup-mb-align-docs_<timestamp>\, timestamp per the
mandatory method in
C:\dev\project-library-global\adr-global\timezone-utc-storage-display-conversion.md,
format YYYY-MM-DDTHHMMSS+0200. One backup per repo, or a combined backup
covering both if taken in the same session — state which was done in the
report.

Step 3 — Propose outcome, no writes yet.
For each file, propose one of:
  (a) Not referenced anywhere, safe to move to an "obsolete" folder within
      its repo (create the folder if it does not exist) — do not delete
      outright.
  (b) Referenced somewhere and still relevant — report the reference and
      recommend keeping it in place. Do not move it.
For file 2 specifically, regardless of outcome (a) or (b): the mistakenly
applied front-matter block (doc-id: mb5pdlf-0003, state: Live,
date-created) must be removed. Propose this as a separate, explicit line
item, flagged clearly as a correction of a prior error — not folded
silently into the move.

Step 4 — Approval.
Present both proposed outcomes (and the front-matter removal for file 2)
for explicit approval before any write.

Step 5 — Apply.
Only after approval: move each file to obsolete/ if approved, and strip
the erroneous front-matter block from file 2 regardless of its final
location. Re-read each affected file after writing to confirm the change
was applied correctly and nothing else was altered.

Step 6 — Report.
For each of the two files, state final outcome: moved to obsolete / left
in place / front matter removed, with reasoning.

Hard constraints:
  - No writes before backup is complete, in either repo.
  - No writes without explicit approval on Step 4.
  - Never alter file content beyond what is explicitly described above
    (move, or front-matter removal) — no other edits.
  - Do not touch any file outside the two repos named above.
  - Do not touch any file other than the two named in this task.
