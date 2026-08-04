# Docs Manager — README

**Full technical spec:** `SKILL.md` (same skill folder). This file is the short version — read
this first, read `SKILL.md` only when you need the exact rule for something.

---
## read first
— the big structural work is done. Quick note on testing V8, since it's a meaningfully bigger change than the last few rounds: the resume/checkpoint path (Phase −2, the in-progress → last-completed-run handoff) and the new file-system split (4a/4b, the second confirmation gate) are both genuinely new code paths that haven't run for real yet — worth watching those specifically on the first pass, the same way the backup-verification gap only showed up once it actually ran.

---

## What it is

Docs Manager keeps a handful of "map" documents — [[docmap|Docmap]], [[project-inventory|Project Inventory]], and the
`README.md`/`AGENTS.md`/`INDEX.md` files scattered through your project folders — accurate
against what's actually on disk. Think of [[docmap|Docmap]] as a map of a city: the real city (your
folders and files) keeps changing, and over time the map stops matching it. Docs Manager walks
the city, notices where the map is wrong, and redraws it — it never touches the city itself. It
works in five small, single-job pieces: one checks your git repos are clean and takes a safety
backup before anything else happens; one looks around and compares the maps to reality without
changing anything; one writes only the small text corrections you've approved; a separate one
carries out any approved renames or moves — and can never delete anything, only archive it; and
a last one commits everything to GitHub once you're satisfied. Every run is fully recorded, past
decisions are remembered so the same question doesn't get re-asked next time, and if a session
gets interrupted partway through, the next run offers to pick up exactly where it left off
instead of starting over.

## How to run it

```
/docs-manager              → full run
/docs-manager quick        → the two pinned maps + README.md files only
/docs-manager division-maps → just docmap.md and project-inventory.md
/docs-manager no-push      → runs everything except the final GitHub commit/push
```

Nothing needs confirming to *start* — running the command is the trigger. It will stop and ask
you things at exactly two points: if it finds a problem before it can safely begin (a dirty
repo, a failed backup), and when it has a report ready for you to review.

## What happens when you run it

1. Checks your git repos are clean — stops immediately if not, tells you which ones.
2. Backs up the five file types it might touch.
3. Looks around, compares what the maps say to what's actually there.
4. Shows you a report — proposed text corrections, separately from any file renames/moves,
   plus anything it's unsure about with a recommendation attached.
5. **You decide what happens.** Nothing is written until you approve it — and file renames/moves
   get one more explicit "about to do this, proceed?" on top of that.
6. Commits to GitHub, writes a log, remembers anything worth remembering for next time.

## The folders it uses

| Folder | What it holds |
|---|---|
| `C:\mybizz\logs\docs-manager\` | Permanent history — one file per run, forever |
| `...\Learnings\` | Judgment calls from past runs, so the same question isn't re-asked every time |
| `...\in-progress\` | The *current* run only, updated as it goes — if a session dies mid-run, this is what it resumes from |
| `...\last-completed-run\` | Full detail of the most recent finished run — the place to look if something needs tracing back |
| `...\abandoned-runs\` | Runs you chose to discard rather than resume — kept, never deleted |
| `C:\backup-docs-manager\<timestamp>\` | Safety copies of the five file types, one snapshot per run |
| `C:\mybizz\logs\github-logs\` | Commit/push results, closing git-status snapshots |

## The five sub-agent files, one line each

| File | Job |
|---|---|
| `docs-manager-backup.md` | Checks repos are clean, backs up the five file types |
| `docs-manager-scan.md` | Reads everything, compares map to reality, writes nothing |
| `docs-manager-apply.md` | Writes approved text corrections only |
| `docs-manager-filesystem.md` | Performs approved renames/moves only — can never delete anything |
| `docs-manager-commit.md` | Commits and pushes to GitHub |

## The safety guarantees, in plain terms

- **Nothing is ever written without your explicit approval** — no exceptions.
- **It never deletes anything.** A "delete" is always a move to an `obsolete\` folder instead.
- **It never touches your code**, business documents, or anything outside the five file types.
- **It never runs `gbrain sync`** or anything that changes GBrain's state.
- **A backup happens before anything else, every time**, and the run stops cold if that backup
  can't be verified.
- **A lost session never loses your work** — resuming picks up exactly where it left off,
  including decisions you'd already made.

## If something goes wrong

| Situation | What to do |
|---|---|
| Session/window closed mid-run | Just run `/docs-manager` again — it'll find the unfinished run and ask if you want to resume |
| It says a repo is dirty | Commit or clean that repo's git status, then run it again |
| Something looks off after a run | Check `C:\mybizz\logs\docs-manager\last-completed-run\` — it has the full detail of exactly what happened |
| Need to undo something | Files: restore from `C:\backup-docs-manager\<timestamp>\`. Renames/moves: check `git log` in the relevant repo |
| Want the exact rule for something | `SKILL.md`, same folder — it's the full spec this README summarizes |
