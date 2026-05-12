# Larry PKA Starter Kit

A personal-knowledge-assistant orchestrator pattern for [Claude Code](https://claude.com/claude-code). **Larry** is the AI chief of staff; a named team of specialists handles the actual work; you talk to Larry, Larry routes, the right specialist responds.

Inspired by [Andrej Karpathy's LLM Wiki pattern](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f) for the knowledge layer, and the named-team orchestrator pattern (closest structural analogue: [BMAD-METHOD](https://github.com/bmad-method)) for the agent layer. The differentiator is the **named personality layer** — each specialist has a name, a voice, and a lane — which makes the team feel like a team, not a chatbot.

## The iron rule

> **Larry never carries out work himself.** No research, no writing, no analysis, no coding. Every task gets delegated to the right specialist.

This is the load-bearing pattern. It forces you (the owner) to think of your AI as a team you direct, not a single brain you query.

## What's in the kit

```
CLAUDE.md                    — Larry's identity + the iron rule + how you talk to the team
.claude/agents/              — 10 specialist role files (drop the ones you don't need)
Library/                     — your operating rulebook, tag vocabulary, relocation log
Owner's Inbox/               — where the team drops finished work for you
Team Inbox/                  — where you drop files for the team to work on (Archive/ subfolder included)
Team - AI team of agents/    — human-readable profiles for the specialists you keep
docs/
  ├─ getting-started.md      — 30-minute first-time setup walkthrough
  ├─ folder-structure.md     — workspace map and lifecycle rules
  └─ karpathy-llm-wiki-guide.md  — how to set up the wiki on Google Drive
```

## The team (10 specialists in this v1)

| Specialist | Lane | Keep me if… |
|---|---|---|
| **Nolan** — HR Manager | Hires new specialists; writes role files | Always — universal core |
| **Pax** — Senior Researcher | Cited, date-stamped outside research | Always — universal core |
| **Wren** — PKM Librarian | Folder rules, tag vocabulary, the wiki, audits | Always — universal core |
| **Mira** — Database Architect | SQLite schema, FTS5, sqlite-vec, migrations | You're building a local PKM stack |
| **Cleo** — CLI Engineer | The `pkm` CLI; library shape; named parameters | You're building a local PKM stack |
| **Theo** — Local Application Engineer | Local web UI over your knowledge store | You're building a local PKM stack |
| **Hank** — Strategic Advisor | Pre-Decision Memos, competitive landscape, kill/scale calls | You have business or venture work |
| **Sloane** — Pursuit Advisor | Account briefs, outbound sequences, pricing menus | You have sales/BD pursuit work |
| **Knox** — Startup Counsel | Legal issue-spotting; never binding advice | You have legal-adjacent work |
| **Felix** — SaaS CPA | Federal + multi-state tax; never signs returns | You have tax-adjacent work |

Each role file starts with a **"When to keep this specialist"** note (look at the top of each `.claude/agents/<name>.md` file). Drop the ones that don't apply to you; keep the universal core (Larry / Nolan / Pax / Wren) at minimum.

## How you talk to the team

- **Address Larry directly:** *"Larry, …"*
- **Address a specialist by name:** *"Pax, research X"* or *"Nolan, hire someone who can Y"* — Larry routes the call.
- **Give a task without naming anyone:** Larry picks the right specialist.

## Setup

See `docs/getting-started.md`. Short version:

1. Clone this repo to your machine. Rename the root folder to something meaningful for you.
2. Install [Claude Code](https://claude.com/claude-code).
3. Read `CLAUDE.md` so you understand the iron rule and the routing pattern.
4. Open the `.claude/agents/` folder. Delete the role files for specialists you don't need. Customize the ones you keep (especially Hank, Sloane, Knox, Felix — they have venture-specific scope that needs your details).
5. Fill in your Day 0 entry in `Library/rulebook.md` (your name, workspace, methodology).
6. Optional: set up the wiki on Google Drive per `docs/karpathy-llm-wiki-guide.md`.
7. Connect MCP tools (Krisp, Gmail, Drive, Calendar — at the [claude.ai connectors](https://claude.ai/customize/connectors) level).
8. Talk to Larry. Start small.

## License

MIT. See `LICENSE`.

## Credit

Built originally as one user's working setup, then generalized by that user's own team — Pax did the prior-art recon; Nolan generalized the 10 role files; Wren scaffolded the Library and wrote the wiki guide; Larry assembled and pushed the repo.

The pattern is the gift. Take it, customize it, evolve it.
