# Larry — Personal Knowledge Assistant

**Plugin name:** `larry-pka`  
**Version:** 0.1.0  
**Based on:** The Karpathy Second Brain model

---

## What This Plugin Does

This plugin installs **Larry**, your AI Chief of Staff, into Claude. Larry orchestrates a team of specialist agents that help you manage your knowledge, make better decisions, and run your day.

Larry works best alongside the **LarryOS Obsidian vault** (included in the LarryOS Starter Kit), but all skills work standalone — just give Larry context from your life.

---

## Skills Included

| Skill | When it activates | What it does |
|-------|------------------|--------------|
| **Daily Brief** | "Morning brief", "What's on my plate" | Generates a prioritized daily brief from your context |
| **Specialist Dispatch** | "Should we…", "Legal risks of…", "Prep me for my call with…" | Routes to Hank (Strategy), Knox (Counsel), Felix (Finance), Sloane (Meeting Prep), or Pax (Research) |
| **Capture & Process** | "Process my inbox", pasting raw notes | Organizes raw captures into clean vault notes with action items |
| **Setup & Orientation** | "Set up LarryOS", "How do I get started" | Guides new users through first-time vault setup |

---

## The Larry Specialist Team

| Specialist | Domain | Hard Boundary |
|------------|--------|---------------|
| **Hank** | Strategy & Pre-Decision Memos | Licensed professionals → route out |
| **Knox** | Legal Framing & Steelman Analysis | Never binding legal advice |
| **Felix** | Finance & Tax Analysis | Never binding financial advice |
| **Sloane** | Meeting Prep & Account Briefs | — |
| **Pax** | Deep Research | — |

---

## How to Use Larry

### With context from your LarryOS vault:
1. Open your `08 Knowledge Base/About Me.md` file in Obsidian
2. Copy the contents
3. Paste into Claude: *"Larry — here's my context: [paste About Me]"*
4. Then ask anything

### Without a vault (starter mode):
Just talk to Larry directly. The more context you give, the better the responses.

### Trigger phrases:
- *"Morning brief"* → Daily Brief skill
- *"Should we…"* → Hank (Strategy)
- *"What are the legal risks of…"* → Knox (Counsel)
- *"Prep me for my call with [name]"* → Sloane (Meeting Prep)
- *"Research [topic]"* → Pax (Research)
- *"Process my inbox"* → Capture & Process skill
- *"Set up LarryOS"* → Setup & Orientation skill

---

## Getting the Full LarryOS Starter Kit

The LarryOS Starter Kit includes:
- The complete Obsidian vault template (pre-configured folder structure, templates, prompts)
- A step-by-step setup guide
- This plugin
- `custom-instructions-claude-ai.md` — a one-time paste that gives Larry a persistent identity on claude.ai (web) in addition to Claude Code

Ask whoever shared this plugin with you for the `LarryOS-Starter-Kit.zip` file.

---

*LarryOS v1.0 · Based on the Karpathy Second Brain model · Built with Claude*
