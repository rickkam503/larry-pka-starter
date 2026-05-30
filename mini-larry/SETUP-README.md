# Mini-Larry on iPhone — Setup Guide

A ten-minute setup. Do steps 1–4 from a desktop browser (faster than mobile for paste-and-upload), then steps 5–7 on the phone.

## 1. Install the Claude iOS app

App Store → search "Claude" by Anthropic → install → sign in with the same account you use at claude.ai.
Link: https://apps.apple.com/app/claude-by-anthropic/id6473753684

## 2. Create the Project on claude.ai (web)

Open https://claude.ai in a desktop browser.
Left sidebar → **Projects** → **New Project**.
Name it exactly: **Larry**.
Description (optional): *"Rick's AI chief of staff — iPhone edition."*

## 3. Paste the custom instructions

In the new Project → **Custom instructions** field → paste the full contents of `custom-instructions.md` (sibling to this file).
Save.

## 4. Upload the project knowledge

In the Project → **Project knowledge** → upload each file from the `project-knowledge/` sibling folder, one at a time. Wren prepared these — they include the team roster, the wiki snapshot, and key memos Mini-Larry needs as background.

## 5. Open the iOS app

Launch Claude on iPhone. Tap **Projects** in the bottom or side nav. The **Larry** project will appear — it syncs from your account.

## 6. Pin or star Larry

In the Projects list, long-press **Larry** → pin (or star, depending on app version) so he's the default project when you open the app. This is how you avoid talking to a fresh empty Claude by mistake.

## 7. Talk to Larry

Open the **Larry** project. Two ways to talk:

- **Mic icon** (next to the text field) — voice-to-text. You speak, Claude transcribes, then types a reply. Best when you're in a quiet spot but might want to read.
- **Sphere / voice-mode icon** — full voice conversation. Larry speaks back. Best for the car, walks, hands-busy moments.

## Caveats to remember (full list is in custom-instructions.md)

- Mini-Larry **cannot dispatch the 12-member agent team** — he channels their voices instead.
- Mini-Larry **cannot read local Mac files** — no Owner's Inbox, no `.claude/agents/`, no local Library.
- Mini-Larry **cannot run the `pkm` CLI** or query the local PKM database.
- Capture anything important; Wren folds it into the wiki at the morning sweep.
- Connectors (Krisp, Gmail, Drive, Calendar) are live — same account as desktop.

## Maintenance

When the wiki or roster changes meaningfully on the laptop, re-upload the affected file(s) in **Project knowledge** to keep Mini-Larry in sync. Wren handles this on the morning sweep.
