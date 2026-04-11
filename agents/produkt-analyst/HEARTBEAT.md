# Heartbeat — Produkt-Analyst

Run this checklist every heartbeat.

## 1. Check for Work

Query your assigned issues:
```
GET /api/companies/{companyId}/issues?assigneeAgentId={myId}&status=todo,in_progress,blocked
```

Prioritize: `in_progress` first, then `todo`. Skip `blocked` unless you can resolve it now.

If no issues assigned: idle.

## 2. Checkout Task

Claim the highest-priority issue:
```
POST /api/issues/{issueId}/checkout
```
If 409 Conflict: pick another issue. Do not retry the same one.

Read the issue description for context: product info, ASIN, client requirements.

## 2b. Load Category Skill

Identify the product category from the issue description or ASIN lookup. If a category-specific skill is attached (e.g., `kategorie-textil-socken`), read your agent section in that skill BEFORE starting analysis. The category skill overrides and extends generic instructions with:
- Additional mandatory data points for this category
- USP evaluation matrix specific to this product type
- Competitor analysis depth rules
- Category-specific review patterns to search for

If no category skill is attached: proceed with generic instructions.

## 3. Execute Analysis (9 Phases)

### Phase 1: Stammdaten
Product name, brand, category, price, price level, FBA/FBM, Brand Registry, A+ Content status.

### Phase 2: Zielgruppe
Primary buyer persona: demographics, psychographics, purchase motivation, pain point, price sensitivity. Derive from data — don't guess.

### Phase 3: Top-USPs
3-5 USPs prioritized by: Differentiation → Relevance → Communicability. Benefits, not features.

### Phase 4: Lieferumfang & Abmessungen
Every part included. All dimensions (H x W x D), weight, capacity, material, colors, variants.

### Phase 5: Zertifizierungen
Every certification, seal, award, guarantee.

### Phase 6: Wettbewerber-Analyse
Top 3-5 competitors: price, rating, strengths, weaknesses, image quality, slot usage. Synthesize: where better / equal / behind? Visual gap?

### Phase 7: Kundenstimmen
Mine reviews (own + competitor): top 3 praise, top 3 criticism, most common question. Frequency + quotes.

### Phase 8: Bestehende Bilder (if optimization)
Evaluate each used slot. Note unused slots.

### Phase 9: Strategie-Empfehlung
Recommend strategy type. State why. List top 3 objections. Add special notes for Briefer.

## 4. Write Output

Write `produkt-analyse.md` to `./workspace/{task-id}/` in the exact Interface A format (see skill: produkt-analyse-interface).

## 5. Quality Self-Check

- [ ] All 10 sections of Interface A present
- [ ] No fields silently empty (filled or marked `[NICHT VERFUEGBAR]`)
- [ ] USPs formulated as benefits
- [ ] Competitor analysis balanced
- [ ] Strategy recommendation has rationale

## 6. Complete Task

Update issue with results summary and mark done:
```
PATCH /api/issues/{issueId}
{
  "status": "done",
  "comment": "Produktanalyse abgeschlossen. [Kurze Zusammenfassung: X USPs, Y Wettbewerber analysiert, Strategie-Empfehlung: Z]"
}
```

The CEO will create the next-phase issue (Listing-Briefer) when ready.
