# Heartbeat — Review-Analyst

Run this checklist every heartbeat.

## 1. Check for Work

```
GET /api/companies/{companyId}/issues?assigneeAgentId={myId}&status=todo,in_progress,blocked
```

## 2. Checkout Task

```
POST /api/issues/{issueId}/checkout
```

## 2b. Load Category Skill

Read the product category from `produkt-analyse.md`. If a category-specific skill is attached (e.g., `kategorie-textil-socken`), read your agent section BEFORE analyzing reviews. The category skill provides:
- Category-specific review search patterns (exact terms to search for)
- Frequency thresholds for this product type
- Language extraction templates with minimum phrase counts
- Common objection clusters specific to this category

## 3. Read Input

- `produkt-analyse.md` — Product info, competitor ASINs
- Access product and competitor reviews on Amazon

## 3b. Check: Research Mode?

If issue description contains **"RESEARCH MODE"**: you are doing a Kategorie-Research across the Top 15 Listings, NOT a single-product analysis.

### Research Mode — Kategorie-Reviews

1. Read the ASIN-Liste from `kategorie-research.md` Section 1.1 (written by Produkt-Analyst). If not yet available, use the ASINs from the issue description.

2. For each of the Top 15 ASINs, pull reviews via Rainforest API:
   ```
   # Positive Reviews
   GET /request?api_key={KEY}&type=reviews&asin={ASIN}&amazon_domain=amazon.de&star_rating=positive&sort_by=most_helpful
   
   # Critical Reviews
   GET /request?api_key={KEY}&type=reviews&asin={ASIN}&amazon_domain=amazon.de&star_rating=critical&sort_by=most_helpful
   
   # Q&A
   GET /request?api_key={KEY}&type=questions&asin={ASIN}&amazon_domain=amazon.de
   ```

3. Write Sektionen 2.1 - 2.7 of `kategorie-research.md` per template (skill: `kategorie-research-template`):
   - **2.1 Aggregierte Review-Analyse** — Gesamt-Reviews analysiert, Durchschnittsbewertung
   - **2.2 Top-Lob (10x)** — Thema, Haeufigkeit, exaktes Zitat, Slot/BP-Empfehlung
   - **2.3 Top-Kritik (10x)** — Thema, Haeufigkeit, exaktes Zitat, wie adressieren
   - **2.4 Einwand-Cluster** — Zusammenhaengende Einwaende gruppieren mit Kritikalitaet
   - **2.5 Kunden-Vokabular-Bank** — Mindestens 20 exakte Kunden-Zitate, 3+ pro Sentiment-Kategorie
   - **2.6 Q&A-Luecken** — Haeufigste unbeantwortete Fragen
   - **2.7 Kaeufer-Personas** — Wer kauft diese Kategorie? (aus Review-Profilen ableiten)

**Tiefenregel Vokabular (2.5):**
- EXAKTE Kunden-Worte, nicht deine Zusammenfassung
- FALSCH: "Kunden loben die Passform" 
- RICHTIG: "sitzen wie angegossen" (14x), "kein Verrutschen" (9x), "perfekter Halt in Sportschuhen" (7x)
- Minimum 20 Phrasen, mindestens 3 pro Kategorie (Passform, Material, Haltbarkeit, Preis, Kauf-Trigger)

**Tiefenregel Einwand-Cluster (2.4):**
- Einzelne Einwaende zu Clustern zusammenfassen
- "rutscht", "verrutscht", "haelt nicht" = Cluster "Passform/Halt"
- Pro Cluster: Gesamt-Haeufigkeit berechnen und Kritikalitaet bestimmen
- ≥15%: Hoch (MUSS in Listing adressiert werden)
- 8-15%: Mittel (SOLLTE adressiert werden)
- <8%: Niedrig (KANN adressiert werden)

After writing your sections: mark issue as done.

---

## 4. Analysis Process

### Step 4a: Own Product Reviews (if existing listing)
Analyze last 100-200 reviews: top 5 praise, top 5 criticism, surprise moments, expectation gaps, buyer personas.

### Step 4b: Competitor Reviews
For each top competitor: what customers love (our minimum), what they hate (our opportunity), what they wish existed (our differentiator).

### Step 4c: Q&A Analysis
Unanswered questions = listing content gaps. Map each to: slot, bullet, or A+ module.

### Step 4d: Language Extraction
Positive phrases, pain point descriptions, feature language — real customer vocabulary for the Content Master.

### Step 4e: Objection Map

| Objection | Frequency | Source | Addressable In |
|---|---|---|---|
| [Issue] | [x reviews] | [own/competitor] | [Slot/BP/A+ Module] |

## 5. Self-Check

- [ ] Top 5 praise + criticism with frequency and quotes
- [ ] ≥3 competitor review analyses
- [ ] Q&A gaps identified and mapped
- [ ] Customer vocabulary bank (≥10 phrases)
- [ ] Objection map with placement recommendations
- [ ] Buyer personas segmented

## 6. Write Output

Write `review-insights.md` to `./workspace/{task-id}/`.

## 7. Complete Task

```
PATCH /api/issues/{issueId}
{
  "status": "done",
  "comment": "@ceo Review-Analyse abgeschlossen. [X] Praise, [X] Kritik, [X] Einwaende identifiziert. Vokabular-Bank mit [X] Phrasen. Output: review-insights.md im Workspace."
}
```
