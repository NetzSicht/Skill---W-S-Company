# Heartbeat — Produkt-Analyst

Run this checklist every heartbeat. This is your execution loop.

## 1. Check for Tasks

- Look for new tasks assigned to you (new ASIN or product description)
- Look for revision requests from downstream agents (Listing-Briefer or Quality-Reviewer)

If no tasks: idle.

## 2. Gather Input

Read the task description. You will receive one or more of:

| Input Type | What To Do |
|---|---|
| ASIN | Pull all data from the Amazon listing |
| Product URL | Same as ASIN — extract ASIN first |
| Product description (manual) | Structure into analysis format |
| Product data sheet (PDF/doc) | Extract specs, materials, dimensions |
| Existing images | Evaluate current slot usage and quality |

## 3. Execute Analysis (7 Phases)

Work through these phases sequentially. Each phase fills a section of the output.

### Phase 1: Stammdaten
Collect: product name, brand, category, subcategory, price, price level (Budget/Mittel/Premium), FBA/FBM, Brand Registry status, A+ Content status.

### Phase 2: Zielgruppe
Define primary buyer persona: demographics, psychographics, purchase motivation, pain point, price sensitivity. Derive from review profiles and category norms — don't guess.

### Phase 3: Top-USPs
Identify 3-5 USPs. Prioritize by:
1. Differentiation (what competitors DON'T have)
2. Relevance (what buyers care about MOST)
3. Communicability (what can be shown VISUALLY)

Formulate as benefits, not features.

### Phase 4: Lieferumfang & Abmessungen
List every part included. Record all dimensions (H x W x D), weight, capacity, material, colors, variants.

### Phase 5: Zertifizierungen
Document every certification, seal, award, guarantee.

### Phase 6: Wettbewerber-Analyse
Analyze top 3-5 competitors by sales rank. For each: price, rating, strengths, weaknesses, image quality, slot usage. Then synthesize: where are we better / equal / behind? What visual gap exists?

### Phase 7: Kundenstimmen
Mine reviews (own + competitor): top 3 praise points, top 3 criticism points, most common question. Include frequency counts and example quotes.

### Phase 8: Bestehende Bilder (if optimization)
If existing listing: evaluate each used slot (content, quality, problems). Note unused slots.

### Phase 9: Strategie-Empfehlung
Recommend strategy type (Standard-Balanced / Feature-Lastig / Emotional / Kategorie-Spezifisch). State why. List top 3 objections the briefing must address. Add special notes for the Briefer.

## 4. Write Output

Write `produkt-analyse.md` in the exact Interface A format (see skill: produkt-analyse-interface). Every field must be filled or explicitly marked as unavailable.

## 5. Mark Task Complete

Mark your task as done. This triggers the Listing-Briefer to pick up your output.

## 6. Quality Self-Check

Before marking done, verify:
- [ ] All 10 sections of Interface A are present
- [ ] No fields are silently empty (either filled or marked `[NICHT VERFUEGBAR]`)
- [ ] USPs are formulated as benefits, not features
- [ ] Competitor analysis is balanced (strengths AND weaknesses)
- [ ] Strategy recommendation has a clear rationale
