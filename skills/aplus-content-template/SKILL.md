---
name: aplus-content-template
description: "A+ Content Briefing-Template fuer NetzSicht Amazon Listings. Definiert die 4-Slice + 5-Karussell-Panel + Comparison Struktur. Jedes Element mit Briefing-Format fuer den Grafiker: Kernbotschaft, Desktop+Mobile-Komposition, Text-Overlays, Farbzuordnung aus CI. Genutzt vom A+ Content Designer."
---

# A+ Content Briefing Template (NetzSicht Standard)

---

## Die NetzSicht A+ Content Architektur

```
┌─────────────────────────────────────────┐
│ Brand Story (separat, nicht briefen)    │
├─────────────────────────────────────────┤
│ SLICE 1: Hero                            │
│ SLICE 2: Benefit-Roundel                 │
│ SLICE 3: Lifestyle + Top-Benefit         │
│ SLICE 4: Qualitaet + Trust               │
├─────────────────────────────────────────┤
│ Premium-Navigations-Karussell            │
│ 5 Panels mit Deep-Dives pro Benefit      │
├─────────────────────────────────────────┤
│ Comparison-Modul (Amazon-Formular)       │
└─────────────────────────────────────────┘
```

**Kern-Logik:**
- **4 Slices** = lineare Hauptgeschichte (AIDA-Funnel)
- **Karussell** = non-lineare Deep-Dives fuer Interessierte
- **Comparison** = Retention + Cross-Sell

---

## Amazon Modul-Spezifikationen

### Vollstaendiges Premium-Bild (jeweils pro Slice 1-4)

Pro Modul liefert Amazon drei Felder:
- **Ueberschrift** (Text-Feld — kurz, 80 chars max)
- **Bild** — Desktop min. 1464x600px, Mobile min. 600x450px
- **Fliesstext** (optional, Body-Text unter dem Bild)

**Wichtig:** Desktop- und Mobile-Bild sind **separate Uploads**. Der Designer muss beide Varianten liefern — oft neu arrangiert, nicht nur gecroppt.

### Premium-Navigations-Karussell

Ein einziges Modul mit 2-5 Panels (wir nutzen immer 5). Pro Panel:
- **Navigationstext** (klickbares Label, max ~30 chars)
- **Ueberschrift** (Detail-View)
- **Unterueberschrift** (optional)
- **Fliesstext** (Body mit Bullets)
- **Bild** — gleiche Anforderungen wie Premium-Bild

Die Panels haben zwei visuelle Layer:
1. **Thumbnail** (im geschlossenen Zustand, klein + farbig)
2. **Detail-Bild** (nach Klick, gross, informativ)

Der Designer muss beide Layer liefern — das Thumbnail ist nicht einfach ein Crop des Detail-Bilds.

---

## Das Briefing-Format

### TEIL A: Strategische Uebersicht

```markdown
# A+ Content Briefing: [Produktname]

## Meta
- **Produkt:** [Name]
- **ASIN:** [ASIN wenn vorhanden]
- **Marktplatz:** [amazon.de / PAN-EU]
- **Brand Registry:** Ja (Premium A+ verfuegbar)
- **CI-Farben:** [Liste der verfuegbaren Markenfarben]
- **Zielgruppe:** [aus Produkt-Analyse]
- **Hauptpersona:** [aus Produkt-Analyse]

## Narrativer Bogen

Die 4 Slices erzaehlen folgende Geschichte:

1. **HERO** — [Was ist das Produkt, was ist das Haupt-Versprechen]
2. **BENEFIT-OVERVIEW** — [5 Schluessel-Benefits im Ueberblick]
3. **LIFESTYLE** — [Emotionale Anwendungs-Szene]
4. **QUALITAET + TRUST** — [Beweis + Sicherheit]

Das Karussell vertieft anschliessend:
- Panel 1: [Benefit 1 - Thema]
- Panel 2: [Benefit 2 - Thema]
- Panel 3: [Benefit 3 - Thema]
- Panel 4: [Benefit 4 - Thema]
- Panel 5: [Benefit 5 - Thema]

## Painpoint-Mapping (aus review-insights.md)

| Painpoint | Adressiert in |
|---|---|
| [Search-Painpoint 1] | Slice [X] + Karussell Panel [Y] |
| [Search-Painpoint 2] | Slice [X] |
| [Search-Painpoint 3] | Karussell Panel [Y] |
```

---

### TEIL B: Die 4 Slices

#### Slice 1: HERO

```markdown
## SLICE 1: HERO

**Ueberschrift (Amazon-Feld):**
> [Exakter Text, max 80 chars — Haupt-Versprechen in 3-5 Woertern]

Beispiel: "Warm, rutschfest & unglaublich kuschelig"

**Kernbotschaft (2-Sekunden-Regel):**
[Was der Kaeufer in 2 Sekunden verstehen soll]

**Adressierter Painpoint:**
[Welches Problem spricht die Slice an]

**Psychologische Funktion:**
Attention — sofortige USP-Erkennung. Der Kaeufer soll erkennen: "Das ist was ich gesucht habe."

---

### Desktop-Komposition (1464x600+)

**Hintergrund:** [z.B. "Produktbild im Kontext, nicht Studio-Weiss. Beispiel: Socken auf Teppich, Fuesse angedeutet"]

**Hauptelement:**
[Produkt + Positionierung im Bild — links/mittig/rechts?]

**Badges / Callouts:** 3-4 Stueck, ueber das Bild verteilt

| Position | Badge-Text | Farbe (aus CI) | Funktion |
|---|---|---|---|
| Links oben | [z.B. "Weicher Tragekomfort"] | [Hex aus CI] | Komfort-USP |
| Rechts oben | [z.B. "Hervorragende Passform"] | [Hex aus CI] | Haupt-USP |
| Rechts unten | [z.B. "Rutschfeste ABS-Sohle"] | [Hex aus CI] | Funktions-USP |
| Rund, dezent | [z.B. "Handmade in EU"] | [neutral] | Trust |

**Zentraler Text:** [z.B. "RUTSCHFEST, KUSCHELIG, WARM" — gross, weiss, klar]

**Text-Spezifikationen:**
- Hauptschrift: [Schriftart, Groesse >60pt]
- Badge-Schrift: [Schriftart, Groesse >30pt]
- Kontrast: [hoch, lesbar auf Hintergrund]

### Mobile-Komposition (600x450+)

**Unterschied zum Desktop:**
[Was muss neu arrangiert werden, damit es auf Mobile funktioniert — oft: weniger Badges, groessere Textgroesse, Hauptmotiv staerker zentriert]

**Anpassungen:**
- Max. 2-3 Badges (statt 4)
- Hauptmotiv nimmt mehr Flaeche ein
- Zentraler Text evtl. auf 2 Zeilen

**Fliesstext (optional):**
[Kurzer Body-Text unter dem Bild, 2-3 Saetze, unterstreicht die Hauptbotschaft — oft kann dies leer bleiben weil das Bild schon alles sagt]
```

---

#### Slice 2: BENEFIT-ROUNDEL

```markdown
## SLICE 2: BENEFIT-OVERVIEW (Roundel)

**Ueberschrift (Amazon-Feld):**
> [z.B. "5 Gruende die ueberzeugen" oder "Das macht sie besonders"]

**Kernbotschaft:**
Schneller Ueberblick ueber die 5 wichtigsten Benefits. Scanner-Mode — Kaeufer soll in 3 Sekunden alle Vorteile erfasst haben.

**Psychologische Funktion:**
Interest — kognitive Entlastung. Keine Textwaende, nur Icons + kurze Labels.

---

### Desktop-Komposition (1464x600+)

**Hintergrund:** [Material-Nahaufnahme oder farblich ruhiger Hintergrund, der die Icons nicht erdrueckt]

**Layout:** 5 runde Icons nebeneinander (oder 3+2 auf Mobile)

**Pro Icon:**
| # | Icon-Motiv | Label (max 3 Woerter) | Painpoint den es loest |
|---|---|---|---|
| 1 | [z.B. Blatt/Feder] | [z.B. "Kuscheliges Innenfutter"] | [Pain: kalte Fuesse] |
| 2 | [z.B. Wolke] | [z.B. "Weicher Materialmix"] | [Pain: kratziges Gefuehl] |
| 3 | [z.B. Tropfen durchgestrichen] | [z.B. "Keine Schweissfuesse"] | [Pain: schwitzige Fuesse] |
| 4 | [z.B. Kreise] | [z.B. "Kein Kratzen"] | [Pain: Juckreiz] |
| 5 | [z.B. Thermometer] | [z.B. "Besonders Gut Waermend"] | [Pain: frieren] |

**Icon-Stil:** Line-Icons, einheitliche Strichstaerke, innerhalb weisser Kreise, alle gleich gross

**Optional: Trust-Element im Hintergrund:**
[z.B. "Herstellung in der EU" Badge oben rechts — dezent, nicht dominant]

### Mobile-Komposition (600x450+)

**Layout-Anpassung:** Icons koennen 3+2 arrangiert werden (3 oben, 2 unten), oder alle 5 in einer Reihe kleiner

**Label-Anpassung:** Ggf. auf 2 Woerter verkuerzen damit sie lesbar bleiben

**Fliesstext:** [Optional — kann leer bleiben da das Bild selbsterklaerend ist]
```

---

#### Slice 3: LIFESTYLE + TOP-BENEFIT

```markdown
## SLICE 3: LIFESTYLE — Emotionale Anwendungsszene

**Ueberschrift (Amazon-Feld):**
> [z.B. "So entspannt war ein Feierabend noch nie" oder "Dein Moment der Gemuetlichkeit"]

**Kernbotschaft:**
Der Kaeufer sieht sich selbst in der Anwendungsszene. Spiegelneuronen aktivieren.

**Adressierter Painpoint:**
[Die Lebens-Situation die dem Pain gegenuebersteht — nicht "kalte Fuesse" sondern "der gemuetliche Abend der sonst durch kalte Fuesse ruiniert wird"]

**Psychologische Funktion:**
Desire — emotionale Projektion. Der Kaeufer kauft das Gefuehl, nicht das Produkt.

---

### Desktop-Komposition (1464x600+)

**Szenen-Setup:**
- **Setting:** [z.B. "Wohnzimmer, Sofa, warmer Herbstabend"]
- **Model:** [z.B. "Frau Mitte 30 mit Tasse Tee, Fuesse hochgelegt, lacht leicht"]
- **Produkt:** [wie integriert — Fuesse mit Socken klar sichtbar, nicht abgeschnitten]
- **Licht:** [warmes Licht, weich, nicht hart]
- **Farbwelt:** [natuerliche warme Toene, passend zu CI]

**Text-Element:**
[z.B. ein subtiler Top-Benefit-Banner links unten, nicht zu dominant — die Szene traegt die Emotion]

**Gaze Cueing:**
Blick des Models auf das Produkt oder auf den "Moment" (Tasse, Buch) — nicht in die Kamera.

### Mobile-Komposition (600x450+)

**Unterschied:**
- Szene enger crop — Fokus auf Fuesse + ein Kontext-Element (z.B. Tasse)
- Weniger weiter Raum
- Text-Element prominenter weil Bild kleiner

**Fliesstext:**
[2-3 Saetze die die emotionale Szene in Worte fassen. Hier darf es poetisch werden — aber immer mit konkretem Bezug zum Produkt-Benefit]

Beispiel: "Wenn der Tag lang war, die Fuesse muede und die Heizung auf Sparflamme — dann sind es die kleinen Dinge, die den Unterschied machen. Unsere Socken sind eines davon."
```

---

#### Slice 4: QUALITAET + TRUST

```markdown
## SLICE 4: QUALITAET + TRUST (der Closer)

**Ueberschrift (Amazon-Feld):**
> [z.B. "Material das haelt was es verspricht" oder "Qualitaet die du spuerst"]

**Kernbotschaft:**
Der Kaeufer sieht den Beweis fuer die Qualitaet + bekommt die Vertrauens-Elemente kurz vor der Kaufentscheidung.

**Adressierter Painpoint:**
"Ist das wirklich hochwertig oder nur schoen praesentiert?"

**Psychologische Funktion:**
Action-Vorbereitung — Sicherheit + Preis-Rechtfertigung. Letzter Baustein vor dem Kauf.

---

### Desktop-Komposition (1464x600+)

**Aufteilung:** Drei-Zonen-Layout

| Zone | Inhalt |
|---|---|
| **Links (40%)** | Material-Makro (Strickstruktur, Nahaufnahme) |
| **Mitte (40%)** | Qualitaets-Story: Text-Headline + 2-3 Bullet-Points zur Material-Herkunft |
| **Rechts (20%)** | Trust-Siegel-Leiste (vertikal oder quadratisch arrangiert) |

**Trust-Siegel:** Alle relevanten Zertifikate als Leiste:
- [z.B. Oeko-Tex 100]
- [z.B. Made in EU]
- [z.B. Fair Trade]
- [z.B. Vegan]

**Material-Headline:**
[z.B. "80% Merinowolle aus [Herkunft]. Handgekettelte Spitze. Zertifiziert schadstofffrei."]

### Mobile-Komposition (600x450+)

**Aufteilung:** Vertikales Stack statt Drei-Zonen
- Oben: Material-Makro
- Mitte: Headline + Bullets
- Unten: Trust-Siegel horizontal

**Fliesstext:**
[3-4 Saetze die die Qualitaets-Story ausfuehren. Fokus: Material-Herkunft, Produktion, Zertifikate. Warum der Preis gerechtfertigt ist.]
```

---

### TEIL C: Das Premium-Navigations-Karussell

```markdown
## KARUSSELL: 5 Deep-Dive Panels

**Gesamt-Konzept:**
Jedes Panel vertieft einen Benefit den die 4 Slices nur angerissen haben. Der Kaeufer waehlt selbst welche Panels ihn interessieren.

**Farbsystem (aus CI):**
Die 5 Panels brauchen visuell unterscheidbare Farben aus der CI des Kunden. Vorschlag pro Panel in der jeweiligen Sektion.

**Fallback wenn CI nur 2-3 Farben hat:**
- Primaerfarbe → wichtigster Benefit (Panel 1)
- Sekundaerfarbe → zweitwichtigster (Panel 2)
- Abgeleitete Toene (heller/dunkler) fuer Panel 3-5
- Oder: Grauabstufungen mit Akzentfarbe
```

#### Panel 1: [Haupt-Benefit]

```markdown
## KARUSSELL Panel 1: [z.B. "Hervorragende Passform"]

**Navigationstext** (Label im Thumbnail, max 30 chars):
> [z.B. "Durchdachter Materialmix"]

**Ueberschrift** (Detail-View):
> [z.B. "Hervorragende Passform"]

**Unterueberschrift** (optional):
> [z.B. "Anatomisch geformt, handgekettelt"]

**Fliesstext** (Body):
- [Bullet: z.B. "wohlige Passform"]
- [Bullet: z.B. "keine Druckstellen"]
- [Bullet: z.B. "optional weitere"]

---

### Farbzuordnung

**Panel-Farbe:** [Hex aus CI — z.B. Primaerfarbe weil wichtigster Benefit]
**Begruendung:** [z.B. "Primaer-Rot der Marke, weil Passform der Haupt-USP ist"]

---

### Thumbnail-Komposition (klickbare Kachel, klein)

**Hintergrund:** [Panel-Farbe als Vollflaeche]
**Produktausschnitt:** [kleiner Close-up, z.B. Socken-Ausschnitt]
**Text-Overlay:** [Navigationstext — gut lesbar, weisse Schrift auf Panel-Farbe]
**Icon (optional):** [kleines passendes Icon]

---

### Detail-Bild (nach Klick, gross)

**Desktop-Komposition (1464x600+):**

**Layout:** [z.B. Zweispaltig — links Headline+Bullets, rechts Produktbild]
**Hintergrund:** [Panel-Farbe oder Gradient]
**Hauptmotiv:** [Nahaufnahme oder Detail-Foto das den Benefit beweist]
**Text-Overlay:** 
- Headline: [exakter Text, Schriftgroesse, Farbe]
- Bullets: [mit Check-Icons, Schriftgroesse]

**Mobile-Komposition (600x450+):**

**Unterschied:** [z.B. Vertikal gestackt, Hauptmotiv oben, Text unten]
- Headline kleiner
- Max 2 Bullets sichtbar
- Hauptmotiv 60% der Flaeche

---

### Adressierter Painpoint
[Welches Problem loest dieser Benefit]

### Psychologische Funktion
[Welcher Trigger — Sicherheit, Komfort, Statuts, etc.]
```

**[Panel 2-5 nach gleichem Schema — jeweils anderer Benefit, andere CI-Farbe]**

---

### TEIL D: Comparison-Modul

```markdown
## Comparison-Modul (Amazon-Formular)

**WICHTIG:** Dies ist KEINE Designer-Komposition. Das Comparison-Modul ist ein Amazon-Formular. Der Designer muss nichts gestalten. Der A+ Content Designer liefert nur den Content.

### Inhalte

**Produkte zum Vergleich (5 ASINs der eigenen Marke):**
1. [Dieses Produkt]
2. [Variante 1, z.B. Sneakersocken]
3. [Variante 2, z.B. Wandersocken]
4. [Variante 3, z.B. Businesssocken]
5. [Variante 4, z.B. Thermosocken]

### Vergleichs-Zeilen (die Eigenschaften)

| Zeile | Werte pro ASIN |
|---|---|
| **Material** | [Wert 1] / [Wert 2] / [Wert 3] / [Wert 4] / [Wert 5] |
| **Hoehe** | |
| **Haupteinsatz** | |
| **Groessen** | |
| **Besonderheit** | |
| **Preis (geschaetzt)** | |

**Ziel:** Cross-Selling + Retention. Der Kaeufer findet im Vergleich entweder das passendere Produkt innerhalb unserer Marke (Upsell/Cross-Sell) oder bestaetigt seine Wahl (Retention).
```

---

## Master-Komposition (Orientierung fuer den Designer)

Der Designer braucht am Anfang eine Skizze wie die 4 Slices + das Karussell **zusammen** aussehen — so versteht er den Gesamt-Look und kann die Slices konsistent gestalten.

**Empfehlung:** Der A+ Content Designer erstellt eine einfache Master-Uebersicht (kann textuell oder als ASCII-Skizze sein) die zeigt:
- Welche Hauptfarben in welcher Slice dominieren
- Wie der Uebergang zwischen Slices aussieht (konsistent oder kontrastierend)
- Wo die Markenfarben auftauchen

Diese Master-Uebersicht ist Teil des Briefings.

---

## Qualitaets-Check vor Abgabe

- [ ] Alle 4 Slices haben eine einzigartige Aufgabe (keine Redundanz)
- [ ] Narrativer Bogen ist schluessig (AIDA erkennbar)
- [ ] Jede Slice hat Desktop UND Mobile-Komposition
- [ ] Alle Text-Overlays haben Mindestgroesse 30pt (Mobile)
- [ ] Karussell-Panels decken 5 verschiedene Benefits ab (keine Wiederholung)
- [ ] CI-Farben sind pro Panel zugeordnet mit Begruendung
- [ ] Trust-Elemente sind in Slice 4 konsolidiert (nicht verteilt)
- [ ] Lifestyle-Szene in Slice 3 ist emotional und konkret (nicht generisch)
- [ ] Keine Duplikate zwischen Slices und Galerie-Bildern
- [ ] Comparison-Modul hat 5 ASINs + mindestens 5 Vergleichs-Zeilen
