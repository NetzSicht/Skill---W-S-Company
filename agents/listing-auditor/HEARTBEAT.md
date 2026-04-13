# Heartbeat — Listing-Auditor

Run this checklist every heartbeat.

## 1. Check for Work

```
GET /api/companies/{companyId}/issues?assigneeAgentId={myId}&status=todo,in_progress,blocked
```

If no issues: idle.

## 2. Checkout Task

```
POST /api/issues/{issueId}/checkout
```

Read the issue description. You should receive:
- ASIN of the existing listing
- Marktplatz (amazon.de / PAN-EU)
- Client context (why is this being optimized? What has the client observed?)

## 2b. Load Category Skill

Identify the category. If a kategorie-*-skill is attached (e.g., `kategorie-textil-socken`), read the agent section AND the category benchmark data. You will compare the current listing against this benchmark.

## 3. Pull Complete Listing Data

Use Rainforest API to pull EVERY available data point for the ASIN:

```
# Core product data
GET /request?api_key={KEY}&type=product&asin={ASIN}&amazon_domain=amazon.de

# All offers and pricing
GET /request?api_key={KEY}&type=offers&asin={ASIN}&amazon_domain=amazon.de

# All reviews — pull multiple pages
GET /request?api_key={KEY}&type=reviews&asin={ASIN}&amazon_domain=amazon.de&sort_by=most_recent&page=1
GET /request?api_key={KEY}&type=reviews&asin={ASIN}&amazon_domain=amazon.de&star_rating=critical&sort_by=most_helpful
GET /request?api_key={KEY}&type=reviews&asin={ASIN}&amazon_domain=amazon.de&star_rating=positive&sort_by=most_helpful

# Q&A
GET /request?api_key={KEY}&type=questions&asin={ASIN}&amazon_domain=amazon.de

# Related products (Also Bought)
GET /request?api_key={KEY}&type=also_bought&asin={ASIN}&amazon_domain=amazon.de
```

**Credit-Budget fuer ein Audit: ~10 Requests pro Listing**

## 3b. Visual Content Analysis (KI-Bilderkennung)

**Wichtig:** Du analysierst die Bilder nicht nur per Metadaten — du SCHAUST sie dir tatsaechlich an mit deinen Vision-Faehigkeiten.

Aus der Rainforest API Response bekommst du die kompletten Bild-URLs (`product.main_image.link`, `product.images[].link`). Fuer JEDES dieser Bilder:

1. **Bild oeffnen/herunterladen** (per URL, die API liefert direkte Links zu den Amazon-Bild-CDN)
2. **Inhalt visuell analysieren:**
   - Was ist tatsaechlich zu sehen? (Produkt, Hintergrund, Model, Text-Overlays, Icons)
   - Ist die Bildqualitaet hochwertig? (Schaerfe, Licht, Komposition)
   - Bei Slot 1: Compliance visuell pruefen (weisser Hintergrund? Keine Texte? Keine Props?)
   - Bei Slot 2-7: Bildtyp visuell bestimmen (Lifestyle, Infografik, Material-Close-up, etc.)
   - Text-Overlays lesen: Was steht drauf? Ist es lesbar? Kategorie-angemessen?
   - Kategorie-Fit: Passt das Bild zu den Erwartungen fuer diese Kategorie?

3. **Fuer A+ Content:** Wenn `product.a_plus_content` vorhanden ist, auch die A+ Module-Bilder visuell analysieren. Vergleiche sie mit der Galerie — gibt es Duplikate? Vertieft A+ die Story oder wiederholt sie?

4. **Befunde dokumentieren** mit konkreten visuellen Beobachtungen:
   - FALSCH: "Slot 2 ist schwach"
   - RICHTIG: "Slot 2 zeigt ein Flat-Lay mit 4 Socken auf weissem Hintergrund. Kein Tragebild, kein Kontext. Fuer die Kategorie Socken (wo Passform der Hauptkaufgrund ist) ein kritischer Fehler — Kategorie-Top-Performer zeigen hier ausnahmslos Tragebilder am Fuss."

**Regel:** Jede Aussage ueber ein Bild muss auf das basieren, was du visuell gesehen hast. Nicht raten, nicht aus der URL schliessen — tatsaechlich anschauen.

## 4. Execute the 10-Dimension Audit

Work through every dimension per skill `listing-audit-framework`. For each dimension:
- Measure current state
- Compare to category benchmark (from kategorie skill)
- Assign status tag (KEEP / ENHANCE / REBUILD / MISSING)
- Document evidence
- Write fix instruction for downstream agent

### The 10 Audit Dimensions

| # | Dimension | What to Check | Which Agent Handles Fix |
|---|---|---|---|
| 1 | **Performance-Metriken** | BSR, Reviews-Zahl, Sterne, Preis vs. Kategorie | — (Kontext) |
| 2 | **Hero Image (Slot 1)** | Compliance, Klarheit, Mobile-Thumbnail-Test, Packungsgroesse sichtbar | Listing-Briefer |
| 3 | **Sekundaer-Bilder (Slot 2-7)** | Slot-Nutzung, Bildtypen, Kategorie-Fit, Qualitaet | Listing-Briefer |
| 4 | **Titel** | Keyword-Nutzung, Formel-Qualitaet, Zeichenzahl, Mobile-First 70 chars | Content Master |
| 5 | **Bullet Points** | Hierarchie, Benefits vs. Features, Kunden-Vokabular, Einwand-Behandlung | Content Master |
| 6 | **Backend Keywords** | Abdeckung, Duplikate, Synonyme, PAN-EU | Content Master |
| 7 | **A+ Content** | Vorhanden? Basic/Premium? Moduele, Duplikate zur Galerie | A+ Content Designer |
| 8 | **Brand Story** | Vorhanden? Cross-Selling genutzt? | A+ Content Designer |
| 9 | **Review-Management** | Aktuelle Kritikpunkte die nicht adressiert werden | Produkt-Analyst + Listing-Briefer |
| 10 | **Kategorie-Benchmark** | Wo steht das Listing vs. Top 15 der Kategorie | — (Synthese) |

## 5. Identify Quick Wins vs. Deep Issues

Kategorisiere jeden Befund:

**QUICK WIN** (Prioritaet HOCH):
- <1 Stunde Aufwand
- Sofortiger CTR/CVR-Effekt erwartbar
- Kein Re-Shoot / Re-Design noetig
- Beispiele: Titel-Fix, fehlendes Keyword im Backend, einzelne Text-Overlay Korrektur

**ENHANCEMENT** (Prioritaet MITTEL):
- 1-4 Stunden Aufwand
- Bestehendes Element wird verbessert, nicht ersetzt
- Beispiele: Infografik-Ueberarbeitung, Bullet-Umformulierung

**REBUILD** (Prioritaet NIEDRIG/Projekt):
- >4 Stunden Aufwand
- Element muss komplett neu gemacht werden
- Beispiele: Slot 2 neues Shooting, komplett neues A+ Content

**MISSING** (Prioritaet je nach Impact):
- Element fehlt komplett
- Beispiele: Kein A+ obwohl Brand Registry vorhanden, keine Groessentabelle bei Textil

## 6. Write Adaption-Anweisungen fuer downstream Agents

Das ist der wichtigste Teil — klare Befehle an die naechsten Agents:

```markdown
## Adaption-Anweisungen

### Fuer Produkt-Analyst
- **FOKUS:** [Was muss er neu erforschen?]
- **SKIP:** [Was ist schon bekannt und muss nicht neu erhoben werden?]
- **PRUEFEN:** [Welche konkreten Annahmen des alten Listings muessen neu bewertet werden?]

### Fuer Listing-Briefer
- **Slot 1:** KEEP / ENHANCE / REBUILD — [Begruendung]
- **Slot 2:** ... 
- **Slot 3:** ...
- **Slot 4:** ...
- **Slot 5:** ...
- **Slot 6:** ...
- **Slot 7:** ...

### Fuer Content Master
- **Titel:** KEEP / ENHANCE / REBUILD — [Was behalten, was aendern]
- **BP1:** ...
- **BP2:** ...
- **BP3:** ...
- **BP4:** ...
- **BP5:** ...
- **Backend Keywords:** [Was fehlt]

### Fuer A+ Content Designer
- **Brand Story:** Vorhanden? Behalten/neu?
- **A+ Module:** [Welche behalten, welche neu]

### Prioritaet der Umsetzung
1. [Quick Win 1] — Impact: X — Aufwand: Y
2. [Quick Win 2] — ...
3. [Enhancement 1] — ...
4. [Rebuild 1] — ...
```

## 7. Self-Check

- [ ] Alle 10 Dimensionen analysiert
- [ ] Jeder Befund hat Evidenz (Metrik, Zitat, Vergleich)
- [ ] Jeder Befund hat Status-Tag (KEEP/ENHANCE/REBUILD/MISSING)
- [ ] Quick Wins klar getrennt von Deep Issues
- [ ] Adaption-Anweisungen pro downstream Agent vorhanden
- [ ] Keine generischen Aussagen ("qualitaet schlecht") — immer spezifisch
- [ ] Elemente die funktionieren sind explizit als KEEP markiert

## 8. Write Output

Write `listing-audit.md` to `./workspace/{task-id}/` per skill `listing-audit-interface`.

## 9. Complete Task

```
PATCH /api/issues/{issueId}
{
  "status": "done",
  "comment": "@ceo Audit abgeschlossen. Status: [X Quick Wins, Y Enhancements, Z Rebuilds, W Missing]. Kritischster Befund: [...]. Empfehlung: [Optimierung / Komplett-Relaunch]. Output: listing-audit.md im Workspace."
}
```

The CEO will then trigger the downstream pipeline (Produkt-Analyst → Briefer → ...) with your audit as input.
