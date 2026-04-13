# Heartbeat — Content Master

Run this checklist every heartbeat.

## 1. Check for Work

```
GET /api/companies/{companyId}/issues?assigneeAgentId={myId}&status=todo,in_progress,blocked
```

## 2. Checkout Task

```
POST /api/issues/{issueId}/checkout
```

Read issue description. Check available files in `./workspace/{task-id}/`.

## 2b. Load Category Skill

Read the product category from `produkt-analyse.md`. If a category-specific skill is attached (e.g., `kategorie-textil-socken`), read your agent section BEFORE writing copy. The category skill provides:
- Category-specific title formula with examples
- Bullet point hierarchy adapted to this product type
- Mandatory keywords and keyword patterns
- PAN-EU keyword lists per marketplace

## 2c. Check: Audit Available? (Optimization Mode)

Look for `listing-audit.md` in `./workspace/{task-id}/`. If it exists:

1. Read the complete audit, especially Section 9 "Fuer Content Master".
2. For each text element (Title, BP1-5, Backend Keywords) the audit provides a status: **KEEP / ENHANCE / REBUILD / MISSING**

| Audit Status | What You Do |
|---|---|
| **KEEP** | Copy the current text unchanged into `listing-texte.md`. Mark it: "(KEEP — aus aktuellem Listing uebernommen)". Do NOT rewrite. |
| **ENHANCE** | Use the current text as baseline. Improve only what the audit fix-instruction says. Preserve tone, keywords, structure. |
| **REBUILD** | Write completely new. Ignore the current version. |
| **MISSING** | Write new (e.g., PAN-EU backend keywords not yet present). |

Your output format stays the same, but each element now starts with the status tag.

**Critical:** Do not rewrite working titles or bullets. If the audit says the current BP2 performs well, keep it verbatim. Optimization means surgical changes, not full rewrites.

If no audit exists: proceed as normal (new listing mode).

## 3. Read Input Documents

- `produkt-analyse.md` — Product data, USPs, target audience
- `keyword-strategie.md` — Primary keywords, long-tails, placement plan
- `review-insights.md` — Customer language, praise, criticism
- `listing-briefing.md` — Image briefing (if available, for text-image synergy)

## 4. Create Listing Title

Formula: **Brand + Top Intent Phrase + Feature Group + Use Case + Specs**

- 150-180 characters total
- First 70 characters: brand + primary keyword (mobile visibility)
- Natural language — no keyword stuffing
- Must match what buyer sees in Hero Image

## 5. Create Bullet Points (5x)

| Bullet | Focus | Synergy With |
|---|---|---|
| BP1 | Primary USP — transformative benefit | Slot 2 + 3 |
| BP2 | Technical superiority | Slot 4 + 5 |
| BP3 | Secondary technical benefit | Slot 5 |
| BP4 | Preemptive objection handling | Review insights |
| BP5 | Risk reversal — guarantee, service, contents | Slot 6 + 7 |

Per bullet: CAPS anchor + benefit statement. Max 200 chars. 1-2 keywords naturally.

## 6. Backend Keywords

- Max 250 bytes
- No duplicates from title/bullets
- Include: misspellings, synonyms, long-tail variations
- No brand names, ASINs, subjective claims

## 7. Self-Check

- [ ] Title: 150-180 chars, primary keyword in first 70
- [ ] 5 bullet points follow hierarchy
- [ ] Bullet-image synergy verified (if briefing available)
- [ ] Customer language from reviews used (≥3 phrases)
- [ ] All primary keywords placed
- [ ] Backend keywords: no duplicates, ≤250 bytes

## 8. Write Output

Write `listing-texte.md` to `./workspace/{task-id}/`.

## 9. Complete Task

```
PATCH /api/issues/{issueId}
{
  "status": "done",
  "comment": "@ceo Listing-Texte abgeschlossen. Titel: [X] Zeichen. 5 Bullets. Backend: [X] Bytes. Output: listing-texte.md im Workspace."
}
```
