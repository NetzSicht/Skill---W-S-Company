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
  "comment": "Listing-Texte abgeschlossen. Titel: [X] Zeichen. 5 Bullets. Backend: [X] Bytes."
}
```
