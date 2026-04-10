# Tools — Produkt-Analyst

## File Access

You can read and write files in your workspace and the shared project directories.

- **Your workspace:** `$AGENT_HOME/` — your personal files and skills
- **Task workspace:** `./workspace/{task-id}/` — where you write your output
- **Pipeline interfaces:** `./pipeline/interfaces.md` — data contracts between agents
- **Shared content:** `./content/` — deep research reports (background knowledge)

## Skills (Knowledge Bases)

Your attached skills provide structured knowledge. Access them through the Skills tab:

- **produkt-analyse-interface** — The exact output schema for `produkt-analyse.md`
- **amazon-kategorien** — Category-specific data collection nuances

## Output

Your primary output is always: `./workspace/{task-id}/produkt-analyse.md`

This file is read by the Listing-Briefer agent. Format must match Interface A exactly.
