# Folder Structure

How the workspace is organized and what each folder is for. Read once, refer back when "where does this go?" comes up.

The structure is **PARA-shaped at the top**, **Johnny-Decimal-named at the file level**, and **inbox-driven for flow**. Files move predictably between inboxes, working folders, and archives.

---

## Top-level map

```
your-workspace/
├── CLAUDE.md                                          # Larry's identity + the iron rule (HR's lane)
├── .claude/
│   └── agents/                                        # Callable agent definitions (HR's lane)
├── Library/                                           # Librarian's lane — rulebook, tag vocab, relocation log
├── Owner's Inbox - Working folder for AI to share with me/
│   └── Archive/
├── Team Inbox - Move working files to give AI team to work with/
│   └── Archive/
├── Team - AI team of agents/                          # Human-readable team profiles
├── docs/                                              # Starter-kit guides + reference
├── Projects/                                          # PARA — active, time-bounded work (you create as needed)
├── Areas/                                             # PARA — ongoing responsibilities (you create as needed)
└── Resources/                                         # PARA — reference material (you create as needed)
```

The seven folders above the PARA buckets ship with the starter kit. The `Projects/` / `Areas/` / `Resources/` buckets are conventions you grow into — they don't need to exist on day one.

---

## The two inboxes

### Owner's Inbox — *Working folder for AI to share with me*

**Direction:** team → owner.
**Purpose:** where the team drops finished deliverables for you (the owner) to read, decide on, or act on.
**Examples:** audit reports, decision memos, research briefs, weekly summaries, RFCs awaiting ratification.
**Lifecycle:** once the owner has acknowledged a deliverable (read it, decided on it, or filed the decision elsewhere), the deliverable moves into `Owner's Inbox/.../Archive/` with the **same filename** — no re-dating.

### Team Inbox — *Move working files to give AI team to work with*

**Direction:** owner → team. Also team → team (intra-team handoffs are visible here so the owner can see what's being passed around).
**Purpose:** where the owner drops files for the team to act on. Where one team member hands a working file to another.
**Examples:** raw documents the owner wants summarized, a research brief one team member produced for another, a draft awaiting review.
**Lifecycle:** when a Team Inbox file is fully consumed by the team member working it, that team member moves it into `Team Inbox/.../Archive/` with the **same filename**. If it's still in flight, it stays in the active inbox.

### Why the long folder names

The folder names read like instructions on purpose. When someone (you, a teammate, a future you) sees `Team Inbox - Move working files to give AI team to work with`, they don't have to remember which inbox is which — the name tells them.

---

## `Library/` — librarian's lane

Three files, all owned by Wren (PKM Librarian) or whoever fills that lane in your team:

| File | Purpose |
|---|---|
| `Library/rulebook.md` | The living rulebook. Every routing / naming / archive decision lands here with a date and a rationale. |
| `Library/tag-vocabulary.md` | Controlled tag list with one-line definitions per term. |
| `Library/relocation-log.md` | Append-only log of every move / rename, citing the rulebook entry that justified it. |

The librarian's audit reports drop into `Owner's Inbox/`, not into `Library/`. `Library/` is the *rules*; audits are *findings against those rules*.

---

## `Team - AI team of agents/` — human-readable team profiles

One file per team member. Each profile is a one-page introduction: name, role, personality, what they own, what they don't own. The owner can hand a profile to someone outside the workspace as a "this is my team" intro.

These profiles complement (don't replace) the callable agent definitions in `.claude/agents/`. The callable definitions are operational; the profiles are introductory.

---

## `.claude/agents/` — callable agent definitions (HR's lane)

Don't edit by hand. The HR specialist (Nolan in the default team) owns these files; the orchestrator (Larry in the default team) calls them by referencing the role file in the agent prompt.

If you want to hire a new specialist, ask Nolan to hire them. If you want to retire one, ask Nolan to retire them. The files here are the team's "callable identity layer."

---

## `Projects/`, `Areas/`, `Resources/` — PARA buckets (grow into them)

These come from Tiago Forte's PARA method:

- **`Projects/`** — active, time-bounded work. Each project is a folder. A project ends; the folder gets archived.
- **`Areas/`** — ongoing responsibilities. Each area is a folder that persists indefinitely. "Personal finance," "the company you're building," "your health" — areas don't end, you just maintain them.
- **`Resources/`** — reference material. Not actionable today, but worth keeping searchable. Frameworks, prior-art write-ups, vendor evaluations, durable knowledge that doesn't belong to one project or area.

The PARA buckets are optional on day one. Start with the inboxes + Library + team folder; create PARA buckets when you have real content to put in them. Empty PARA folders are clutter.

---

## File naming — Johnny-Decimal-style ISO date prefix

Every working file uses:

```
YYYY-MM-DD-<kind>-<slug>.md
```

- `YYYY-MM-DD` is the ISO 8601 date — when the artifact was about / produced, not when it was moved.
- `<kind>` is one short token: `audit`, `memo`, `brief`, `routing`, `decision`, `meeting`.
- `<slug>` is lowercase-hyphen, cross-platform safe, under ~40 characters.

**Always** date → kind → slug. Never slug → date.

Examples:

- `2026-05-12-audit-team-inbox.md`
- `2026-05-12-memo-pricing-decision.md`
- `2026-05-12-brief-vendor-comparison.md`
- `2026-05-12-routing-where-do-meeting-transcripts-go.md`

The date prefix means alphabetical sort = chronological sort, on every filesystem, in every tool.

---

## The `Archive/` archival pattern

When a file is consumed (Team Inbox) or acknowledged (Owner's Inbox), it moves to that inbox's `Archive/` subfolder with the **same filename**. No re-dating. The original date is the artifact's history.

```
Owner's Inbox - Working folder for AI to share with me/
├── 2026-05-15-audit-library.md                        # still live
└── Archive/
    └── 2026-05-08-audit-library.md                    # last week's, acknowledged
```

If you ever need to know "when did I move this to archive?", that lives in `Library/relocation-log.md`. The filename stays clean.

---

## Two-pass file lifecycle

1. **Creation pass.** New artifact → working folder or inbox with the correct name. Tag vocabulary consulted before any tag is applied.
2. **Consumption pass.** Artifact is read / acted on / decided on. Moves to `Archive/`. Relocation logged.

If a file lives in an inbox for more than two weeks without movement, it's stale — flag it in the next weekly audit and either consume it or kill it. Inboxes are not long-term storage.

---

## What does NOT live in this workspace

- **Raw meeting transcripts** — they belong to the meeting tool (Krisp, Otter, Granola, etc.). The workspace points at them; it does not copy them.
- **Email threads** — they live in the mail client. Reference by message ID or thread URL.
- **Calendar events** — they live in the calendar.
- **Source files the owner uploaded to Drive / Dropbox / cloud** — they stay where they are. The workspace references them by ID or path.

This workspace holds *durable structured knowledge* (rulebook, tags, team identity) and *flow artifacts* (briefs, memos, audits, drafts). It does not hold raw third-party content.
