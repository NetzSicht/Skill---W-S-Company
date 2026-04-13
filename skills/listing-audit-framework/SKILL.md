---
name: listing-audit-framework
description: "Audit-Methodik fuer bestehende Amazon-Listings. 10 Pruefdimensionen mit Bewertungsrubriken, Status-Tags (KEEP/ENHANCE/REBUILD/MISSING) und Beweisanforderungen. Genutzt vom Listing-Auditor."
---

# Listing Audit Framework

10 Dimensionen. Jede mit eigener Rubrik. Jeder Befund braucht Evidenz.

---

## Die 4 Status-Tags

Jedes auditierte Element bekommt genau einen Status:

| Status | Bedeutung | Downstream-Impact |
|---|---|---|
| **KEEP** | Element funktioniert gut, nicht anfassen | Agents muessen es im neuen Briefing/Text identisch uebernehmen |
| **ENHANCE** | Element ist brauchbar aber verbesserbar | Agents nehmen es als Basis, arbeiten dran weiter |
| **REBUILD** | Element ist grundlegend kaputt | Agents machen komplett neu |
| **MISSING** | Element fehlt komplett | Agents muessen es neu erstellen |

---

## Dimension 1: Performance-Metriken

**Was pruefen:**
- BSR (Best Seller Rank) in Hauptkategorie und Unterkategorie
- Anzahl Reviews + durchschnittliche Sterne
- Preis vs. Kategorie-Median
- Anzahl Fragen in Q&A-Sektion
- Prime/FBA-Status

**Evidenz-Anforderung:** Exakte Zahlen aus Rainforest API `product` endpoint.

**Ableitungen:**
- BSR < 5000 in Hauptkategorie = erfolgreiches Listing (kleine Optimierungen)
- BSR > 50.000 = strukturelle Probleme (groeßere Ueberarbeitung noetig)
- <4.0 Sterne bei >100 Reviews = systematisches Qualitaetsproblem
- Review-Wachstum letzte 30 Tage = Engagement-Indikator

---

## Dimension 2: Hero Image (Slot 1)

**Compliance-Check (Pass/Fail):**
- [ ] Reiner weisser Hintergrund (RGB 255,255,255)?
- [ ] Keine Texte, Logos, Badges, Wasserzeichen?
- [ ] Keine Requisiten ausserhalb Lieferumfang?
- [ ] Mindestens 1600px Aufloesung?
- [ ] Produkt fuellt 85-100% des Rahmens?

**Qualitaets-Check:**
- [ ] Klarheit: Erkennt man in <1 Sekunde was das Produkt ist?
- [ ] Mobile Thumbnail-Test (150x150px): Noch erkennbar?
- [ ] Bei Multipacks: Sind alle Einheiten sichtbar?
- [ ] Hoehe/Form bei Kleidung erkennbar?
- [ ] Lichtsetzung professionell?

**Kategorie-Fit (aus kategorie-Skill):**
- [ ] Erfuellt die kategorie-spezifischen Anforderungen?
- Beispiel Socken: Paar oder Pack sichtbar? Hoehe erkennbar?
- Beispiel Bekleidung: Stehend am Model (Pflicht)?

**Status-Entscheidung:**
| Bedingung | Status |
|---|---|
| Compliance FAIL | REBUILD (Pflicht, sonst Search Suppression) |
| Compliance PASS + Qualitaet gut + Kategorie-fit | KEEP |
| Compliance PASS + kleine Qualitaetsmaengel | ENHANCE |
| Compliance PASS + schwerwiegende Qualitaetsmaengel oder Kategorie-fehlt | REBUILD |

**Evidenz:** Screenshot des aktuellen Hero. Vergleich zu Top-3 Kategorie-Performern.

---

## Dimension 3: Sekundaer-Bilder (Slot 2-7)

**Pro Slot auditieren:**

Fuer jeden genutzten Slot:
1. **Bildtyp bestimmen:** Lifestyle / Infografik / Dimension / Material / Packshot / Vergleich / Trust
2. **Kategorie-Fit pruefen:** Passt dieser Bildtyp an diese Position fuer diese Kategorie?
3. **Qualitaet bewerten:** Scharf, professionell, Mobile-lesbar?
4. **Text-Overlays pruefen:** 30pt+? Kontrast? Keine Compliance-Verstoesse?

**Fehlende Slots identifizieren:**
- Wie viele der 7 Slots werden genutzt?
- Welche typische Funktion fehlt? (Groessentabelle? Vergleich? Material-Nahaufnahme?)

**Status pro Slot:**
| Bedingung | Status |
|---|---|
| Slot leer | MISSING |
| Slot genutzt, aber falscher Typ fuer Kategorie | REBUILD |
| Slot genutzt, richtiger Typ, schlechte Ausfuehrung | REBUILD oder ENHANCE |
| Slot genutzt, richtiger Typ, ok Ausfuehrung | ENHANCE |
| Slot genutzt, richtiger Typ, sehr gute Ausfuehrung | KEEP |

**Gesamtbewertung:** Wie viele Slots sind KEEP? (Wenn <3 von 7: strukturelles Problem)

**Evidenz:** Slot-fuer-Slot Tabelle mit Ist-Zustand und Diagnose.

---

## Dimension 4: Titel

**Struktur-Check:**
- [ ] Marke am Anfang?
- [ ] Primaeres Keyword in ersten 70 Zeichen (Mobile-Anzeige)?
- [ ] Zielgruppe erkennbar (Herren/Damen/Kinder)?
- [ ] Groessenangabe vorhanden wenn relevant?
- [ ] Packungsgroesse bei Multipacks?
- [ ] Zeichenzahl 150-180?

**Keyword-Check:**
- Welche Keywords sind im Titel?
- Welche Top-Kategorie-Keywords fehlen? (Vergleich zum Kategorie-Skill)
- Keyword-Stuffing (Rufus/COSMO Risiko)?

**Compliance-Check:**
- [ ] Keine verbotenen Claims ("best", "#1", "bestseller", subjektive Superlative)?
- [ ] Keine Preise?
- [ ] Keine Aktions-Aufrufe?

**Status:**
| Bedingung | Status |
|---|---|
| Compliance-Verstoss | REBUILD (Pflicht) |
| Primaeres Keyword fehlt | REBUILD |
| Primaeres Keyword da, aber nicht in ersten 70 Zeichen | ENHANCE |
| Formel passt, aber bessere Kategorie-Keywords moeglich | ENHANCE |
| Titel erfuellt alle Checks | KEEP |

**Evidenz:** Aktueller Titel + Vergleich zu 3 Top-Listings der Kategorie + Keyword-Luecken-Liste.

---

## Dimension 5: Bullet Points

**Pro Bullet auditieren (BP1-BP5):**

1. **Hierarchie-Check:**
   - BP1: Primary USP / transformativer Benefit?
   - BP2: Technische Ueberlegenheit / Material?
   - BP3: Sekundaer-Benefit?
   - BP4: Einwand-Behandlung?
   - BP5: Lieferumfang / Garantie / Risk Reversal?

2. **Benefit vs. Feature:**
   - Wird der Nutzen kommuniziert oder nur das Feature?
   - Feature → Funktion → Outcome → Emotion Kette erkennbar?

3. **Kundensprache:**
   - Werden Formulierungen aus Reviews genutzt?
   - Oder klingt es wie Marketing-Sprech?

4. **Einwand-Behandlung:**
   - Werden die Top-Kritikpunkte aus Reviews proaktiv adressiert?

5. **Mobile-Lesbarkeit:**
   - Max. 200 Zeichen pro Bullet?
   - CAPS-Anker am Anfang?

**Status pro Bullet:**
| Bedingung | Status |
|---|---|
| Bullet fehlt | MISSING |
| Feature statt Benefit | REBUILD |
| Schwache Hierarchie (z.B. BP1 behandelt Nebensaechliches) | REBUILD |
| Hierarchie ok, aber bessere Kundensprache moeglich | ENHANCE |
| Bullet erfuellt alle Checks | KEEP |

**Evidenz:** Aktuelle Bullets + Top-3 Einwaende aus Reviews + wie sie (nicht) adressiert werden.

---

## Dimension 6: Backend Keywords

**Was pruefen (soweit ueber API/UI zugaenglich):**
- Werden die 250 Bytes vollstaendig genutzt?
- Duplikate zum Titel/Bullets (Verschwendung)?
- Fehlende Synonyme und Schreibfehler?
- PAN-EU: Sind fremdsprachige Keywords drin?

**Status:**
| Bedingung | Status |
|---|---|
| Unzugaenglich via API | Flag fuer Kunden-Anfrage |
| <200 Bytes genutzt | ENHANCE |
| Duplikate zum Titel | REBUILD |
| PAN-EU aber nur DE Keywords | REBUILD |

---

## Dimension 7: A+ Content

**Pruefung:**
- [ ] A+ Content vorhanden?
- [ ] Basic oder Premium?
- [ ] Wie viele Module?
- [ ] Duplikate zur Galerie-Bildern?
- [ ] Narrativ-Konsistenz zur Galerie?
- [ ] Vergleichstabelle vorhanden?
- [ ] FAQ-Modul vorhanden?

**Status:**
| Bedingung | Status |
|---|---|
| Kein A+ obwohl Brand Registry | MISSING (hoher Impact) |
| A+ vorhanden, dupliziert Galerie | REBUILD |
| A+ vorhanden, ergaenzt Galerie, aber Module fehlen | ENHANCE |
| A+ vollstaendig und komplementaer | KEEP |

---

## Dimension 8: Brand Story

**Pruefung:**
- [ ] Brand Story Modul vorhanden?
- [ ] Cross-Selling-Karussell genutzt?
- [ ] Markengeschichte erzaehlt?

**Status:**
- Fehlt bei Brand Registry = MISSING (Prerequisite fuer Premium A+)
- Vorhanden aber generisch = ENHANCE
- Vorhanden mit echter Story = KEEP

---

## Dimension 9: Review-Management — Nicht adressierte Kritikpunkte

**Der wichtigste Befund:**
- Welche Kritikpunkte tauchen in Reviews wiederholt auf?
- Werden diese Kritikpunkte im Listing (Titel/Bullets/Bilder/A+) proaktiv adressiert?
- Wenn NEIN: Das ist ein grosser Hebel.

**Beispiel:**
- 15% der Reviews beschweren sich ueber "Naht drueckt an den Zehen"
- Listing erwaehnt nichts zu Naehten
- → BP4 MISSING: "Nahtfrei / Flachnaht" als Einwand-Behandlung

**Status:** Pro nicht-adressierter Kritikpunkt ein MISSING-Befund mit Platzierungsempfehlung.

---

## Dimension 10: Kategorie-Benchmark

**Vergleich zum Kategorie-Standard:**

Aus dem Kategorie-Skill (z.B. `kategorie-textil-socken`) holen:
- Typische Slot-Sequenz der Top-Performer
- Typische Titel-Formel
- Typische A+ Module
- Typische Keywords

**Lueckenanalyse:**
- Wo steht dieses Listing im Vergleich?
- Welche Top-15-Patterns fehlen?
- Welche Differenzierungschancen gibt es?

**Status:** Meta-Dimension. Fuehrt Gesamtbewertung zusammen.

---

## Bewertungs-Rubrik Gesamt

Nach allen 10 Dimensionen:

| Ergebnis | Empfehlung |
|---|---|
| >70% KEEP, wenige ENHANCE, 0-1 REBUILD | **Minor Optimization** (Quick Wins reichen) |
| 40-70% KEEP, mehrere ENHANCE, 2-3 REBUILD | **Standard Optimization** (volle Pipeline mit Fokus) |
| <40% KEEP, viele REBUILD, mehrere MISSING | **Full Relaunch** (wie neues Listing behandeln) |
| Compliance-FAIL in Dim 2 oder Dim 4 | **Immediate Fix** (Pflicht vor allem anderen) |
