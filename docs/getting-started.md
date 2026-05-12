# Getting Started — Your First 30 Minutes

A step-by-step setup guide for new adopters of the Larry PKA starter kit. Plan for 30 minutes. You don't need to finish in one sitting.

---

## Before you start

You'll need:

- A machine with [Claude Code](https://docs.claude.com/en/docs/claude-code/overview) installed (macOS, Linux, or Windows / WSL).
- A clone of this starter-kit repo somewhere on your filesystem. The workspace is the cloned folder.
- Optional but recommended: a Google account if you want to wire up Drive / Gmail / Calendar.
- Optional but recommended: a meeting tool like Krisp, Granola, or Otter if you want transcripts to flow in.

---

## Step 1 — Install Claude Code

If you don't have Claude Code installed already:

- **Docs:** [https://docs.claude.com/en/docs/claude-code/overview](https://docs.claude.com/en/docs/claude-code/overview)
- **Install:** follow the platform-specific instructions in the docs.

Verify the install:

```bash
claude --version
```

If that works, you're ready. If it doesn't, fix the install before continuing — the rest of the setup assumes a working Claude Code.

---

## Step 2 — Read the workspace CLAUDE.md

The file `CLAUDE.md` at the root of the cloned repo is your **orchestrator's identity file** (Larry, in the default team). Read it once before doing anything else.

Two things to absorb:

1. **The iron rule.** Larry never does work himself. He routes every task to a named team member. This is the entire shape of how you'll interact with the team.
2. **The named-team model.** You can address Larry directly ("Larry, route this to ...") or address a team member by name ("Pax, research X"). When you don't name anyone, Larry decides.

You don't need to memorize the file. Read it once so you know what's in it; refer back when something surprises you.

---

## Step 3 — Pick your specialists

The HR specialist (Nolan) ships with a roster of 12 generalized role templates in `.claude/agents/`. Each role has a **"when to keep me / when to skip me" note** at the top.

Walk the roster. Delete the role files you don't need. Keep the ones that match your life right now.

Suggested starting set for most adopters:

- **Larry** — orchestrator. Always keep.
- **Nolan** — HR. Always keep. He's the one who modifies the team.
- **Pax** — researcher. Almost always keep. The "I need this researched" lane is hard to do without.
- **Wren** — librarian. Almost always keep. Organization decays without this lane.
- **One or two domain specialists** — whichever match your active work (legal counsel, CPA, strategic advisor, sales pursuit, engineering, etc.).

Start narrow. You can ask Nolan to hire new specialists as needs become real. Hiring on speculation produces specialists that never get used.

---

## Step 4 — Fill in your Day 0 rulebook entry

Open `Library/rulebook.md`. Find the **Day 0 entry template**:

```markdown
### {YYYY-MM-DD} — Workspace initialized

**Owner:** {NAME}
**Methodology:** PARA + Johnny-Decimal-naming + DB-first (inherited from starter-kit seed; subject to evolution as audit evidence accumulates).
**Workspace surfaces in scope:** local filesystem (this repo).
```

Replace `{YYYY-MM-DD}` with today's date. Replace `{NAME}` with your name (or the workspace owner's name). Add any other surfaces you want the librarian to govern (Google Drive, Notion, etc.).

This entry is the first commit in the rulebook's decision log. Every future decision builds on it.

While you're in `Library/`, take a look at:

- **`Library/tag-vocabulary.md`** — the seed universal tags. Read once so you know what's there; don't customize yet.
- **`Library/relocation-log.md`** — empty with a placeholder example. Will populate as the workspace moves files around.

---

## Step 5 — Set up Drive folders + the wiki (optional but recommended)

If you want the AI team to maintain a Karpathy-style LLM Wiki in your Drive (recommended for most users):

1. Read **`docs/karpathy-llm-wiki-guide.md`** end-to-end. It's the deepest part of the kit.
2. Follow the **First-week setup checklist** at the bottom of that guide.
3. Decide your **3–5 seed MOCs** based on what's most active in your life *right now*.
4. Create the wiki folder + index + log + MOCs in Drive.
5. Record the file IDs in `Library/rulebook.md` under a new dated decision-log entry.

You can skip this step on day one and add it later. The rest of the kit works without a Drive wiki.

---

## Step 6 — Connect MCPs

If you want the team to reach external surfaces (Gmail, Calendar, Drive, meeting tools), connect the MCP servers via [claude.ai connectors](https://docs.claude.com/en/docs/build-with-claude/mcp).

Common connections:

- **Google Drive** — for the wiki, file storage, document creation.
- **Gmail** — for searching / drafting email.
- **Google Calendar** — for scheduling, meeting context.
- **A meeting tool** (Krisp, Granola, Otter) — for transcripts and action items.

Connect only what you'll use. Each MCP is a surface the team has to be careful about. Fewer surfaces = clearer boundaries.

---

## Step 7 — Talk to Larry

Open Claude Code in your workspace folder:

```bash
claude
```

Try a few sentences to feel the routing layer:

- *"Larry, route a one-paragraph summary of this guide to Pax."*
- *"Larry, ask Wren what folder a one-off vendor evaluation should go in."*
- *"Pax, research how PARA evolved between 2024 and 2026."*

Watch what Larry does — he picks the right specialist and relays their output. He doesn't do the work himself. If you ever catch him doing the work directly, that's a bug; remind him of the iron rule.

---

## Step 8 — After 1 week, review

Set a calendar reminder for one week from today.

When the reminder fires:

1. Open `Library/rulebook.md` and read every entry that landed in the last week.
2. Walk the two inboxes. Anything stale gets archived or killed.
3. Ask Wren for a library audit: *"Wren, run a library audit on the workspace."*
4. Read her audit. Act on what makes sense; ignore what doesn't.
5. If a specialist hasn't gotten used at all, consider retiring them (ask Nolan).
6. If something feels missing, consider hiring a new specialist (ask Nolan, who will route to Pax for research first).

The starter kit is opinionated for a reason. Keep the defaults intact for the first month. After a month of real use, you'll have the audit evidence to evolve confidently.

---

## What to do when something breaks

- **An agent went off-lane.** Ask Larry to remind them of their role file. Or open `.claude/agents/<name>.md` and read the lane line yourself.
- **A file ended up in the wrong place.** Ask Wren to route it. She'll move it and log the move in `Library/relocation-log.md`.
- **The team feels too small or too big.** Ask Nolan. He hires and retires.
- **You're not sure who to ask.** Ask Larry. That's literally his job.

---

## What this starter kit is not

- It's not a turnkey "do my work for me" system. The team is a routing + drafting + organizing layer. You still make the calls.
- It's not a replacement for the apps you already use. The wiki lives in Drive (or your chosen surface); meeting transcripts live in your meeting tool; email lives in your mailbox. The kit references them; it doesn't replace them.
- It's not finished. Every workspace evolves. The rulebook + the team + the wiki all grow with use.

Welcome aboard.
