# mb-align-docs — README

**Full technical spec:** `SKILL.md` (in the skill-store folder, see inventory below). This file
is the short version — read this first, read `SKILL.md` only when you need the exact rule for
something.

---

## What it is

mb-align-docs keeps your planning/spec documents agreeing with each other — terminology,
requirements, cross-references, and identifiers all staying consistent across a project's
documentation. Where Docs Manager keeps the *map* (folder structure, index files) matching the
*city* (your filesystem), mb-align-docs makes sure everything written on the map actually agrees
with everything else written on the map — it never touches folder structure, only document
content and cross-references. It works in four single-job pieces: one looks around and compares
every document's claims to every other's, and to a permanent register of what's supposed to
exist, without changing anything; one writes only the small reference corrections you've
approved; a separate one carries out approved renames, identifier changes, and moves into
Quarantine — and can never delete anything, only retire or quarantine it; and a last one commits
everything and logs what happened. Every run is fully recorded, past decisions are remembered so
the same question doesn't get re-asked next time, and if a session gets interrupted partway
through, the next run offers to pick up exactly where it left off instead of starting over.

## How to run it

```
/mb-align-docs              → run against a named project (+ project-library-global, always)
```

Every run covers one named project's `project-library` together with `project-library-global` —
global is never optional and never run alone. Nothing needs confirming to *start* — running the
command is the trigger. It will stop and ask you things at exactly two points, plus one extra for
structural changes: if it finds a problem before it can safely begin (a dirty repo, a failed
backup); when it has a report ready for you to review; and again, specifically, before it carries
out any rename, identifier-change sweep, or Quarantine move — even after you've already approved
that finding.

## What happens when you run it

1. Checks for an unfinished prior run against this project — offers to resume if found.
2. Checks your git repos (project + global) are clean — stops immediately if not.
3. Backs up everything it might touch.
4. Looks around: compares document content and references against each other and against the
   registers.
5. Shows you a report — every finding with an opinionated recommendation attached, never a bare
   problem.
6. **You decide what happens.** Nothing is written until you approve it — and renames, identifier
   changes, and Quarantine moves get one more explicit "about to do this, proceed?" on top of
   that.
7. Commits, writes a log, remembers anything worth remembering for next time.

## The safety guarantees, in plain terms

- **Nothing is ever written without your explicit approval** — no exceptions.
- **Structural changes need a second, separate confirmation**, even after approval.
- **It never deletes anything.** Retirement or Quarantine, always — never deletion.
- **It never touches folder/file structure** — that's Docs Manager's job, not this skill's.
- **A backup happens before anything else, every time**, and the run stops cold if that backup
  can't be verified.
- **A lost session never loses your work** — resuming picks up exactly where it left off,
  including decisions you'd already made.

## If something goes wrong

| Situation | What to do |
|---|---|
| Session/window closed mid-run | Just run `/mb-align-docs` again — it'll find the unfinished run and ask if you want to resume |
| It says a repo is dirty | Commit or clean that repo's git status, then run it again |
| Something looks off after a run | Check `C:\mybizz\logs\mb-align-docs\last-completed-run\` — it has the full detail |
| Need to undo something | Files: restore from `C:\backups-general\backup-mb-align-docs_<timestamp>\`. Renames/moves: check `git log` in the relevant repo |
| Want the exact rule for something | `SKILL.md`, in the skill-store folder — it's the full spec this README summarizes |

---

## Full inventory — every folder and file belonging to mb-align-docs

### A. Skill package — destined for OpenCode

`C:\projects-reference\custom-skills-store\mb-align-docs\`

| File | Job |
|---|---|
| `SKILL.md` | Full technical spec — phases, subagents, hard constraints |
| `mb-align-docs-function-scope.md` | Locked function scope — what the skill is for and the rules governing it |
| `front-matter-schema.md` | Reference: permitted front-matter fields and valid values |
| `register-template.md` | Blank template — seed for both global and per-project registers |
| `quarantine-provenance-template.md` | Front-matter block applied to any document copied into Quarantine |
| `alignment-log-template.md` | Entry format for the append-only alignment log |
| `finding-report-format.md` | Fixed shape every finding must be reported in, per finding-type |
| `mb-align-docs-detector.md` | Subagent — read-only. Detect + Report. |
| `mb-align-docs-writer-text.md` | Subagent — writes approved reference-healing repoints only |
| `mb-align-docs-writer-structural.md` | Subagent — writes approved renames, identifier-change sweeps, register actions, Quarantine moves. Second-confirmation gated. |
| `mb-align-docs-logger.md` | Subagent — append-only. Commit/Log + Learnings write-back |
| `learnings\` | Folder — seed/example only in this package; the live version accumulates elsewhere (see C, below) |

### B. Human-facing documentation — not for OpenCode

`C:\dev\dev-root\`

| File | Job |
|---|---|
| `dev-root-README.md` | Covers `docmap.md` and `project-inventory.md` only. *Pending rewrite by OpenCode from live filesystem/doc research — no reliable original content exists to restore from.* |
| `docs-manager-README.md` | Short-form guide to Docs Manager |
| `mb-align-docs-README.md` | This file |
| `docmap.md` | Map of the `C:\dev\` folder structure — Docs Manager's territory |
| `project-inventory.md` | List of active projects under `C:\dev\` — Docs Manager's territory |

### C. Operational data — generated by real runs, not delivered

`C:\mybizz\logs\mb-align-docs\`

| Folder | Holds |
|---|---|
| `learnings\` | Live judgment calls from past runs |
| `in-progress\` | Current run only — resume source if interrupted |
| `last-completed-run\` | Full detail of most recent finished run |
| `abandoned-runs\` | Declined-resume runs — kept, never deleted |

`C:\backups-general\backup-mb-align-docs_<timestamp>\` — verified backups, one snapshot per run.

### D. Registers and Quarantine — one set per project, plus one global set

| Project | Register | Quarantine |
|---|---|---|
| Global (`project-library-global`) | `C:\dev\project-library-global\register-global\` | `C:\dev\project-library-global\Quarantine\` |
| mb-3-cs | `C:\dev\dev-mb-3-cs\mb-3-cs-project-library\register-local\` | `C:\dev\dev-mb-3-cs\mb-3-cs-project-library\Quarantine\` |
| mb4ecom | `C:\dev\dev-mb4ecom\mb4ecom-project-library\register-local\` | `C:\dev\dev-mb4ecom\mb4ecom-project-library\Quarantine\` |
| mb5pdlf | `C:\dev\dev-mb5pdlf\mb5pdlf-project-library\register-local\` | `C:\dev\dev-mb5pdlf\mb5pdlf-project-library\Quarantine\` |
| makepdlf | `C:\dev\dev-makepdlf\makepdlf-project-library\register-local\` | `C:\dev\dev-makepdlf\makepdlf-project-library\Quarantine\` |

`register-global` is reserved for `project-library-global` only. Every per-project register is
named `register-local`. Each register folder holds either a populated register file or, until
populated, `register-template-placeholder.md`.

`Quarantine` (capital Q) is the standard casing across both global and per-project folders.
