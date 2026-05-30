# Glossary

Domain terms Mini-Larry should recognize on first reference. One line each.

---

## Entities and brands

- **AcuityFirst.ai, Inc.** — The canonical entity name as of 2026-05-12. Delaware C-Corp in formation. Replaces "Aculine" as the working name.
- **Aculine** — Retired placeholder name (April 2026). Any current reference is either stale or preserved as legal-evidence-of-record.
- **FSM Drive** — The product. AcuityFirst.ai's governance and workflow orchestration platform; the customer-facing surface.
- **a1ai.site** — Internal AcuityFirst.ai property. Hosts the BD Sales Pipeline Targeting Dashboard. Future home for the orchestration team.
- **ELSA** — E.L. Stull and Associates, Inc. Ed's operating S-Corp. Current holder of FSM Drive IP, which will assign to AcuityFirst.ai at formation.
- **hand6** — The v6 (final) Aculine context handoff document. Lives in `My Drive/98_AI_Context_Handoff_Memory/`. Filename `Aculine_Context_Handoff_Apr2026.docx`.

## Technical terms

- **FSM** — Finite State Machine. The deterministic governance layer over non-deterministic AI output that gives FSM Drive its name and its conductor-of-AI talk-track.
- **Operational ontology** — The architectural primitive under FSM Drive. Lets AI reason operationally, not just verbally — modeling entities, relationships, workflows, dependencies, permissions, and states over the customer's systems of record.
- **A1AI-FSM Normal Form** — The specific structural discipline (rules R1-R7) AcuityFirst is trying to patent through IP-001. NOT FSMs in general — a particular FSM-construction technique.
- **PKM** — Personal Knowledge Management. The local SQLite-backed knowledge store on Rick's laptop. The `pkm` CLI runs against it.

## Tax / legal terms

- **§1202** (IRC §1202) — Qualified Small Business Stock exclusion. Drives the C-Corp structure choice. Post-OBBBA: tiered 3-year / 50%, 4-year / 75%, 5-year+ / 100% exclusion. Gross-asset cap $75M, per-issuer cap $15M or 10x. Stock issued at AcuityFirst.ai formation will be post-OBBBA / new-rule QSBS.
- **QSBS** — Qualified Small Business Stock. The §1202-eligible founder stock.
- **§174A** (IRC §174A) — Domestic R&E immediately deductible. Restored by OBBBA effective 2025-01-01. Small-business retroactive amendment window for 2022-2023 closes earlier of 2026-07-06 or normal refund SOL.
- **§41** (IRC §41) — R&D credit. §41(h) payroll-tax offset for QSBs with under $5M gross receipts and 5-or-fewer years of receipts. AcuityFirst will trivially qualify at formation.
- **§195** (IRC §195) — Start-up expenses treatment. $5,000 immediate deduction + 180-month amortization. Applies to pre-incorporation R&E spend on Rick's personal cards.
- **§83(b)** — Election to include restricted property in income at grant. 30-day deadline statutory and unforgivable. Fires the moment Rick signs his Founder SPA; must be filed within 30 days of share purchase.
- **§1045** — Capital-gain rollover from one QSBS to another. 60-day window. Fallback if AcuityFirst sells before the 5-year §1202 mark.
- **§469** — Passive Activity Loss rules. Relevant to Rick's Form 8582 PAL pool (ID Mentor, Private Equity Co-Invest).
- **Accountable plan** — IRC §62(c) + Treas. Reg. §1.62-2. Mechanism that makes reimbursements to Rick from AcuityFirst NOT W-2 income. Required to be in place before any reimbursement.
- **OBBBA** — One Big Beautiful Bill Act, P.L. 119-21, signed 2025-07-04. Restored §174A immediate expensing, modified §1202 (post-OBBBA rules apply to stock issued after 2025-07-04), various other items.
- **TCJA** — Tax Cuts and Jobs Act, P.L. 115-97, signed 2017-12-22. Source of the $10K SALT cap (modified but extended by OBBBA), §174 original capitalization rule (now restored by §174A), §199A QBI deduction.
- **OBBBA-modified §1202** — Post-2025-07-04 stock. Tiered 3/4/5-year exclusion; $75M gross-asset cap; $15M-or-10x per-issuer gain cap.
- **PI practice** — Personal Injury chiropractic. Mike Kam's business in Portland, OR. The FSM Drive vertical proof-point.
- **LOP** — Letter of Protection. PI billing term — agreement signed by a PI attorney pledging payment to a provider out of any future settlement or judgment.
- **PIP** — Personal Injury Protection insurance. PI billing term — first-party medical coverage available regardless of fault, common in no-fault auto states.

## Methodology / framework terms

- **MOC** — Map of Content. A wiki page that organizes and links to atomic pages within a single project or topic area. The AcuityFirst wiki has five MOCs: AcuityFirst.ai, FSM Drive, Leader Bank, Marty advisory, AI Team.
- **Karpathy LLM Wiki** — The wiki pattern Rick is using. Three layers: raw sources stay where they live; LLM-maintained interlinked wiki of short atomic pages organized under MOCs; query layer where good answers file back into the wiki so the corpus compounds. Gist 2026-04-03 by Andrej Karpathy.
- **Pre-Decision Memo** — Hank's standard format for any non-trivial commitment. Decision being made; the options; the recommendation; the risks. Short.
- **Steelman Against** — Knox's mandatory section in every legal memo. The strongest argument against the proposed action, written in good faith.
- **Citations and As-Of** — Felix's mandatory section in every tax memo. Source statute or regulation, plus the date that source was last verified. Tax law moves; everything has a half-life.
- **Iron rule** — Larry's: never do the work himself, always delegate. On iPhone Mini-Larry adapts: answer directly in the right specialist's voice, name who he's channeling, and queue heavy lifting for the laptop.

## Workspace / file conventions

- **Owner's Inbox** — Local folder `Owner's Inbox - Working folder for AI to share with me/`. Where the team drops finished deliverables for Rick.
- **Team Inbox** — Local folder `Team Inbox - Move working files to give AI team to work with/`. Where Rick drops files for the team and where intra-team handoffs land.
- **Library** — Local folder `Library/`. Wren's rulebooks, tag vocabulary, audits, relocation log. Source of truth on naming and routing rules.
- **YYYY-MM-DD-** — ISO 8601 date prefix on every working file. Rick's date format discipline. Wren's lane.
