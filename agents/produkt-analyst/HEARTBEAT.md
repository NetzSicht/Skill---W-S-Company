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

## 2bb. Check: Audit Available? (Optimization Mode)

Look for `listing-audit.md` in `./workspace/{task-id}/`. If it exists, you are in **Optimization Mode** — not a new listing.

Read the audit completely. Focus on Section 9 "Adaption-Anweisungen fuer downstream Agents → Fuer Produkt-Analyst". The audit tells you:

- **FOKUS:** Which specific aspects to research deeply (the gaps the audit identified)
- **SKIP:** Which data already exists in the audit — don't redo this work
- **PRUEFEN:** Which old assumptions need re-validation
- **KEEP-Daten:** Which existing data to carry forward unchanged

**Adaptation rules:**
- If audit says SKIP for an analysis phase: reference the audit in your output instead of redoing the analysis
- If audit says FOKUS: go deeper than usual on that phase
- If audit flagged a critical review cluster (e.g., "23% complain about sizing"): make sure your competitor analysis captures how competitors handle this
- Your output still follows Interface A format, but with cross-references to the audit where data is reused

If no audit exists: proceed as normal (new listing mode).

## 2c. Check: Research Mode?

Read the issue description. If it contains **"RESEARCH MODE"**: you are doing a Kategorie-Research, NOT a single-product analysis. Switch to the research workflow:

### Research Mode — Kategorie-Scan

1. Use Rainforest API `search` to find Top 15 organic listings:
   ```
   GET /request?api_key={KEY}&type=search&search_term={HAUPTKEYWORD}&amazon_domain=amazon.de&sort_by=relevance&number_of_results=15&exclude_sponsored=true
   ```

2. For each of the 15 ASINs, pull product data:
   ```
   GET /request?api_key={KEY}&type=product&asin={ASIN}&amazon_domain=amazon.de
   ```

3. For each ASIN, pull offers:
   ```
   GET /request?api_key={KEY}&type=offers&asin={ASIN}&amazon_domain=amazon.de
   ```

4. Analyze and write Sektionen 1.1 - 1.6 of `kategorie-research.md` per template (skill: `kategorie-research-template`):
   - **1.1 Top 15 Stammdaten-Tabelle** — ASIN, Titel, Marke, Preis, Bewertung, Reviews, BSR, FBA
   - **1.2 Preis-Analyse** — Budget/Mid/Premium Segmente, Sweet Spot, Preisschwelle
   - **1.3 Bild-Analyse** — Fuer JEDE ASIN: Welcher Bildtyp in welchem Slot? Dominante Muster? Visuelle Luecken? Haeufigste Fehler?
   - **1.4 Titel-Analyse** — Gemeinsame Formel der Top-Performer, was differenziert
   - **1.5 Bullet-Point-Analyse** — Haeufigste Themen pro BP, gemeinsame Schwaechen
   - **1.6 A+ Content Analyse** — Wer hat A+, welche Module, was fehlt

**Tiefenregel Bild-Analyse (1.3):**
- Fuer JEDE der 15 ASINs JEDES Bild kategorisieren: H=Hero, L=Lifestyle, I=Infografik, D=Dimension, M=Material, P=Pack, V=Vergleich, G=Groessentabelle, T=Trust
- Dann zaehlen: "X von 15 zeigen Lifestyle in Slot 2", "X von 15 haben Groessentabelle"
- Luecken identifizieren: "Was zeigt KEINES der 15 Listings?"

**Tiefenregel Preis-Analyse (1.2):**
- Stueckpreis berechnen bei Multipacks!
- "6er Pack fuer 14.99 = 2.50/Paar" — nicht nur den Pack-Preis nennen

After writing your sections: mark issue as done. Skip to Step 6 (Complete Task).

---

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
