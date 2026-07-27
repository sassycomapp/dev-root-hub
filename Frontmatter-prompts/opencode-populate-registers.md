Task: Populate registers from existing front matter.
Scope: the following repos, each treated independently:
  1. C:\dev\project-library-global\                        → register-global
  2. C:\dev\dev-mb-3-cs\mb-3-cs-project-library\             → register-local
  3. C:\dev\dev-mb4ecom\mb4ecom-project-library\             → register-local
  4. C:\dev\dev-mb5pdlf\mb5pdlf-project-library\             → register-local
  5. C:\dev\dev-makepdlf\makepdlf-project-library\           → register-local
  6. C:\dev\project-template\dev-(SLUG)\(slug)-project-library\ → register-local
     (parameterized template — see Step 3a note below)
Do not touch any repo not listed above.

Context: Every in-scope document in every repo listed above now has a
front-matter block (document, doc-id, state, date-created). Registers are
currently empty placeholders (register-template-placeholder.md) in every
project and globally. This task populates each register from the
front-matter fields already present — no new front matter is generated or
altered in this task. Register format follows register-template.md at
C:\projects-reference\custom-skills-store\mb-align-docs\register-template.md.
Reminder of the standing rule: register-global exists only at
project-library-global; every per-project register is register-local.
Never the reverse.

Step 0 — Read the register schema first.
Read register-template.md in full before generating any entries. If any
field in the template is not directly available from a document's front
matter (e.g. a field requiring the file's relative path, or a category
derived from folder location), state how that field will be derived
before proceeding — do not guess silently.

Step 1 — Precondition check, per repo.
For each of the six repos, confirm its git working tree is clean before
proceeding. If any repo is dirty, stop and report that repo — do not
proceed on that repo, but continue checking the others.

Step 2 — Backup, per repo.
Take a full backup of each repo before any write. Save to
C:\backups-general\backup-mb-align-docs_<timestamp>\, one backup per repo,
timestamp per the mandatory method in
C:\dev\project-library-global\adr-global\timezone-utc-storage-display-conversion.md,
format YYYY-MM-DDTHHMMSS+0200.

Step 3 — Detect and propose, no writes yet.
For each repo, list every in-scope document that currently has a
front-matter block, with the register entry proposed for it (per the
register-template.md schema). Present one table per repo: relative file
path | doc-id | document | state | date-created | (any other
register-template.md field). Report the total document count per repo.

Step 3a — Template repo note.
For the project-template repo, some front matter is parameterized
(placeholder values for (slug), etc., not real project data — this was
already flagged as stale/placeholder content in a prior task). Populate
its register using the parameterized values as they exist in the
front matter now. Do not attempt to resolve or invent real project
values for the template.

Step 3b — Documents still missing front matter.
If any in-scope document in any repo is found without front matter during
this scan, do not add front matter as part of this task and do not add a
register entry for it. List it separately as "excluded — no front matter"
in the report. (Front-matter completion for any such document is handled
by the missing-front-matter check now in SKILL.md, not by this task.)

Step 4 — Approval.
Present all six per-repo tables for one batch approval, since every entry
receives the same uniform treatment (a direct field mapping from existing
front matter, no invented data).

Step 5 — Apply.
Only after approval, write the approved entries into each repo's register
file, replacing the placeholder content. One repo at a time. Re-read each
register file immediately after writing to confirm entries match what was
approved exactly and no unapproved entry was added.

Step 6 — Report.
Per repo: confirm total entries written, list any documents excluded for
missing front matter, and confirm the register-global vs. register-local
placement was correct for each (register-global written only for
project-library-global; register-local written for the other five).

Hard constraints:
  - No writes before Step 1 and Step 2 are complete, per repo.
  - No writes without the Step 4 approval.
  - Never alter any document's front matter as part of this task — this
    task only reads front matter and writes register entries.
  - Never write register-global anywhere other than project-library-global.
  - Do not touch any repo not listed in Scope above.
