# Karpathy LLM Wiki — Setup Guide

A practical guide to setting up Andrej Karpathy's "LLM Wiki" pattern in your knowledge surface (Google Drive, Notion, Obsidian, or any markdown-friendly storage). Adapted by Wren (PKM Librarian) from a live operational deployment.

---

## What the Karpathy LLM Wiki pattern is

**Source:** Andrej Karpathy, "LLM Wiki" Gist, **2026-04-03**.
**URL:** [https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f)

The pattern has a **three-layer architecture** that separates raw sources from the interlinked knowledge layer from the AI-assisted query layer. The separation is the whole point.

### Layer 1 — Raw sources

Files in Drive, transcripts in your meeting tool, emails in your mailbox, PDFs uploaded somewhere. **Immutable.** The wiki never replaces them. The wiki *points at* them.

You don't copy a meeting transcript into the wiki. You write an atomic page that says "Meeting with X on date Y about topic Z. Key call: ___. Source: link to the transcript in your meeting tool." The transcript stays where it lives. The wiki carries the distilled call.

### Layer 2 — The interlinked wiki

A set of short, atomic pages, cross-linked by hand, organized under **Maps of Content (MOCs)**. One MOC per major project, relationship, or area of your life.

The wiki has three structural files:

- **Index** — the canonical pointer. A table of MOCs + a table of every atomic page with its parent MOC and a one-line summary. This is the **manual backlink map** since plain markdown has no automatic backlinks.
- **Log** — append-only ledger. Every page created, updated, or retired lands here as a dated line. Newest on top, never edit prior entries.
- **Atomic pages** — one topic per page. Short. Under one screen when possible. Named `<MOC> - <topic>`. Cross-linked manually.

### Layer 3 — Query-and-file-back

When you or your AI assistant write a good answer to a question, that answer files back into the wiki as a new atomic page or an update to an existing one. The corpus compounds instead of evaporating into chat history.

This is the layer most people skip and the layer that makes the whole thing pay off. A great answer that doesn't file back is a great answer you'll have to regenerate next month.

---

## How to set it up in Google Drive

The pattern is storage-agnostic. The instructions below are for Drive because Drive is the most common starting point — the same shape works in Notion, Obsidian, or a plain folder of markdown files.

### Choosing a parent folder

Two reasonable defaults:

- **`My Drive/<NN>_<Topic>/Wiki/`** — nest the wiki under the most-related existing folder if you have a numbered taxonomy (e.g., `97_Personal Assistant/Wiki/`). Keeps your folder discipline intact.
- **`My Drive/00_Wiki/`** or **`My Drive/Wiki/`** — top-level if the wiki is going to be a primary surface in your workflow. Signals importance at the cost of a new top-level bucket.

Pick one and stick with it. The wiki's location is in the rulebook, not in your head.

### Markdown vs. Google Docs — the format trade-off

You can store wiki pages as `.md` files in Drive or as native Google Docs. Both work. The decision has consequences.

**Markdown (`.md` files in Drive)** — recommended default:

- Closer to Karpathy's native form (his Gist is markdown).
- Future-proof for migration to Obsidian, Logseq, or any markdown-native PKM later — no conversion pass.
- Drive previews `.md` cleanly enough for review.
- Cost paid: no in-Drive WYSIWYG editing. Edits happen via AI tools, by download-edit-reupload, or by treating the file as append-only.

**Google Docs (native Drive Docs)**:

- WYSIWYG editing in Drive.
- Comments, suggesting mode, real-time collaboration.
- Cost paid: lock-in to Google's format. Migration requires a conversion pass that loses formatting nuance. Diffs and version history live in Drive's revision history, not in your tools.

**The call most people regret later:** picking Docs for the editing convenience, then wanting to migrate to Obsidian a year in. **Default to markdown** unless your team genuinely needs in-Drive collaborative editing.

### File shapes

Three structural files at the root of the wiki folder:

1. **`<Workspace name> Wiki - Index.md`** — the catalog. Table of MOCs + table of atomic pages.
2. **`<Workspace name> Wiki - Log.md`** — append-only ledger. Newest on top.
3. **One file per MOC**, named `<MOC name> - MOC.md`.

Atomic pages, named `<MOC> - <topic>.md`, sit alongside the MOC files. No subfolders for the first six months — flat is easier to scan. If the wiki grows past 100 pages, revisit.

### Index file shape

```markdown
# <Workspace name> Wiki — Index

The catalog of every wiki page, organized by MOC.

## How to use this wiki

[One paragraph explaining the three-layer pattern in your own words.]

## Table of MOCs

| MOC | Scope | Link |
|---|---|---|
| <MOC name> | <one sentence> | [link] |

## Table of atomic pages

| Page | MOC parent | 1-line summary | Link |
|---|---|---|---|
| <page name> | <MOC> | <one sentence> | [link] |
```

### Log file shape

```markdown
# <Workspace name> Wiki — Log

Append-only ledger. Every wiki page created, updated, or retired lands here as a dated entry.

## How this log is used

One line per change, in reverse chronological order — newest at the top, never edit prior entries.

## Entries

**YYYY-MM-DD — Created `<page>` under `<MOC>`. Source: <pointer>. Reason: <one sentence>.**

**YYYY-MM-DD — Wiki created. Initial MOCs: <list>. Methodology: Karpathy LLM Wiki.**
```

---

## How to seed your first MOCs

The starting question is **"what are the 3–5 most active areas of my life right now?"** Each becomes one MOC. Not "all areas of my life" — *active*, where new artifacts land most weeks.

**Examples of what becomes an MOC for someone in active flight:**

- A company you're building (entity, product, customers, IP, advisors)
- A specific customer or partner pursuit (relationship, briefs, commercial terms, stakeholder map)
- An advisor relationship (briefs, asks, cadence, history of reframes)
- An ongoing operating responsibility (a team, a board, a board seat)
- A meta-MOC for the AI team / orchestration layer itself

Three to five is the right starting number. **Two is fine if your life is concentrated.** Six is the upper bound before you lose the "I can hold all my MOCs in my head" benefit.

You will be wrong about the seed MOC list within a month. That's fine. MOCs split, merge, retire. The log records the changes. The index always reflects the current truth.

---

## Operating protocol for real-time intake

The shape of the work when something new lands and needs to enter the wiki.

### The 6-field intake brief

When a new item arrives, capture six fields before doing anything else:

1. **Subject** — one short noun phrase ("Marty 11:30 call reframe," "Vendor X tech spec status").
2. **Source** — pointer to the raw artifact: Drive file ID, meeting transcript link, email message ID, file path, or "verbal — owner on call at 10:15."
3. **MOC candidate** — your first read on which existing MOC this belongs under. If none fits, the candidate is *propose a new MOC*.
4. **1-line summary** — what the item *says*, not what to do with it.
5. **Urgency flag** — same-day vs. next-day vs. backlog.
6. **Freshness flag** — does this *replace* an existing wiki page, *update* one, or is it a *net-new* atomic page?

These six fields are the contract between the person triaging (often the orchestrator) and the person writing the wiki page (often the librarian). Anything less and the librarian re-derives context for every page.

### Wren-writes / Larry-creates handoff (or your equivalent two-role split)

If your wiki tooling separates *writing the content* from *creating the file* (common in MCP-driven Drive setups), the handoff shape is:

1. **Librarian writes the atomic-page content** as markdown. Page is short — under one screen. Includes a "Source" line at the bottom pointing at Layer 1.
2. **Librarian writes the proposed index row** — the new row that should land in the index table.
3. **Librarian writes the log line** — date, page name, MOC, source pointer, one-sentence reason.
4. **Librarian hands the full package to the orchestrator** (or whoever has Drive write access).
5. **Orchestrator creates the file** in the wiki folder with the correct name.
6. **Orchestrator updates the index** with the new row.
7. **Orchestrator updates the log** with the new line.
8. **Orchestrator reports the file URL back to the librarian** for batched recording in the rulebook.

If one person plays both roles, the steps collapse but the discipline doesn't. Write content → write index row → write log line → save the file. All four. Skipping the log is the most common failure mode.

### Index-row format

```markdown
| <page name> | <MOC parent> | <1-line summary, ≤120 chars> | [link] |
```

### What does NOT go in the wiki

This is as important as what does. The wiki is **durable knowledge with cross-cutting reach**. The following stay in their native homes:

- **Raw meeting transcripts** — stay in your meeting tool. The wiki points at them.
- **Deliverables for the owner** — stay in `Owner's Inbox/`. The wiki points at them by path or by Drive ID.
- **Tactical to-dos / next-action lists** — stay in whatever task surface you use (a database, a task app, a list). The wiki captures durable knowledge, not transient action items.
- **Drafts in progress** — stay in `Team Inbox/` or working folders. A page enters the wiki when it carries durable knowledge, not while it's being drafted.
- **Source files uploaded to Drive** — stay in their Drive home. The wiki points at them by Drive ID.
- **Personal / private items** — only if the owner has scoped the wiki to include them.

A wiki page is durable when (a) it's likely to be referenced again, and (b) it's a *distillation*, not a copy of the source.

---

## Weekly rhythm

The cadence below is what works in practice. Tune to your week.

### Friday afternoon — MOC walk (30 minutes)

Owner + orchestrator (or owner alone if solo) walks the 3–5 MOCs. For each MOC:

- Read the MOC page.
- Skim the atomic page table.
- Flag anything that drifted, anything stale, anything that should split or merge.
- Make the calls on the spot. The log records what changed.

### Sunday evening — log paragraph (10 minutes)

Librarian writes a one-paragraph "wiki delta this week" entry into the log:

- Number of pages added, by MOC.
- Any pages retired.
- Any MOCs proposed for split, merge, or retirement.
- Anything escalated to the owner for a structural call.

### Monday morning — week kickoff (15 minutes)

Owner reviews:

- The Sunday log paragraph (what shifted last week).
- The 1–2 stale wiki items the librarian flagged.
- The freshness check on the most-active MOCs — is the index still accurate?

This is the cadence that keeps the wiki from drifting silently. Pick any three time slots that work in your week; consistency beats perfection.

---

## Anti-patterns to avoid

- **Skipping the log.** The log is the audit trail. A wiki without a log is a wiki you can't trust six months in.
- **Letting atomic pages bloat.** If a page passes ~one screen, split it into two. Atomicity is the property; long pages forfeit it.
- **Copying transcripts in.** The wiki points at sources, doesn't replace them. If you're copying, you've conflated Layer 1 and Layer 2.
- **Adding tags without definitions.** Tag vocabulary lives in `Library/tag-vocabulary.md`. Same discipline applies to wiki-level tagging.
- **Folder nesting for organization.** Stay flat for the first ~100 pages. Folders inside the wiki create premature structure.
- **Setting up the wiki without a Day 0 rulebook entry.** Wiki location, format choice (Docs vs. markdown), naming convention, log discipline — these are rulebook decisions. Record them when you set up, not "when you have time."

---

## First-week setup checklist

1. Decide parent folder.
2. Pick format — markdown or Google Docs. Record the decision in `Library/rulebook.md` with rationale.
3. Create the wiki folder.
4. Create the index file (use the shape above).
5. Create the log file (use the shape above) with one entry: "YYYY-MM-DD — Wiki created. Initial MOCs: [list]."
6. Create your 3–5 MOC files. Each starts with a one-paragraph scope statement and a (mostly empty) atomic-pages list.
7. Record the parent-folder ID and the seven-ish file IDs in `Library/rulebook.md` so the rulebook is the canonical pointer.
8. Set the Friday MOC walk on your calendar.
9. Stop. Don't try to populate atomic pages on day one. They accumulate by intake.

---

## What you'll learn after two weeks

- Whether your seed MOCs are right. (Usually 1 of them is wrong.)
- Whether the intake protocol fits your week. (Usually the urgency flag is the part that needs tuning.)
- Whether markdown vs. Docs was the right call. (Usually yes for markdown.)
- Whether 3–5 MOCs is the right count for your life right now. (Usually yes; sometimes 2.)

Write a short review memo at the two-week mark. Land it in `Owner's Inbox/` as `YYYY-MM-DD-wiki-review-week-2.md`. Then decide what to formalize and what to evolve.
