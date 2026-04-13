---
name: listing-audit-interface
description: "Exaktes Output-Schema fuer Listing-Audits (Interface E). Definiert Performance-Snapshot, Element-by-Element Audit, Adaption-Anweisungen fuer downstream Agents. Genutzt vom Listing-Auditor."
---

# Interface E: Listing-Audit Output-Schema

Dateiname: `listing-audit.md`

---

## Das Schema

```markdown
# Listing-Audit: [Produktname]

## Meta
- **ASIN:** [ASIN]
- **Marktplatz:** [amazon.de / PAN-EU]
- **Audit-Datum:** [Datum]
- **Auditor:** Listing-Auditor
- **Gesamtempfehlung:** [Minor Optimization / Standard Optimization / Full Relaunch / Immediate Fix]

---

## 1. Performance-Snapshot

| Metrik | Aktueller Wert | Kategorie-Median | Bewertung |
|---|---|---|---|
| BSR (Hauptkategorie) | [Rang] | [Rang] | [Gut/Mittel/Schlecht] |
| BSR (Unterkategorie) | [Rang] | [Rang] | |
| Anzahl Reviews | [X] | [X] | |
| Durchschnittliche Sterne | [X.X] | [X.X] | |
| Preis | [EUR] | [EUR] | |
| FBA/FBM | [FBA/FBM] | - | |
| Brand Registry | [Ja/Nein] | - | |
| A+ Content | [Ja/Nein/Premium] | - | |

**Ableitungen:**
- [z.B. "Listing performt ueberdurchschnittlich fuer die Kategorie. Fokus: Feinoptimierung statt Grundueberholung."]
- [z.B. "Review-Trend der letzten 30 Tage: sinkend — moeglicherweise Qualitaetsproblem"]

---

## 2. Element-by-Element Audit

### Hero Image (Slot 1) — Status: [KEEP/ENHANCE/REBUILD/MISSING]

**Aktueller Zustand:**
[Beschreibung was im Bild zu sehen ist]

**Compliance-Check:**
- [ ] Weisser Hintergrund: [PASS/FAIL]
- [ ] Keine Texte/Logos: [PASS/FAIL]
- [ ] 85-100% Fuellung: [PASS/FAIL]
- [ ] Min. 1600px: [PASS/FAIL]

**Qualitaets-Befund:**
[Was funktioniert, was nicht, mit konkreten Belegen]

**Fix-Instruktion fuer Listing-Briefer:**
[Exakte Anweisung: KEEP / Was aendern / Komplett neu machen mit Vorgaben X]

---

### Sekundaer-Bilder (Slot 2-7)

| Slot | Typ aktuell | Status | Befund | Fix |
|---|---|---|---|---|
| 2 | [Lifestyle/Infografik/etc.] | [KEEP/ENHANCE/REBUILD/MISSING] | [Was ist Problem/Staerke] | [Konkrete Anweisung] |
| 3 | | | | |
| 4 | | | | |
| 5 | | | | |
| 6 | | | | |
| 7 | | | | |

**Slot-Gesamtbewertung:** [X von 7 Slots genutzt]. [Y von 7 sind KEEP]. 

---

### Titel — Status: [KEEP/ENHANCE/REBUILD]

**Aktueller Titel:**
> [Exakter Titel]

**Zeichenzahl:** [X / 200]
**Primaere Keywords in ersten 70 Zeichen:** [Ja/Nein]
**Compliance:** [PASS/FAIL]

**Befund:**
[Was funktioniert, was fehlt, mit Vergleich zu Kategorie-Top-3]

**Fix-Instruktion fuer Content Master:**
[z.B. "KEEP — aktueller Titel performt gut" oder "REBUILD: Neue Formel [Marke] + [Subtyp] + [Groesse] + [Feature]. Keywords die fehlen: X, Y, Z."]

---

### Bullet Points

| BP | Aktueller Inhalt (Kurzform) | Status | Befund | Fix |
|---|---|---|---|---|
| 1 | [Kurz] | [KEEP/ENHANCE/REBUILD/MISSING] | [Problem] | [Fix] |
| 2 | | | | |
| 3 | | | | |
| 4 | | | | |
| 5 | | | | |

---

### Backend Keywords — Status: [KEEP/ENHANCE/REBUILD/UNBEKANNT]

**Befund:** [Was sichtbar/messbar ist]
**Fix-Instruktion:** [z.B. "Backend unzugaenglich via API — beim Kunden anfragen. Fuer PAN-EU fehlen FR, IT, ES Keywords."]

---

### A+ Content — Status: [KEEP/ENHANCE/REBUILD/MISSING]

**Vorhanden:** [Ja/Nein/Premium]
**Module:** [Liste]
**Befund:** [Analyse]
**Fix-Instruktion fuer A+ Content Designer:** [Konkrete Anweisung]

---

### Brand Story — Status: [KEEP/ENHANCE/REBUILD/MISSING]

**Vorhanden:** [Ja/Nein]
**Befund:** [Analyse]
**Fix-Instruktion:** [Anweisung]

---

## 3. Review-Management: Nicht adressierte Kritikpunkte

| Kritikpunkt | Haeufigkeit | Beispiel-Zitat | Adressiert im Listing? | Wo adressieren |
|---|---|---|---|---|
| [z.B. "Naht drueckt"] | [X%] | "[exaktes Zitat]" | [Nein] | [BP4 / Slot 5] |
| | | | | |
| | | | | |

**Groesster Hebel:** [Welcher Kritikpunkt hat die hoechste Haeufigkeit und wird nicht adressiert?]

---

## 4. Kategorie-Benchmark-Vergleich

| Aspekt | Top-3 Kategorie-Listings | Dieses Listing | Luecke |
|---|---|---|---|
| Slots genutzt | [X/7] | [X/7] | [Ja/Nein] |
| Typische Titel-Formel | [Formel] | [Abweichung] | [Was fehlt] |
| A+ Module | [Anzahl] | [Anzahl] | [Was fehlt] |
| Groessentabelle | [Ja/Nein] | [Ja/Nein] | |
| Vergleichstabelle | [Ja/Nein] | [Ja/Nein] | |

---

## 5. Quick Wins (Prioritaet HOCH)

Sofort umsetzbar, grosser Effekt, <1 Stunde Aufwand pro Item:

| # | Befund | Fix | Erwarteter Impact | Verantwortlich |
|---|---|---|---|---|
| 1 | [Kurz] | [Konkrete Aktion] | [CTR/CVR-Effekt] | [Agent] |
| 2 | | | | |
| 3 | | | | |

---

## 6. Enhancements (Prioritaet MITTEL)

Verbesserung bestehender Elemente, 1-4 Stunden pro Item:

| # | Element | Aktuell | Verbesserung | Verantwortlich |
|---|---|---|---|---|
| 1 | | | | |
| 2 | | | | |

---

## 7. Rebuilds (Prioritaet NIEDRIG / Projekt)

Komplette Neuerstellung noetig, grosser Aufwand:

| # | Element | Warum Rebuild | Neu-Konzept | Verantwortlich |
|---|---|---|---|---|
| 1 | | | | |
| 2 | | | | |

---

## 8. Missing (fehlende Elemente)

| # | Was fehlt | Warum kritisch | Wer erstellt neu |
|---|---|---|---|
| 1 | | | |
| 2 | | | |

---

## 9. Adaption-Anweisungen fuer downstream Agents

### Fuer Produkt-Analyst

- **FOKUS:** [Was muss er neu erforschen?]
- **SKIP:** [Was ist aus dem Audit schon bekannt und muss nicht neu erhoben werden?]
- **PRUEFEN:** [Welche Annahmen des alten Listings muessen neu bewertet werden?]
- **KEEP-Daten:** [Welche Daten aus dem bestehenden Listing sind korrekt und koennen uebernommen werden?]

### Fuer Listing-Briefer

Slot-Status Uebersicht:
- **Slot 1 Hero:** [KEEP/ENHANCE/REBUILD] — [Einzeilige Begruendung]
- **Slot 2:** [Status] — [Begruendung]
- **Slot 3:** [Status] — [Begruendung]
- **Slot 4:** [Status] — [Begruendung]
- **Slot 5:** [Status] — [Begruendung]
- **Slot 6:** [Status] — [Begruendung]
- **Slot 7:** [Status] — [Begruendung]

**Wichtig:** Bei KEEP Slots: Im neuen Briefing explizit markieren "Uebernehmen wie aktuell auf ASIN [X]".

### Fuer Content Master

- **Titel:** [Status] — [Was behalten / was aendern]
- **BP1:** [Status] — [Anweisung]
- **BP2:** [Status] — [Anweisung]
- **BP3:** [Status] — [Anweisung]
- **BP4:** [Status] — [Anweisung]
- **BP5:** [Status] — [Anweisung]
- **Backend Keywords:** [Was fehlt, was PAN-EU Laender sind unterversorgt]

**Wichtig:** Bei KEEP Elementen: Original-Text im neuen `listing-texte.md` identisch uebernehmen.

### Fuer A+ Content Designer

- **Brand Story:** [Status] — [Anweisung]
- **A+ Module:** [Welche behalten, welche rebuilden, welche fehlen]
- **Galerie-Duplikate:** [Falls vorhanden: welche Duplikate muessen weg]

### Fuer Quality-Reviewer

- **Besonders achten auf:** [Welche Dimensionen sind die kritischsten in diesem Audit]
- **Compliance-Risiken:** [Spezifische Fehler im alten Listing die nicht wiederholt werden duerfen]

---

## 10. Empfehlung & Priorisierung

**Gesamt-Empfehlung:** [Minor / Standard / Full Relaunch / Immediate Fix]

**Geschaetzter Aufwand:** [X Stunden Design + Y Stunden Copy + Z Stunden Research]

**Erwarteter Impact:** [CTR +X%, CVR +Y%]

**Reihenfolge der Umsetzung:**
1. [Sofort: Immediate Fixes / Compliance]
2. [Diese Woche: Quick Wins]
3. [Dieses Monat: Enhancements]
4. [Naechstes Quartal: Rebuilds]
```
