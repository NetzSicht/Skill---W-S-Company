# Tools — Quality-Reviewer

## File Access

- **Your workspace:** `$AGENT_HOME/` — your personal files and skills
- **Task workspace:** `./workspace/{task-id}/` — briefing to review, your output goes here
- **Pipeline interfaces:** `./pipeline/interfaces.md` — data contracts between agents

## Skills (Knowledge Bases)

Your attached skills are your primary rule sets. Access them through the Skills tab:

- **amazon-compliance** — Amazon image guidelines, technical specs, content rules, mobile requirements, category-specific compliance
- **kategorie-regeln** — Category-specific slot requirements and mandatory elements
- **review-interface** — The exact output format for `review-ergebnis.md` (Interface C)

## Input Files

| File | Source | Purpose |
|---|---|---|
| `listing-briefing.md` | Listing-Briefer | The briefing to review |
| `produkt-analyse.md` | Produkt-Analyst | Context: product data, USPs, objections |

## Output

Your primary output is always: `./workspace/{task-id}/review-ergebnis.md`

This file determines the next step:
- APPROVED → Briefing goes to designer
- REVISION_NOETIG → Back to Listing-Briefer
- ABGELEHNT → Back to Produkt-Analyst
