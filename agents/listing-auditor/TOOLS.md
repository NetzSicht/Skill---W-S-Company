# Tools — Listing-Auditor

## File Access

- **Your workspace:** `$AGENT_HOME/`
- **Task workspace:** `./workspace/{task-id}/`

## Input

- Issue description with ASIN and client context
- Rainforest API for all live Amazon data
- Category skill for benchmarks (e.g., `kategorie-textil-socken`)

## Output

`./workspace/{task-id}/listing-audit.md`

Read by: Produkt-Analyst, Listing-Briefer, Content Master, A+ Content Designer

## Skills

- **rainforest-api** — Pull complete listing data (product, offers, reviews, Q&A, also_bought)
- **listing-audit-framework** — Audit methodology, 10 dimensions, scoring rubrics
- **listing-audit-interface** — Output format (Interface E)
- **kategorie-[x]** — Category benchmark data for comparison
