# Tag Vocabulary

**Owner:** Wren (PKM Librarian)
**Status:** Living document. Every new tag lands here with a one-line definition before it ships.

---

## Why a controlled vocabulary

A flat tag list with no curation drifts fast. `meeting`, `Meeting`, `meetings`, `mtg`, `meet` will all appear within a month if nothing prevents it — and then a query for "all my meetings this quarter" silently misses half the rows. The cost of vocabulary discipline is a few seconds at write time. The cost of vocabulary drift is queries that quietly lie.

This file plus a write-path that consults it is the entire mechanism.

---

## Normalization rules (apply at write time)

Every write path — UI form, CLI insert, AI-assisted ingestion — must honor these rules:

1. **Lowercase only.** `CRM` → `crm`. Case-insensitive matching.
2. **Hyphen-separated.** No spaces, no underscores, no camelCase. `follow up` → `follow-up`.
3. **Singular nouns** unless inherently plural. `meetings` → `meeting`. `contacts` → `contact`.
4. **No leading / trailing whitespace.** Trim before insert.
5. **ASCII only for v1.** Non-ASCII gets flagged for librarian review.
6. **Max 30 characters.** Longer than that is usually a sentence pretending to be a tag.

If a normalized tag already exists in your store, reuse it. Do not insert a duplicate.

---

## Seed vocabulary (universal tags)

These are universal starters. The owner customizes from here.

| Tag | Definition | First used | Notes |
|---|---|---|---|
| `meeting` | A scheduled or ad-hoc conversation involving two or more people, recorded in the workspace. | _(YYYY-MM-DD)_ | Use on the artifact, not the participants. |
| `decision` | A point-in-time call the owner made, worth retrieving later. Includes rationale. | _(YYYY-MM-DD)_ | If the file IS a decision memo, also use `memo`. |
| `research` | Outside-world investigation: market, regulatory, technical, vendor, prior-art. | _(YYYY-MM-DD)_ | Add a domain-specific tag alongside (e.g., `research` + `competitive`). |
| `draft` | An in-progress artifact not yet ready for the owner or external sharing. | _(YYYY-MM-DD)_ | Drop the tag once the artifact ships. |
| `memo` | A short structured deliverable. Usually one author, one decision-grade ask. | _(YYYY-MM-DD)_ | Distinct from `brief` (longer-form) and `note` (working). |
| `brief` | A longer structured deliverable. Multiple sections, often briefing for a meeting or call. | _(YYYY-MM-DD)_ | Pair with the target meeting / event tag. |
| `routing` | A librarian routing call: "this artifact belongs here, in this folder, with this name." | _(YYYY-MM-DD)_ | Written when an artifact is genuinely novel and the rulebook needs a new entry. |
| `audit` | A periodic walk-through with findings + a fix list. Owned by the librarian (or whoever has audit lane). | _(YYYY-MM-DD)_ | Always paired with the surface audited (`audit` + `inbox`, etc.). |
| `archive` | An artifact that has been moved into an `Archive/` subfolder. | _(YYYY-MM-DD)_ | Applied at archive time, never at creation. |
| `reference` | Durable reference material the owner wants searchable but rarely edits. | _(YYYY-MM-DD)_ | Lives in `Resources/`. |

---

## How to add a tag (3-line workflow)

1. **Normalize** the proposed tag against the rules above.
2. **Check this vocabulary table** for an existing tag that means the same thing. If yes, use that one.
3. **If genuinely new, add a row to the table** with a one-line definition and the first-used date — *before* the tag ships to a row or file.

The "wait a beat" step is the entire point of vocabulary discipline. Free-text comma-separated tagging skips that pause and burns the audit budget on cleanup.

---

## Custom vocabulary (owner adds as the workspace grows)

The owner adds tags here as real content generates demand. A tag without a corresponding artifact is speculation; tags are added by use, not by anticipation.

Examples of where custom tags usually accumulate:

- **Project / venture tags** — one per active project or company.
- **Person tags** — one per recurring contact (or skip if your `contact` table handles this).
- **Domain tags** — `legal`, `tax`, `engineering`, `marketing`, `finance`, etc.
- **Status tags** — `open`, `blocked`, `done`, `parked`.
- **Audience tags** — `internal`, `external`, `investor`, `customer`.

| Tag | Definition | First used | Notes |
|---|---|---|---|
| _(add as needed)_ | | | |

---

## Decision log

| Date | Change | Rationale |
|---|---|---|
| {YYYY-MM-DD} | File created from starter-kit seed. Universal vocabulary seeded; custom vocabulary empty. | Day 0 of workspace. The seed is opinionated for a reason — extend by use, not by anticipation. |
