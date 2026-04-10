---
name: produkt-analyse-interface
description: "Exaktes Output-Schema fuer die Produkt-Analyse (Interface A). Definiert alle 10 Sektionen die der Produkt-Analyst liefern muss."
---

# Interface A: Produkt-Analyse Output-Schema

Dein Output muss exakt diesem Format folgen. Der Listing-Briefer erwartet genau diese Struktur.

Dateiname: `produkt-analyse.md`

---

## Das Schema

```markdown
# Produkt-Analyse: [Produktname]

## Meta
- **Erstellt:** [Datum]
- **ASIN:** [ASIN oder "Neues Listing"]
- **Marktplatz:** [amazon.de / amazon.com / etc.]
- **Analyst:** [Agent-Name oder Bearbeiter]

---

## 1. Produkt-Stammdaten

| Feld | Wert |
|---|---|
| Produktname | [Vollstaendiger Name] |
| Marke | [Markenname] |
| Kategorie | [Amazon-Hauptkategorie] |
| Unterkategorie | [Falls relevant] |
| Preis | [Aktueller Preis in EUR/USD] |
| Preisniveau | [Budget / Mittel / Premium] |
| FBA/FBM | [Fulfillment-Methode] |
| Brand Registry | [Ja / Nein] |
| A+ Content | [Verfuegbar / Nicht verfuegbar / Bereits vorhanden] |

## 2. Zielgruppe

| Feld | Wert |
|---|---|
| Primaere Persona | [z.B. "Gesundheitsbewusste Muetter, 30-45, urban"] |
| Sekundaere Persona | [Falls vorhanden] |
| Kaufmotivation | [Was treibt den Kauf?] |
| Schmerzpunkt | [Welches Problem loest das Produkt?] |
| Preissensibilitaet | [Hoch / Mittel / Niedrig] |

## 3. Top-USPs (priorisiert)

1. **[USP 1]** — [Kurze Erklaerung warum das ein USP ist]
2. **[USP 2]** — [Erklaerung]
3. **[USP 3]** — [Erklaerung]
4. **[USP 4]** — [Falls vorhanden]
5. **[USP 5]** — [Falls vorhanden]

## 4. Lieferumfang

| Teil | Anzahl | Hinweis |
|---|---|---|
| [Hauptprodukt] | 1 | [z.B. "Farbe: Schwarz"] |
| [Zubehoer 1] | [x] | |
| [Anleitung] | 1 | [Sprachen] |

## 5. Abmessungen & Physisches

| Feld | Wert |
|---|---|
| Hoehe | [cm] |
| Breite | [cm] |
| Tiefe | [cm] |
| Gewicht | [g/kg] |
| Fassungsvermoegen | [Falls relevant] |
| Material | [Hauptmaterial] |
| Farbe | [Verfuegbare Farben] |
| Varianten | [Groessen/Farben/Modelle] |

## 6. Zertifizierungen & Trust-Signale

- [ ] [Zertifikat 1]
- [ ] [Zertifikat 2]
- [ ] [Garantie]

## 7. Wettbewerber-Analyse

### Wettbewerber 1: [Name / ASIN]
| Aspekt | Bewertung |
|---|---|
| Preis | [EUR] |
| Bewertung | [Sterne / Anzahl] |
| Staerken | [Was machen sie gut?] |
| Schwaechen | [Wo sind sie angreifbar?] |
| Bild-Qualitaet | [Schlecht / Mittel / Gut / Sehr gut] |
| Slot-Nutzung | [Wie viele Slots? Welche Strategie?] |

[Wiederholen fuer Wettbewerber 2-5]

### Wettbewerber-Zusammenfassung
| Differenzierungspotenzial | Beschreibung |
|---|---|
| Wo wir besser sind | [Konkret] |
| Wo wir gleich sind | [Konkret] |
| Wo wir aufholen muessen | [Konkret] |
| Visuelle Luecke | [Was zeigt KEIN Wettbewerber?] |

## 8. Kundenstimmen-Analyse

### Aus eigenen Bewertungen (falls vorhanden)
| Typ | Haeufigkeit | Beispiel-Zitat |
|---|---|---|
| Top-Lob | [x Nennungen] | "[Zitat]" |
| Top-Kritik | [x Nennungen] | "[Zitat]" |
| Haeufigste Frage | [x Nennungen] | "[Frage]" |

### Aus Wettbewerber-Bewertungen
| Typ | Haeufigkeit | Beispiel-Zitat |
|---|---|---|
| Wiederkehrendes Lob | [x] | "[Zitat]" |
| Wiederkehrende Kritik | [x] | "[Zitat]" — **Chance fuer uns** |

## 9. Bestehende Bilder (falls Optimierung)

| Slot | Aktueller Inhalt | Bewertung | Problem |
|---|---|---|---|
| 1 | [Beschreibung] | [Gut/Mittel/Schlecht] | [Was fehlt] |
| ... | ... | ... | ... |

## 10. Strategie-Empfehlung (Analyst)

**Empfohlener Strategie-Typ:** [Standard-Balanced / Feature-Lastig / Emotional / Kategorie-Spezifisch]

**Begruendung:** [2-3 Saetze]

**Primaere Einwaende die adressiert werden muessen:**
1. [Einwand 1]
2. [Einwand 2]
3. [Einwand 3]

**Besondere Hinweise fuer den Briefer:**
- [Hinweis 1]
- [Hinweis 2]
```

---

## Regeln

- Jedes Feld muss gefuellt sein oder explizit als `[NICHT VERFUEGBAR — Kunde muss liefern]` markiert
- USPs als Benefits formulieren, nicht als Features
- Wettbewerber-Analyse muss ausgewogen sein (Staerken UND Schwaechen)
- Keine Annahmen treffen — nur belegbare Fakten
