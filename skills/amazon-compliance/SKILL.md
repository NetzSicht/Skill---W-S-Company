---
name: amazon-compliance
description: "Amazon Bild-Richtlinien und Compliance-Checkliste. Technische Specs, inhaltliche Regeln pro Slot, Mobile-Anforderungen, kategorie-spezifische Compliance und Upload-Review-Checkliste."
---

# Amazon Bild-Compliance Checkliste

Stand: 2026. Alle Regeln basierend auf offiziellen Amazon-Richtlinien und Best Practices.

---

## Hero Image (Slot 1) — Strikte Pflicht

Verstoesse fuehren zu automatischer Search Suppression (Produkt wird unsichtbar).

### Technisch

| Anforderung | Wert |
|---|---|
| Mindestaufloesung | 1000x1000px (Zoom ab hier aktiv) |
| Empfohlene Aufloesung | 1600-2000px (optimaler Zoom) |
| Maximale Aufloesung | 10000x10000px |
| Dateiformat | JPEG oder PNG |
| Farbraum | RGB (kein CMYK) |
| DPI | 72 dpi |
| Dateigroesse | Max. 10 MB |
| Hintergrund | 100% Weiss (RGB 255, 255, 255) |
| Produktfuellung | 85-100% des Bildrahmens |

### Inhaltlich

| Erlaubt | Verboten |
|---|---|
| Produkt allein, frontal | Texte jeglicher Art |
| Dezentes Produktetikett (falls am Produkt) | Logos (ausser auf Produkt selbst) |
| Leichter Schatten fuer Raeumlichkeit | Wasserzeichen |
| Alle Teile des Lieferumfangs | Badges ("Bestseller", "Neu") |
| | Requisiten die nicht im Lieferumfang sind |
| | Preise oder Aktionshinweise |
| | "Kaufen"-Aufrufe |
| | Mannequins (bei Bekleidung) |
| | Verpackung (ausser bei Geschenkartikeln) |

### Sonderfaelle

- **Bekleidung Erwachsene:** Muss an stehendem menschlichem Model gezeigt werden
- **Kinderbekleidung:** Muss flach (Flat-Lay) fotografiert werden
- **Schuhe:** Ein einzelner Schuh, 45-Grad-Winkel, nach links zeigend
- **Bundles/Sets:** Alle Teile muessen sichtbar sein

---

## Sekundaerbilder (Slot 2-7) — Flexiblere Regeln

### Technisch

Gleiche technische Anforderungen wie Hero Image bezueglich Aufloesung, Format und Dateigroesse.

### Inhaltlich Erlaubt

- Verschiedene Perspektiven und Winkel
- Lifestyle-/Anwendungsbilder mit Models und Requisiten
- Text-Overlays und Infografiken
- Icons, Piktogramme, Callout-Lines
- Vergleichstabellen (ohne Wettbewerber-Markennamen)
- Massangaben und Groessendarstellungen
- Zertifizierungs-Badges und Pruefsiegel
- Detail- und Makroaufnahmen

### Inhaltlich Verboten

- Preise oder Rabatthinweise
- "Kaufen"-/Werbe-Aufrufe
- Wasserzeichen
- Amazon-eigene Logos
- Falsche oder irrelevante Produktdarstellungen
- Sexuell suggestive Inhalte
- Clickbait-Texte
- Zeitlich begrenzte Angebote (z.B. "Nur heute!")

---

## Text-Overlay-Richtlinien (Slot 2-7)

| Parameter | Empfehlung | Begruendung |
|---|---|---|
| Schriftgroesse | Min. 30pt (relativ zu Bildgroesse) | Mobile-Lesbarkeit |
| Schriftart | Serifenlos (Sans-Serif) | Schnelle Erfassbarkeit |
| Kontrast | Hoch (weiss auf dunkel oder dunkel auf hell) | WCAG-konform, Mobile |
| Textmenge | Max. 5 Textbloecke pro Bild | Kognitive Entlastung |
| Sprache | An Zielmarkt anpassen (DE, EN, etc.) | Lokalisierung |
| Inhalt | Benefits, nicht Features | Verkaufspsychologie |
| Platzierung | Nicht in Randzonen (Mobile-Abschnittgefahr) | Responsiveness |

---

## Mobile-Spezifische Regeln

- Nur die **ersten 7 Bilder** werden auf Mobile angezeigt
- Mobile Sessions: durchschnittlich **2 Min 19 Sek**
- Jedes Bild muss seine Kernbotschaft in **unter 2 Sekunden** auf einem **6-Zoll-Screen** kommunizieren
- Hauptmotiv im **Bildzentrum** platzieren (Abschnittgefahr an Raendern)
- Schrift: Min. **10% der Bildhoehe** fuer Lesbarkeit
- Design-Quelldateien in **2x Aufloesung** fuer Retina-Displays erstellen
- A+ Content Bilder: Max. **500 KB** fuer schnelles Mobile-Loading
- Seitenverhaeltnis **1:1** (Standard) oder **1:1.5** (mehr vertikale Flaeche)

---

## Kategorie-Spezifische Compliance

### Bekleidung & Textil

- Erwachsene: Stehende menschliche Models (keine Mannequins, kein Sitzen)
- Kinder: Flat-Lay Fotografie
- Schuhe: Ein Schuh, 45 Grad, nach links
- Groessentabelle als ein Alternate Image empfohlen
- Model-Masse und getragene Groesse angeben

### Lebensmittel

- Naehrwerttabelle darf/muss als Bild hochgeladen werden
- EU-Etikettenpflichten beachten
- Energieetiketten (EEGL) bei bestimmten Produkten Pflicht

### Supplements / Nahrungsergaenzung

- Supplement Facts Panel Pflicht (Amazon Policy Maerz 2026)
- Alle Claims in Bildern muessen mit Panel uebereinstimmen
- "FDA Approved" strikt verboten
- Keine Krankheits-Behandlungs-Claims
- GMP, NSF, USDA Organic Badges erlaubt

### Elektronik

- Amazon erlaubt nun Bilder von mehreren Verkaufspartnern auf Hardline-Seiten
- -> Alle Carousel-Slots fuellen um fremde Bilder zu verhindern
- CE-Kennzeichnung zeigen falls zutreffend
- IP-Ratings bei relevanten Produkten

---

## Review-Checkliste (vor Upload)

Gehe diese Liste fuer jedes fertige Briefing durch:

- [ ] Hero Image: Reiner weisser Hintergrund, keine Texte/Logos/Extras
- [ ] Hero Image: Mind. 1600px, 85-100% Fuellung
- [ ] Alle 7 Slots genutzt
- [ ] Text-Overlays: Mind. 30pt, serifenlos, hoher Kontrast
- [ ] Keine Preise, Rabatte oder Kaufaufforderungen in Bildern
- [ ] Keine Wettbewerber-Markennamen in Vergleichstabellen
- [ ] Mobile-Test: Alle Bilder bei 6-Zoll-Screen pruefen
- [ ] Thumbnail-Test: Hero bei 150x150px pruefen
- [ ] Kategorie-spezifische Regeln beachtet
- [ ] Kein Bild dupliziert Inhalte eines anderen Slots
- [ ] A+ Content (falls vorhanden): Einzigartige Bilder, keine Galerie-Duplikate
- [ ] Alle Claims in Infografiken sind korrekt und belegbar
- [ ] RGB-Farbraum (kein CMYK)
- [ ] Dateigroesse unter 10 MB pro Bild
