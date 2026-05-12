# Workspace Rulebook

**Owner:** Wren (PKM Librarian)
**Status:** Living document. Every routing / naming / archive decision lands here with a date and a rationale.
**Companion docs:** `Library/tag-vocabulary.md`, `Library/relocation-log.md`.

---

## Purpose

This file is the source of truth the rest of the team consults when they don't know where to put something, what to name it, or whether to archive it. Small set of strong rules. Every entry dated. Every change justified.

If the rulebook doesn't answer the question, Wren makes the call and the new rule lands here so the next instance is self-serve. The rulebook grows by use, not by anticipation.

---

## Working principles

- **Rulebook before reflex.** When you make a routing call, check the rulebook first. If the rulebook covers it, cite the entry. If it doesn't, make the call *and* add the rule.
- **Small set of strong rules.** Six clear rules are easier to defend than twenty fuzzy ones. Resist adding a rule to cover a single one-off. If a situation is genuinely novel, document it; if it's a variant of an existing rule, refine the existing rule.
- **Never silent moves.** Every relocation / rename / in-place rewrite is logged in `Library/relocation-log.md` with the rulebook entry that justified it.
- **Read-only on the database** (if your workspace has one). The librarian queries; the librarian does not modify schema or DDL. Schema-shaped concerns escalate to whoever owns the schema.

---

## Seed methodology (Day 0 — enforce from the start, evolve with evidence)

You inherit a hybrid **PARA + Johnny-Decimal-naming + DB-first** methodology. Enforce it from day one. You are explicitly empowered to evolve it once you have enough audit evidence to justify a change. Every evolution lands as a new dated entry in this decision log with rationale.

### 1. Top-level folders are PARA-shaped

- `Projects/` — active, time-bounded work
- `Areas/` — ongoing responsibilities (a recurring lane of work without an end date)
- `Resources/` — reference material (not actionable, but worth keeping)
- `Library/` — this rulebook, tag vocabulary, relocation log, audit reports' source notes
- `Owner's Inbox - Working folder for AI to share with me/` — team-to-owner deliverables
- `Team Inbox - Move working files to give AI team to work with/` — owner-to-team working files
- `Team - AI team of agents/` — human-readable team profiles
- `.claude/agents/` — callable agent definitions (HR's lane; do not edit by hand)

Both inboxes have an `Archive/` subfolder. The archived form of a file is **same name, different folder** — not a re-dated copy.

### 2. Naming convention — Johnny-Decimal-style ISO date prefix

**Pattern:** `YYYY-MM-DD-<kind>-<slug>.md`

- ISO 8601 date prefix sorts chronologically with no ambiguity (`2026-05-12-`, never `5-12-26-`).
- `<kind>` is the artifact type as one short token: `audit`, `memo`, `brief`, `routing`, `decision`, `meeting`, etc.
- `<slug>` is lowercase-hyphen, cross-platform safe, under ~40 characters when possible.
- Element order is always `date → kind → slug`. Never `slug → date`.
- The date is the artifact's **content date** (when it was about / produced), not the move date.

### 3. Archive rule

An archived file = **same name + `Archive/` location**. Don't re-date on archive. The original date is the artifact's history.

When a Team Inbox file is fully consumed, OR an Owner's Inbox deliverable has been acknowledged by the owner, the team member who finished with the file moves it into the `Archive/` subfolder of that inbox.

### 4. DB-first routing rule (if your workspace has a structured store)

If a piece of content is structurally a row in your knowledge store (e.g., `meeting`, `contact`, `project`, `task`, `journal_entry`), it lives as a row first. Files exist for things rows can't hold: long freeform attachments, source documents, drafts in progress. Files link back to rows by ID.

When in doubt, row-first; rows are queryable, files are not. If your workspace has no structured store yet, every artifact is a file — but mark this as a known gap and revisit when one ships.

### 5. Tag vocabulary

Lives in `Library/tag-vocabulary.md`. Every new tag needs a one-line definition before it ships. Synonyms get merged; case is normalized; no free-form drift. Adding a tag without a corresponding piece of content landing in the workspace is speculation; tags are added by use, not by anticipation.

### 6. Weekly audit

Walk the inboxes and working folders. Write a numbered fix list. Drop the audit in `Owner's Inbox - Working folder for AI to share with me/` as `YYYY-MM-DD-library-audit.md`. Findings to look for:

- Stale files past their archive-by date
- Filename-convention violations
- Near-duplicates (same content, different filename)
- Orphaned files where a DB link is expected but missing
- Tag-vocabulary drift (case variants, near-synonyms, undefined new tags)

---

## DB-vs-file routing — decision tree

When a new artifact arrives, classify it:

1. **Is it structurally a row in the knowledge store?** (meeting, contact, project, task, journal entry, action item, decision, etc.)
   - **Yes** → row first. File only if there's a long freeform body the row can't hold.
2. **Is it a long-form deliverable or working draft?**
   - **Yes** → file in the appropriate inbox or working folder. No row unless a deliverable references it.
3. **Is it a tag, person, or short-string attribute?**
   - **Yes** → goes into the corresponding column / table in the knowledge store.
4. **Is it ambiguous?**
   - Make the call, document it as a new entry in this rulebook, and move on. Don't paralyze on edge cases.

---

## Decision log

Each entry: dated heading + decision + rule going forward + rationale + cross-references. Reverse chronological — newest on top.

### {YYYY-MM-DD} — Workspace initialized

**Owner:** {NAME}
**Methodology:** PARA + Johnny-Decimal-naming + DB-first (inherited from starter-kit seed; subject to evolution as audit evidence accumulates).
**Workspace surfaces in scope:** local filesystem (this repo). Add Google Drive / Notion / Obsidian / etc. as separate entries if/when you extend Wren's scope.

**Rule going forward:**
- All new files use `YYYY-MM-DD-<kind>-<slug>.md`.
- All consumed files move to `Archive/` with the same name.
- Tags land in `Library/tag-vocabulary.md` before they ship.
- Weekly audit lands in `Owner's Inbox/` on the day chosen by the owner.

**Rationale:** Starter-kit defaults. The owner is encouraged to keep these intact for the first month before evolving — the methodology is opinionated for a reason, and evolution without evidence usually produces drift, not improvement.

**Cross-references:** `Library/tag-vocabulary.md` (Day 0 seed vocabulary), `Library/relocation-log.md` (empty until first relocation).

---

*The rulebook grows from here. New entries above this one, newest on top.*
