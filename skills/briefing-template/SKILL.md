---
name: briefing-template
description: "Exaktes Output-Format fuer Listing-Briefings. Header, 7 Slot-Bloecke (10 Felder pro Slot), Footer. Inkl. ausgefuelltem Beispiel (Heissluftfritteuse Slot 3)."
---

# Briefing-Output-Template

Dieses Template definiert das exakte Format, in dem der Skill Briefing-Dokumente fuer den Designer erstellt.

---

## Briefing-Header

```markdown
# Listing Bild-Briefing

**Produkt:** [Produktname]
**Marke:** [Markenname]
**ASIN:** [ASIN falls vorhanden]
**Kategorie:** [Amazon-Kategorie]
**Zielgruppe:** [Primaere Persona — Alter, Geschlecht, Lebenssituation]
**Preisniveau:** [Budget / Mittel / Premium — konkreter Preis]
**Slot-Strategie:** [Standard-Balanced / Feature-Lastig / Emotional / Kategorie-Spezifisch]
**Erstellt am:** [Datum]

---

## Strategische Zusammenfassung

**Narrativer Bogen (Slots 1-7):**
[2-3 Saetze die beschreiben, welche Geschichte die 7 Bilder zusammen erzaehlen.
Z.B.: "Der Kunde sieht das Produkt, erkennt sich in der Anwendungsszene wieder,
versteht die Top-Vorteile, sieht die Dimensionen, fuehlt die Qualitaet,
weiss genau was er bekommt und warum dieses Produkt besser ist als Alternativen."]

**Top-USPs (priorisiert):**
1. [USP 1 — wird in Slot X visualisiert]
2. [USP 2 — wird in Slot X visualisiert]
3. [USP 3 — wird in Slot X visualisiert]

**Haeufigste Kunden-Einwaende (aus Bewertungen/Wettbewerber-Analyse):**
1. [Einwand 1 — adressiert in Slot X]
2. [Einwand 2 — adressiert in Slot X]
3. [Einwand 3 — adressiert in Slot X]
```

---

## Slot-Briefing-Block (pro Slot wiederholen)

```markdown
---

## Slot [1-7]: [Bildtyp-Name]

### Kernbotschaft
> [Was soll der Betrachter in 2 Sekunden verstehen? Ein Satz.]

### Psychologische Funktion
[Welche Kaeufer-Frage wird beantwortet? Welches Neuromarketing-Prinzip greift?]

### Pflicht-Elemente
- [ ] [Element 1 — z.B. "Produkt vor weissem Hintergrund, frontal"]
- [ ] [Element 2 — z.B. "Alle Bundle-Teile sichtbar"]
- [ ] [Element 3]

### Optionale Elemente
- [ ] [Element — z.B. "Leichter Schatten fuer Dreidimensionalitaet"]
- [ ] [Element]

### Text-Overlay
**Vorhanden:** [Ja / Nein]
**Texte:** [Falls ja: Exakte Textvorschlaege]
**Schrift:** [Groesse, Typ, Farbe]
**Platzierung:** [Wo im Bild]

### Technische Vorgaben
- **Aufloesung:** [z.B. 2000x2000px]
- **Seitenverhaeltnis:** [z.B. 1:1]
- **Format:** [z.B. JPEG]
- **Besonderheiten:** [z.B. "Zoom-faehig, Thumbnail-Test bei 150x150px"]

### Farbwelt & Stimmung
[Kurze Beschreibung der gewuenschten Atmosphaere. Z.B.: "Hell, modern, aufgeraeumt.
Keine warmen Filter — clean und professionell. Farbakzente in Markenfarbe [Hex-Code]."]

### Designer-Notizen
[Spezifische Gestaltungshinweise die sich aus der Produkt-Analyse ergeben.
Z.B.: "Das Produkt hat eine matte Oberflaeche — darauf achten dass Lichtreflexe
die Textur nicht verdecken." oder "Model soll auf das Produkt blicken (Gaze Cueing)."]

### Referenz / Inspiration
[Beschreibung von Referenzbildern oder Wettbewerber-Beispielen.
Z.B.: "Aehnlich wie ASIN B08XXXX Slot 2 — Model in Kueche, aber mit
hellerem Setting und juengerer Zielgruppe."]

### A/B-Test-Vorschlag
[Welche Variante sollte getestet werden?
Z.B.: "Variante A: Frontal | Variante B: 20-Grad-Schraege"]
```

---

## Briefing-Footer

```markdown
---

## Review-Checkliste

- [ ] Alle 7 Slots haben eine einzigartige Aufgabe (keine Redundanz)
- [ ] Hero Image ist Amazon-compliant (weiss, keine Texte, 85-100% Fuellung)
- [ ] Alle Text-Overlays sind auf Mobile (6 Zoll) lesbar
- [ ] Top-USPs sind in mindestens je einem Slot visuell repraesentiert
- [ ] Haeufigste Kunden-Einwaende werden adressiert
- [ ] Narrativer Bogen ist schluessig (AIDA-Funnel)
- [ ] Kategorie-spezifische Amazon-Regeln sind eingehalten
- [ ] Keine Wettbewerber-Markennamen in Vergleichstabellen
- [ ] Keine Preise, Rabatte oder Kaufaufforderungen in Bildern
- [ ] Thumbnail-Test fuer Hero Image geplant

## A+ Content Empfehlung

**A+ Content noetig:** [Ja / Nein]
**Empfohlenes Format:** [Basic / Premium]
**Hinweis:** A+ Bilder muessen einzigartig sein — keine Duplikate aus der Galerie.
[Falls ja: Kurze Empfehlung welche A+ Module sinnvoll waeren]

## Naechste Schritte

1. Designer erstellt Bilder gemaess Briefing
2. Interne Review gegen Compliance-Checkliste
3. Mobile-Test auf verschiedenen Geraeten
4. Upload und A/B-Test Setup (Manage Your Experiments)
5. KPI-Tracking: CTR, CVR, Add-to-Cart-Rate, Return-Rate
```

---

## Beispiel: Ausgefuellter Slot-Block

```markdown
## Slot 3: Key Benefits Infografik

### Kernbotschaft
> "Diese Heissluftfritteuse hat 3 entscheidende Vorteile die sie von
> guenstigeren Alternativen unterscheiden."

### Psychologische Funktion
Rationale Rechtfertigung der emotionalen Kaufentscheidung. Der Kunde hat in
Slot 2 das Lifestyle-Bild gesehen und will jetzt Gruende. Ankereffekt:
Groesster Vorteil wird zuerst und am prominentesten gezeigt.

### Pflicht-Elemente
- [ ] Produkt zentral im Bild
- [ ] 3 Benefit-Callouts mit Icons:
      1. "Knusprig ohne Oel — 95% weniger Fett"
      2. "8L XXL Fassungsvermoegen — fuer die ganze Familie"
      3. "Dual-Zone — 2 Gerichte gleichzeitig"
- [ ] Jeder Benefit mit passendem Icon/Piktogramm

### Optionale Elemente
- [ ] Callout-Lines vom Produkt zu den Benefits
- [ ] Kleines "Nr. 1 Bestseller"-Hinweis (falls Amazon-konform)

### Text-Overlay
**Vorhanden:** Ja
**Texte:** Siehe Pflicht-Elemente oben
**Schrift:** 40pt, Montserrat Bold, Weiss auf dunkelgrauem Balken (#333333)
**Platzierung:** Benefits rechts vom Produkt, vertikal gestapelt

### Technische Vorgaben
- **Aufloesung:** 2000x2000px
- **Seitenverhaeltnis:** 1:1
- **Format:** PNG (fuer scharfe Texte)
- **Besonderheiten:** Text muss per OCR lesbar sein (Rufus-Indexierung)

### Farbwelt & Stimmung
Clean, modern. Hintergrund: Hellgrau (#F5F5F5). Akzente in Markenfarbe
Schwarz/Edelstahl-Optik. Icons in einheitlichem Stil (Line-Icons, 2px Strichstaerke).

### Designer-Notizen
Benefits als Outcomes formuliert, nicht als technische Specs. "Knusprig ohne Oel"
statt "Heissluft-Technologie". Der groesste Benefit (Dual-Zone) bekommt das
groesste Icon und die prominenteste Position (oben). Mobile-Check: Alle 3 Texte
muessen auf iPhone SE lesbar sein.

### Referenz / Inspiration
Aehnlich wie Philips Airfryer XXL Listing — klare Infografik mit 3 Benefits,
aber weniger ueberladen. Mehr Weissraum, moderneres Icon-Design.

### A/B-Test-Vorschlag
Variante A: 3 Benefits (wie oben)
Variante B: 5 Benefits (+ "Spuelmaschinenfest" + "30-Minuten-Timer")
Hypothese: Weniger Benefits = hoehere Conversion wegen kognitiver Entlastung
```
