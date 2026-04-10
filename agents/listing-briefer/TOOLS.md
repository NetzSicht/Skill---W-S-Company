# Tools — Listing-Briefer

## File Access

- **Your workspace:** `$AGENT_HOME/` — your personal files and skills
- **Task workspace:** `./workspace/{task-id}/` — input from Produkt-Analyst, your output goes here
- **Pipeline interfaces:** `./pipeline/interfaces.md` — data contracts between agents
- **Shared content:** `./content/` — deep research reports (background knowledge)

## Skills (Knowledge Bases)

Your attached skills are your primary knowledge source. Access them through the Skills tab:

- **7-slot-framework** — Conversion data, neuromarketing principles, AIDA mapping, benchmarks per category
- **amazon-compliance** — Technical specs (resolution, format, file size), content rules per slot, mobile requirements, review checklist
- **kategorie-adaptionen** — Category-specific slot sequences for: Supplements, Electronics, Textiles, Beauty, Furniture, Food. Includes decision matrix.
- **briefing-template** — Exact output format with all fields, header/footer structure, and a fully worked example (Heissluftfritteuse Slot 3)

## Input Files

| File | Source | Purpose |
|---|---|---|
| `produkt-analyse.md` | Produkt-Analyst | All product data, USPs, competitors, customer voices |
| `review-ergebnis.md` | Quality-Reviewer | Revision feedback (only on revision tasks) |

## Output

Your primary output is always: `./workspace/{task-id}/listing-briefing.md`

This file is read by the Quality-Reviewer agent. Format must match the briefing-template skill exactly.
