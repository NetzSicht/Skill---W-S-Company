# Pipeline Interfaces

Dieses Dokument definiert die exakten Datenformate zwischen den Agents.
Jeder Agent liest und schreibt nach diesen Schemas — keine Abweichungen.

---

## Uebersicht

```
[Produkt-Analyst]          [Listing-Briefer]          [Quality-Reviewer]
      |                          |                          |
      | OUTPUT:                  | OUTPUT:                  | OUTPUT:
      | produkt-analyse.md      | listing-briefing.md      | review-ergebnis.md
      |                          |                          |
      +--- Interface A --------->+--- Interface B --------->+
```

---

## Interface A: Produkt-Analyse → Listing-Briefer

Dateiname: `produkt-analyse.md`

Der Produkt-Analyst liefert dieses Dokument. Der Listing-Briefer erwartet genau dieses Format.

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
| Kaufmotivation | [Was treibt den Kauf? z.B. "Geschenk", "Eigennutzung", "Ersatz"] |
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
| [Zubehoer 1] | [x] | [z.B. "Inklusive"] |
| [Zubehoer 2] | [x] | |
| [Anleitung] | 1 | [Sprachen] |

## 5. Abmessungen & Physisches

| Feld | Wert |
|---|---|
| Hoehe | [cm] |
| Breite | [cm] |
| Tiefe | [cm] |
| Gewicht | [g/kg] |
| Fassungsvermoegen | [Falls relevant, z.B. "8 Liter"] |
| Material | [Hauptmaterial] |
| Farbe | [Verfuegbare Farben] |
| Varianten | [Groessen/Farben/Modelle] |

## 6. Zertifizierungen & Trust-Signale

- [ ] [Zertifikat 1, z.B. "CE-zertifiziert"]
- [ ] [Zertifikat 2, z.B. "TUeV-geprueft"]
- [ ] [Award/Auszeichnung]
- [ ] [Garantie: z.B. "2 Jahre Herstellergarantie"]

## 7. Wettbewerber-Analyse

### Wettbewerber 1: [Name / ASIN]
| Aspekt | Bewertung |
|---|---|
| Preis | [EUR] |
| Bewertung | [Sterne / Anzahl] |
| Staerken | [Was machen sie gut?] |
| Schwaechen | [Wo sind sie angreifbar?] |
| Bild-Qualitaet | [Schlecht / Mittel / Gut / Sehr gut] |
| Slot-Nutzung | [Wie viele Slots genutzt? Welche Strategie?] |

### Wettbewerber 2: [Name / ASIN]
[Gleiche Struktur]

### Wettbewerber 3: [Name / ASIN]
[Gleiche Struktur]

### Wettbewerber-Zusammenfassung
| Differenzierungspotenzial | Beschreibung |
|---|---|
| Wo wir besser sind | [Konkret] |
| Wo wir gleich sind | [Konkret] |
| Wo wir aufholen muessen | [Konkret] |
| Visuelle Luecke | [Was zeigt KEIN Wettbewerber, das wir zeigen koennten?] |

## 8. Kundenstimmen-Analyse

### Aus eigenen Bewertungen (falls vorhanden)
| Typ | Haeufigkeit | Beispiel-Zitat |
|---|---|---|
| Top-Lob | [x Nennungen] | "[Zitat]" |
| Top-Lob | [x Nennungen] | "[Zitat]" |
| Top-Kritik | [x Nennungen] | "[Zitat]" |
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
| 1 | [Beschreibung] | [Gut/Mittel/Schlecht] | [Was fehlt/stoert] |
| 2 | [Beschreibung] | [...] | [...] |
| ... | ... | ... | ... |
| Nicht genutzt | Slots [X-7] leer | — | Verlorenes Potenzial |

## 10. Strategie-Empfehlung (Analyst)

**Empfohlener Strategie-Typ:** [Standard-Balanced / Feature-Lastig / Emotional / Kategorie-Spezifisch]

**Begruendung:** [2-3 Saetze warum diese Strategie fuer dieses Produkt am besten passt]

**Primaere Einwaende die adressiert werden muessen:**
1. [Einwand 1 — z.B. "Groesse unklar"]
2. [Einwand 2 — z.B. "Material wirkt billig auf Fotos"]
3. [Einwand 3 — z.B. "Preis hoeher als Wettbewerb"]

**Besondere Hinweise fuer den Briefer:**
- [z.B. "Produkt hat matte Oberflaeche — Lichtreflexe beachten"]
- [z.B. "Zielgruppe ist 60+ — groessere Schrift in Infografiken"]
```

---

## Interface B: Listing-Briefing → Quality-Reviewer

Dateiname: `listing-briefing.md`

Das Briefing wird im Format aus `agents/listing-briefer/references/briefing-template.md` erstellt. Der Quality-Reviewer erhaelt zusaetzlich die originale `produkt-analyse.md` als Kontext.

---

## Interface C: Quality-Review → Ergebnis

Dateiname: `review-ergebnis.md`

```markdown
# Review-Ergebnis: [Produktname]

## Meta
- **Briefing geprueft:** [Dateiname]
- **Reviewer:** [Agent-Name]
- **Datum:** [Datum]
- **Gesamtergebnis:** [APPROVED / REVISION_NOETIG / ABGELEHNT]

---

## Zusammenfassung

[2-3 Saetze Gesamtbewertung]

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

## Slot-Detail-Review

### Slot [Nr]: [Status-Emoji PASS/WARN/FAIL]

**Problem:** [Was stimmt nicht]
**Fix:** [Konkrete Anweisung was geaendert werden muss]
**Prioritaet:** [Hoch / Mittel / Niedrig]

[Wiederholen fuer jeden Slot mit Befund]

## Aktion

| Bei Ergebnis | Naechster Schritt |
|---|---|
| APPROVED | Briefing geht an Designer |
| REVISION_NOETIG | Zurueck an Listing-Briefer mit Fixes |
| ABGELEHNT | Zurueck an Produkt-Analyst (Daten unzureichend) |
```
