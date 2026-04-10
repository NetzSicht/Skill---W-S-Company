---
name: review-interface
description: "Exaktes Output-Schema fuer das Review-Ergebnis (Interface C). Definiert Bewertungs-Dimensionen, Slot-Detail-Reviews und Aktions-Routing."
---

# Interface C: Review-Ergebnis Output-Schema

Dein Output muss exakt diesem Format folgen.

Dateiname: `review-ergebnis.md`

---

## Das Schema

```markdown
# Review-Ergebnis: [Produktname]

## Meta
- **Briefing geprueft:** [Dateiname]
- **Reviewer:** [Agent-Name]
- **Datum:** [Datum]
- **Gesamtergebnis:** [APPROVED / REVISION_NOETIG / ABGELEHNT]

---

## Zusammenfassung

[2-3 Saetze Gesamtbewertung. Was ist gut? Was muss sich aendern?]

## Bewertung pro Dimension

| Dimension | Status | Anmerkung |
|---|---|---|
| Amazon-Compliance | [PASS / FAIL] | [Detail] |
| Mobile-Lesbarkeit | [PASS / WARN / FAIL] | [Detail] |
| Narrativ-Konsistenz | [PASS / WARN / FAIL] | [Detail] |
| USP-Abdeckung | [PASS / WARN / FAIL] | [Detail] |
| Einwand-Behandlung | [PASS / WARN / FAIL] | [Detail] |
| Keine Redundanz | [PASS / WARN / FAIL] | [Detail] |
| Kategorie-Regeln | [PASS / FAIL] | [Detail] |

## Positives Feedback

[Was hat der Briefer gut gemacht? Mindestens 2-3 konkrete Punkte.]

## Slot-Detail-Review

[Nur fuer Slots mit WARN oder FAIL. Fuer PASS-Slots: nichts schreiben.]

### Slot [Nr]: [WARN / FAIL]

**Problem:** [Was stimmt nicht — konkret und spezifisch]
**Fix:** [Exakte Anweisung was geaendert werden muss]
**Prioritaet:** [Hoch / Mittel / Niedrig]
**Betroffene Dimension(en):** [z.B. "Compliance, Mobile-Lesbarkeit"]

[Wiederholen fuer jeden Slot mit Befund]

## USP-Mapping Check

| USP (aus Analyse) | Repraesentiert in Slot(s) | Status |
|---|---|---|
| [USP 1] | [Slot X] | [PASS / FAIL] |
| [USP 2] | [Slot X] | [PASS / FAIL] |

## Einwand-Mapping Check

| Einwand (aus Analyse) | Adressiert in Slot(s) | Wie | Status |
|---|---|---|---|
| [Einwand 1] | [Slot X] | [Beschreibung] | [PASS / FAIL] |

## Aktion

| Ergebnis | Naechster Schritt |
|---|---|
| APPROVED | Briefing geht an Designer |
| REVISION_NOETIG | Zurueck an Listing-Briefer mit obigen Fixes |
| ABGELEHNT | Zurueck an Produkt-Analyst — Grund: [was fehlt] |
```

---

## Bewertungslogik

| Bedingung | Ergebnis |
|---|---|
| Alle Dimensionen PASS | **APPROVED** |
| Mindestens ein WARN, kein FAIL | **REVISION_NOETIG** |
| Compliance FAIL oder 2+ andere FAILs | **REVISION_NOETIG** (schwer) |
| Daten aus Produkt-Analyse unzureichend | **ABGELEHNT** |

## Regeln

- Jeder FAIL braucht einen konkreten Fix
- Prioritaet angeben (Hoch / Mittel / Niedrig)
- Positives benennen — nicht nur Fehler auflisten
- Du schreibst das Briefing nicht um — du gibst Anweisungen
