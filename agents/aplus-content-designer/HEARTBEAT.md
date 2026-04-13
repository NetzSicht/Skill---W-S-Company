# Heartbeat — A+ Content Designer

Run this checklist every heartbeat.

## 1. Check for Work

```
GET /api/companies/{companyId}/issues?assigneeAgentId={myId}&status=todo,in_progress,blocked
```

Only start when image briefing AND listing texts are approved.

## 2. Checkout Task

```
POST /api/issues/{issueId}/checkout
```

## 2b. Load Category Skill

Read the product category from `produkt-analyse.md`. If a category-specific skill is attached (e.g., `kategorie-textil-socken`), read your agent section BEFORE building A+ modules. The category skill provides:
- Category-specific A+ module recommendations
- What the gallery typically covers vs. what A+ must extend
- Anti-duplication examples for this product type

## 2c. Check: Audit Available? (Optimization Mode)

Look for `listing-audit.md` in `./workspace/{task-id}/`. If it exists:

1. Read Section 9 "Fuer A+ Content Designer" — which modules are KEEP/ENHANCE/REBUILD/MISSING
2. Read Dimension 7 (A+ Content) and Dimension 8 (Brand Story) from the audit
3. Respect the status tags — do not redesign modules that already perform

If current A+ Content is REBUILD: ignore it completely, design from scratch
If current A+ Content is ENHANCE: use as baseline, improve specific modules
If current A+ Content is KEEP: carry forward as-is, only add MISSING modules

If no audit exists: proceed as normal (new listing mode).

## 3. Read Input Documents

- `listing-briefing.md` — Gallery content (to avoid duplication). Read the **A+ Uebergabe** section first.
- `listing-texte.md` — Bullet/description content (to avoid duplication)
- `review-insights.md` — Unanswered questions, objections
- `produkt-analyse.md` — Product data, brand info

## 4. Determine A+ Format

| Condition | Format |
|---|---|
| Brand Registry active, no Premium | **Basic A+** (max 5 modules, 970px) |
| Premium A+ eligible | **Premium A+** (max 7 modules, full-width, interactive) |
| No Brand Registry | **No A+** — focus on product description |

## 5. Build Module Plan

Per skill **listing-content-architektur**: A+ extends the gallery story, never repeats it.

### Recommended Sequence

| Module | Purpose | Content |
|---|---|---|
| Brand Story | Trust + Cross-Sell | Brand origin, mission, product carousel |
| Hero Banner | Emotional anchor | Full-width lifestyle + value proposition |
| Feature Breakdown | Deep education | Aspects NOT covered in gallery |
| Use Case Scenarios | Expand audience | 2-3 different usage contexts |
| Comparison Matrix | Defensive retention | Own product VARIANTS (not competitors!) |
| FAQ / Trust | Remove barriers | Top customer questions + certifications |

## 6. Brief Each Module

Per module:
- Module type (Standard Image+Text, Full-width, Comparison, etc.)
- Image requirements (what to show, what NOT to repeat from gallery)
- Text content (headlines, body, alt-text for SEO)
- How it complements the gallery

## 7. Self-Check

- [ ] No image duplicates from gallery
- [ ] No text duplicates from bullets/description
- [ ] Brand Story included (if Brand Registry)
- [ ] Comparison chart uses own variants, not competitor names
- [ ] 70/30 visual-to-text ratio
- [ ] Alt-texts include relevant keywords
- [ ] Narrative arc: gallery → brand story → A+ is coherent
- [ ] Customer questions from Review-Analyst addressed

## 7b. Mobile-First Validation

Nach Erstellung des A+ Briefings: Mobile-First Validation (siehe Skill `mobile-first-validation` — besonders Test 6 "A+ Content Mobile-Check"). Pruefe jedes Modul gegen die Mobile-Regeln. Alt-Texte MUESSEN gefuellt sein (Rufus-SEO + Mobile Screen Reader).

## 8. Write Output

Write `aplus-briefing.md` to `./workspace/{task-id}/`.

## 9. Complete Task

```
PATCH /api/issues/{issueId}
{
  "status": "done",
  "comment": "@ceo A+ Briefing abgeschlossen. Format: [Basic/Premium]. [X] Module definiert. Keine Galerie-Duplikate. Output: aplus-briefing.md im Workspace."
}
```
