---
name: aplus-content-template
description: "A+ Content Briefing-Template fuer NetzSicht Amazon Listings. Definiert die 4-Slice + 5-Karussell-Panel + Comparison Struktur. Jedes Element mit kreativen Bild-Ideen (Painpoint-Metaphern), Desktop+Mobile-Komposition, Text-Overlays und psychologischer Funktion. Farbgebung bleibt dem Designer ueberlassen (CI-abhaengig pro Kunde). Genutzt vom A+ Content Designer."
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

## Rolle der Agents vs. Designer

| Was der A+ Content Designer (Agent) liefert | Was der Designer (Grafiker) macht |
|---|---|
| Strategie & Struktur (4 Slices + 5 Panels) | Visuelle Umsetzung |
| Kernbotschaften + Headlines + Fliesstext | Typografie & Layout |
| Painpoint pro Element | — |
| **Kreative Bild-Ideen** (Metaphern, Szenen, Kompositionen) | Finale Bildauswahl + Fotoshoot/KI-Generierung |
| Desktop/Mobile Komposition (Layout-Prinzipien) | Konkrete Pixel-Umsetzung |
| — | **Farben aus der Kunden-CI** |
| — | Schriftarten aus der Kunden-CI |
| — | Brand-spezifische Details |

**Wichtig:** Der Agent schlaegt KEINE Farben vor. Jeder NetzSicht-Kunde hat eine eigene CI, und der Designer waehlt passend dazu.

Aber: Der Agent schlaegt **kreative Bild-Ideen** vor — Metaphern, Szenen, visuelle Konzepte die den Painpoint illustrieren. Der Designer hat dann einen klaren kreativen Ausgangspunkt.

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
1. **Thumbnail** (im geschlossenen Zustand, klein)
2. **Detail-Bild** (nach Klick, gross, informativ)

Der Designer muss beide Layer liefern — das Thumbnail ist nicht einfach ein Crop des Detail-Bilds. **Wichtig fuer das Karussell:** Die 5 Panels muessen visuell klar unterscheidbar sein (Aufgabe des Designers via CI-Farben und Bildauswahl).

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
- **Zielgruppe:** [aus Produkt-Analyse]
- **Hauptpersona:** [aus Produkt-Analyse]
- **Marken-Ton:** [z.B. "Professionell-warm", "Sportlich-direkt"] (fuer den Designer als Orientierung)

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

**Kernbotschaft (2-Sekunden-Regel):**
[Was der Kaeufer in 2 Sekunden verstehen soll]

**Adressierter Painpoint:**
[Welches Problem spricht die Slice an]

**Psychologische Funktion:**
Attention — sofortige USP-Erkennung.

---

### Kreative Bild-Idee

**Visual Concept:**
[Die Haupt-Bildidee in 2-3 Saetzen beschrieben. Eine Metapher oder Szene die den Painpoint illustriert.]

**Bildstimmung:** [z.B. "Morgendlich-gold, draussen, echt — kein Studio-Look"]

**Mood Reference / Inspiration:** 
[z.B. "Outdoor-Fotografie im Stil von Patagonia-Marketing", oder "wie ein Filmstill aus Into the Wild"]

---

### Desktop-Komposition (1464x600+)

**Hintergrund:** [z.B. "Unscharfe Bergkulisse im goldenen Morgenlicht"]

**Hauptelement:** 
[Produkt + Positionierung — links/mittig/rechts, Perspektive, Groesse im Bild]

**Badges / Callouts:** 3-4 Stueck, ueber das Bild verteilt

| Position | Badge-Text | Bildidee im Badge | Funktion |
|---|---|---|---|
| Links oben | [z.B. "Weicher Tragekomfort"] | [z.B. "Feder-Icon"] | Komfort-USP |
| Rechts oben | [z.B. "Hervorragende Passform"] | [z.B. "Icon: perfekt eingepasster Fuss"] | Haupt-USP |
| Rechts unten | [z.B. "Rutschfeste ABS-Sohle"] | [z.B. "Icon: Rutsch-Symbol durchgestrichen"] | Funktions-USP |
| Rund, dezent | [z.B. "Handmade in EU"] | [z.B. "EU-Flagge-Blatt-Kombi"] | Trust |

**Farbzuordnung Badges:** [An den Designer — waehle 3-4 visuell unterscheidbare Farben aus der Kunden-CI. Jedes Badge in einer anderen Farbe damit die USPs individuell heraus stechen.]

**Zentraler Text:** [z.B. "RUTSCHFEST, KUSCHELIG, WARM" — gross, klar, mindestens 60pt]

### Mobile-Komposition (600x450+)

**Unterschied zum Desktop:**
- Max. 2-3 Badges (statt 4)
- Hauptmotiv nimmt mehr Flaeche ein
- Zentraler Text evtl. auf 2 Zeilen

**Fliesstext (optional):**
[Kurzer Body-Text unter dem Bild, 2-3 Saetze, oder leer]
```

---

#### Slice 2: BENEFIT-ROUNDEL

```markdown
## SLICE 2: BENEFIT-OVERVIEW (Roundel)

**Ueberschrift (Amazon-Feld):**
> [z.B. "5 Gruende die ueberzeugen"]

**Kernbotschaft:**
Schneller Ueberblick ueber die 5 wichtigsten Benefits — Scanner-Mode.

**Psychologische Funktion:**
Interest — kognitive Entlastung. Keine Textwaende, nur Icons + Labels.

---

### Kreative Bild-Idee

**Visual Concept:**
5 runde Icons nebeneinander, jedes illustriert einen Benefit durch eine klare visuelle Metapher. Der Hintergrund soll ruhig sein damit die Icons Hauptfokus bleiben.

**Hintergrund-Idee:** [z.B. "Natuerliche Textur wie Holzmaserung, Stein, oder unscharfer Material-Makro — passt zur Marke, erdrueckt aber nicht die Icons"]

---

### Desktop-Komposition (1464x600+)

**Layout:** 5 runde Icon-Kreise nebeneinander (oder 3+2 auf Mobile)

**Pro Icon:**
| # | Icon-Motiv (Bildidee) | Label (max 3 Woerter) | Painpoint den es loest |
|---|---|---|---|
| 1 | [z.B. "Blatt im Schild — symbolisiert Schutz"] | [z.B. "Kuscheliges Innenfutter"] | [Pain: kalte Fuesse] |
| 2 | [z.B. "Wolke mit Feder — Weichheit"] | [z.B. "Weicher Materialmix"] | [Pain: kratziges Gefuehl] |
| 3 | [z.B. "Tropfen durchgestrichen — keine Feuchtigkeit"] | [z.B. "Keine Schweissfuesse"] | [Pain: schwitzige Fuesse] |
| 4 | [z.B. "Federn-Kreis — null Reibung"] | [z.B. "Kein Kratzen"] | [Pain: Juckreiz] |
| 5 | [z.B. "Thermometer + Sonne — Waerme"] | [z.B. "Besonders Gut Waermend"] | [Pain: frieren] |

**Icon-Stil:** Line-Icons, einheitliche Strichstaerke, innerhalb Kreisen, alle gleich gross. 

**Farbe der Icons und Kreise:** [An den Designer — aus Kunden-CI]

**Optional: Trust-Element im Hintergrund:**
[z.B. "Herstellung in der EU" Badge oben rechts — dezent, nicht dominant]

### Mobile-Komposition (600x450+)

**Layout-Anpassung:** Icons 3+2 arrangiert (3 oben, 2 unten), oder 5 in einer Reihe kleiner.

**Fliesstext:** [Optional]
```

---

#### Slice 3: LIFESTYLE + TOP-BENEFIT

```markdown
## SLICE 3: LIFESTYLE — Emotionale Anwendungsszene

**Ueberschrift (Amazon-Feld):**
> [z.B. "So entspannt war ein Feierabend noch nie"]

**Kernbotschaft:**
Der Kaeufer sieht sich selbst in der Anwendungsszene. Spiegelneuronen aktivieren.

**Adressierter Painpoint:**
[Die Lebens-Situation die dem Pain gegenuebersteht]

**Psychologische Funktion:**
Desire — emotionale Projektion.

---

### Kreative Bild-Idee

**Visual Concept:**
Eine konkrete, authentische Nutzungs-Szene. Kein Stock-Foto-Look. Der Kaeufer soll denken: "Das koennte ich sein."

**Szenen-Vorschlag 1:** [z.B. "Gipfel-Moment: Wanderer sitzt auf Stein, Blick ins Tal, Wanderstiefel aus, Fuesse in Socken entspannt zur Seite gestreckt. Goldene Stunde, warmes Licht."]

**Szenen-Vorschlag 2 (Alternative):** [z.B. "Huette-Ankunft: Person betritt Berghuette nach langer Tour, Jacke ausziehend, ein kleiner Moment der Erleichterung. Socken als Detail sichtbar."]

**Szenen-Vorschlag 3 (Alternative):** [z.B. "Morgen auf der Terrasse: fruehes Fruehstueck vor Tour-Start, Karte auf dem Tisch, Socken angezogen, Stiefel daneben bereit."]

**Empfehlung:** [Welcher der Vorschlaege passt am besten zur Marken-Persona + dem staerksten Painpoint]

---

### Desktop-Komposition (1464x600+)

**Szenen-Setup:**
- **Setting:** [konkret, nicht generisch]
- **Model:** [Alter, Typ, Stimmung — passend zur Zielgruppe]
- **Pose:** [Was macht der Mensch, wo schaut er hin]
- **Produkt-Integration:** [Wie ist das Produkt im Bild — nicht versteckt, aber auch nicht auf Stock-Photo-Art]
- **Licht:** [z.B. warmes Morgenlicht, weich, nicht hart]

**Text-Element:** [Wenn vorhanden: subtiler Banner, nicht dominant]

**Gaze Cueing:** Blick des Models auf das Produkt oder auf den "Moment" (Tasse, Tal, etc.) — nicht in die Kamera.

### Mobile-Komposition (600x450+)

**Unterschied:**
- Szene enger Crop — Fokus auf Hauptperson + 1 Kontext-Element
- Text-Element prominenter weil Bild kleiner

**Fliesstext:**
[2-3 Saetze die die emotionale Szene in Worte fassen. Hier darf es poetisch werden — aber immer mit konkretem Bezug zum Produkt-Benefit]
```

---

#### Slice 4: QUALITAET + TRUST

```markdown
## SLICE 4: QUALITAET + TRUST (der Closer)

**Ueberschrift (Amazon-Feld):**
> [z.B. "Material das haelt was es verspricht"]

**Kernbotschaft:**
Der Kaeufer sieht den Beweis fuer die Qualitaet + bekommt die Vertrauens-Elemente.

**Adressierter Painpoint:**
"Ist das wirklich hochwertig?"

**Psychologische Funktion:**
Action-Vorbereitung — Sicherheit + Preis-Rechtfertigung.

---

### Kreative Bild-Idee

**Visual Concept:**
Drei-Zonen-Kombination: Material-Beweis + Qualitaets-Story + Trust-Signale. Der Betrachter soll "sehen, verstehen, vertrauen".

**Material-Makro-Idee:** [z.B. "Extreme Nahaufnahme der Strickstruktur bei seitlichem Licht — jede Faser sichtbar. Oder: Querschnitt der Socke der die Schichtung zeigt."]

**Visualisierungs-Idee fuer Qualitaet:** [z.B. "Handgestrickt-Detail-Foto (Naehnadel im Anschnitt), oder ein Vergleich mit einer Munze fuer Feinheit"]

---

### Desktop-Komposition (1464x600+)

**Aufteilung:** Drei-Zonen-Layout

| Zone | Inhalt |
|---|---|
| **Links (40%)** | Material-Makro (Strickstruktur, Nahaufnahme) |
| **Mitte (40%)** | Qualitaets-Story: Headline + 2-3 Bullet-Points zur Material-Herkunft |
| **Rechts (20%)** | Trust-Siegel-Leiste |

**Trust-Siegel:** Alle relevanten Zertifikate:
- [z.B. Oeko-Tex 100]
- [z.B. Made in EU]
- [z.B. Fair Trade]
- [z.B. Vegan]

**Material-Headline:**
[z.B. "80% Merinowolle aus [Herkunft]. Handgekettelte Spitze. Schadstofffrei zertifiziert."]

### Mobile-Komposition (600x450+)

**Aufteilung:** Vertikales Stack statt Drei-Zonen
- Oben: Material-Makro
- Mitte: Headline + Bullets
- Unten: Trust-Siegel horizontal

**Fliesstext:**
[3-4 Saetze. Fokus: Material-Herkunft, Produktion, Zertifikate. Warum der Preis gerechtfertigt ist.]
```

---

### TEIL C: Das Premium-Navigations-Karussell

```markdown
## KARUSSELL: 5 Deep-Dive Panels

**Gesamt-Konzept:**
Jedes Panel vertieft einen Benefit den die 4 Slices nur angerissen haben. Der Kaeufer waehlt selbst welche Panels ihn interessieren.

**Regel fuer den Designer:**
Die 5 Panels muessen visuell klar unterscheidbar sein. Der Designer waehlt dafuer:
- Unterschiedliche Farben aus der Kunden-CI (oder abgeleitete Toene)
- Unterschiedliche Bildmotive (jede Panel anderes Visual)
- Konsistente Typografie

Die Content-Agent liefert pro Panel eine **kreative Bild-Idee** als Ausgangspunkt.
```

#### Panel 1-5 Template (pro Panel)

```markdown
## KARUSSELL Panel [X]: [Benefit-Name]

**Navigationstext** (Label im Thumbnail, max 30 chars):
> [z.B. "Blasenfreier Schutz"]

**Ueberschrift** (Detail-View):
> [z.B. "Nie wieder Pflaster im Rucksack"]

**Unterueberschrift** (optional):
> [z.B. "Die Physik hinter dem Versprechen"]

**Fliesstext** (Body):
- [Bullet 1]
- [Bullet 2]
- [Bullet 3]

---

### Kreative Bild-Idee (Painpoint-Metapher)

**Visual Concept Thumbnail (kleine Kachel):**
[Die Hauptidee fuer die klickbare Kachel. Was sieht der Kaeufer bevor er klickt?]

Beispiele:
- "Ein gekaemmtes Stueck Wolle im Detail, dazu der Pflaster-Muellhaufen im Hintergrund unscharf — visuelle Metapher: Keine Pflaster mehr noetig"
- "Ein einzelner Socken-Ausschnitt mit Polster-Detail, Icon eines Schildes eingebettet"

**Visual Concept Detail-Bild (grosse Ansicht):**
[Die tiefere Visualisierung fuer die Detail-View nach Klick. Was sieht der Kaeufer wenn er mehr wissen will?]

Beispiele:
- "Querschnitt-Illustration der Sockenstruktur mit Callout-Pfeilen zu den Verstaerkungs-Zonen. Links ein echtes Foto des Wanderstiefels, rechts die technische Zeichnung als Uebergang."
- "Ein visueller Vorher/Nachher-Split: Links ein Fuss nach langer Wanderung mit roten Druckstellen (angedeutet), rechts der gleiche Fuss in unserer Socke — entspannt."

**Painpoint-Metapher:** [Die kreative Hauptidee in einem Satz]

---

### Thumbnail-Komposition (klickbare Kachel, klein)

**Hintergrund:** [Designer-Farbwahl aus CI]
**Produktausschnitt:** [welches Detail]
**Text-Overlay:** [Navigationstext, gut lesbar]
**Icon (optional):** [passendes Icon zur Metapher]

---

### Detail-Bild (nach Klick, gross)

**Desktop-Komposition (1464x600+):**

**Layout:** [z.B. Zweispaltig — links Headline+Bullets, rechts Produktbild/Infografik]
**Hauptmotiv:** [konkrete Beschreibung basierend auf Visual Concept]
**Text-Overlay:** 
- Headline: [exakter Text]
- Bullets: [mit Check-Icons]

**Mobile-Komposition (600x450+):**

**Unterschied:** [z.B. Vertikal gestackt, Hauptmotiv oben, Text unten]

---

### Adressierter Painpoint
[Welches Problem loest dieser Benefit]

### Psychologische Funktion
[Welcher Trigger — Sicherheit, Komfort, Status, etc.]
```

---

### TEIL D: Comparison-Modul

```markdown
## Comparison-Modul (Amazon-Formular)

**WICHTIG:** Dies ist KEINE Designer-Komposition. Amazon-Formular, nur Content.

### Inhalte

**Produkte zum Vergleich (5 ASINs der eigenen Marke):**
1. [Dieses Produkt]
2. [Variante 1]
3. [Variante 2]
4. [Variante 3]
5. [Variante 4]

### Vergleichs-Zeilen

| Zeile | Werte pro ASIN |
|---|---|
| **Material** | [Wert 1] / [Wert 2] / ... |
| **Hauptanwendung** | |
| **Polsterung** | |
| **Hoehe** | |
| **Packung** | |
| **Preis (geschaetzt)** | |

**Ziel:** Cross-Selling + Retention.
```

---

## Design-Richtlinien (fuer den Grafiker)

Als Briefing-Anhang, klar kommuniziert:

**Farbgebung:**
- Nutze die CI-Farben des jeweiligen Kunden
- Sorge fuer visuelle Differenzierung der 5 Karussell-Panels (unterschiedliche Farbtoene oder abgeleitete Shades wenn CI schlank ist)
- Hoher Kontrast fuer Text-Lesbarkeit auf Mobile (WCAG AA minimum)

**Typografie:**
- Kunden-CI Schriften verwenden
- Minimum 30pt fuer Text-Overlays (Mobile-Lesbarkeit)
- Konsistenz ueber alle Slices

**Bildsprache:**
- Authentisch, nicht Stock-Photo-Look
- Passend zum Marken-Ton (siehe Meta-Header)
- Die kreativen Bild-Ideen im Briefing sind Ausgangspunkt, nicht Pflicht — der Designer kann alternative Umsetzungen waehlen wenn sie das Konzept besser treffen

---

## Master-Komposition (Orientierung fuer den Designer)

Der A+ Content Designer erstellt am Anfang des Briefings eine kurze **Konzept-Uebersicht**:

- Welche narrativen Themen durchziehen die 4 Slices?
- Welche visuellen Motive wiederholen sich (z.B. Natur-Elemente, Materialtexturen)?
- Wie sollte der Gesamt-Look wirken? (sportlich/gemuetlich/premium/nahbar)

Diese Uebersicht gibt dem Designer eine kreative Richtung ohne die konkrete Umsetzung vorzugeben.

---

## Qualitaets-Check vor Abgabe

- [ ] Alle 4 Slices haben eine einzigartige Aufgabe (keine Redundanz)
- [ ] Narrativer Bogen ist schluessig (AIDA erkennbar)
- [ ] Jede Slice hat Desktop UND Mobile-Komposition
- [ ] Jede Slice hat eine kreative Bild-Idee (nicht nur Layout-Beschreibung)
- [ ] Karussell-Panels decken 5 verschiedene Benefits ab (keine Wiederholung)
- [ ] Jedes Panel hat eigene Bild-Metapher fuer Thumbnail + Detail
- [ ] Alle Text-Overlays sind min. 30pt (Mobile)
- [ ] Trust-Elemente sind in Slice 4 konsolidiert
- [ ] Lifestyle-Szene in Slice 3 ist emotional und konkret
- [ ] Keine Duplikate zwischen Slices und Galerie-Bildern
- [ ] Comparison-Modul hat 5 ASINs + mindestens 5 Vergleichs-Zeilen
- [ ] KEINE konkreten Farben vorgegeben (Designer-Aufgabe)
