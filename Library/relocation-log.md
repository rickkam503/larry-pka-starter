# Relocation Log

**Owner:** Wren (PKM Librarian)
**Status:** Append-only. Every move, rename, or in-place rewrite that the librarian executes lands here with the rulebook entry that justifies it.

---

## How this log is used

This is the audit trail for *where things went and why*. The rulebook says what the rules are; this log records the specific actions taken under those rules.

Format conventions:

- **One dated heading per relocation pass.** Reverse chronological — newest on top.
- **Justifying rule.** Always cite the `Library/rulebook.md` entry that authorizes the action. If the action has no rulebook entry, write the rulebook entry first and *then* execute the move.
- **Files touched.** List with `from → to` paths for moves, or before/after snippets for in-place content edits.
- **Files NOT touched.** When a sweep deliberately spares some files, name them and say why. Silence on a file the reader might expect is worse than a one-line "preserved because X."

Never edit prior entries. Corrections land as new entries that supersede.

---

## Example entry (placeholder — delete or overwrite on first real relocation)

### {YYYY-MM-DD} — Example: Archive sweep of Team Inbox

**Justifying rule:** `Library/rulebook.md` Day 0 entry — "consumed files move to `Archive/` with their original name."

**Scope:** Team Inbox only. Owner's Inbox handled separately.

**Files moved (N):**

- `Team Inbox - Move working files to give AI team to work with/2026-05-09-example-brief.md` → `Team Inbox - Move working files to give AI team to work with/Archive/2026-05-09-example-brief.md`
- (one bullet per file)

**Files NOT moved:**

- `Team Inbox - Move working files to give AI team to work with/2026-05-12-still-in-flight-draft.md` — still being consumed by team member. Revisit next audit.

**Renames in this pass:** None.

---

*New entries above this example. Delete the example once real entries accumulate.*
