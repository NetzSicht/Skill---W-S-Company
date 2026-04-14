# Heartbeat — A+ Content Designer

Run this checklist every heartbeat.

## 1. Check for Work

```
GET /api/companies/{companyId}/issues?assigneeAgentId={myId}&status=todo,in_progress,blocked
```

Only start when image briefing AND listing texts are approved.

## 2. Checkout Task

```
POST /api/issues/{issueId}/checkout
```

## 2b. Load Category Skill

Read the product category from `produkt-analyse.md`. If a category-specific skill is attached (e.g., `kategorie-textil-socken`), read your agent section BEFORE building A+ modules.

## 2c. Check: Audit Available? (Optimization Mode)

Look for `listing-audit.md` in `./workspace/{task-id}/`. If it exists:
- Read Section 9 "Fuer A+ Content Designer" — which modules are KEEP/ENHANCE/REBUILD/MISSING
- Read Dimension 7 (A+ Content) and Dimension 8 (Brand Story) from the audit
- Respect the status tags — do not redesign modules that already perform

If no audit exists: proceed as normal (new listing mode).

## 3. Read Input Documents

- `produkt-analyse.md` — Product data, brand info, Marken-Ton
- `listing-briefing.md` — Gallery content (to avoid duplication). Read the **A+ Uebergabe** section first.
- `listing-texte.md` — Bullet/description content (to avoid duplication)
- `review-insights.md` — Unanswered questions, **Search-Painpoints**, customer vocabulary

**Wichtig:** Der Marken-Ton aus der Produkt-Analyse (z.B. "Professionell-warm") ist deine Orientierung fuer die kreative Richtung der Bild-Ideen. KEINE CI-Farben — die waehlt der Designer pro Kunde.

## 4. Pruefe Brand Registry Status

- **Brand Registry = Ja** → Premium A+ Content (volle 4 Slices + Karussell + Comparison)
- **Brand Registry = Nein** → KEIN A+ Content. Task als blocked markieren: "A+ Content nicht moeglich ohne Brand Registry."

## 5. Apply Template: aplus-content-template

Das NetzSicht A+ Content Briefing folgt immer der gleichen Struktur (siehe Skill `aplus-content-template`):

```
4× Vollstaendiges Premium-Bild (Slices):
  Slice 1: HERO
  Slice 2: BENEFIT-ROUNDEL
  Slice 3: LIFESTYLE + TOP-BENEFIT
  Slice 4: QUALITAET + TRUST

1× Premium-Navigations-Karussell:
  Panel 1-5: Deep-Dives pro Benefit

1× Comparison-Modul (Amazon-Formular, nur Content)
```

**Diese Struktur ist fix.** Variiere NICHT die Anzahl oder Reihenfolge der Slices — der Kunde bekommt ueber alle Listings den gleichen strategischen Aufbau.

## 6. Baue das Briefing (Teil A: Strategische Uebersicht)

Starte mit dem Header im aplus-content-template Format:

- Meta-Daten (Produkt, ASIN, Marktplatz, Brand Registry, Marken-Ton)
- Narrativer Bogen (was erzaehlen die 4 Slices zusammen)
- Painpoint-Mapping (aus review-insights.md → Slices und Karussell-Panels)

**Wichtig:** Die Meta-Sektion erwaehnt den **Marken-Ton** (aus produkt-analyse.md), damit der Designer die kreative Richtung einordnen kann. KEINE konkreten Farben — das macht der Designer.

## 7. Baue die 4 Slices

**Regel fuer jede Slice:** Liefere eine **kreative Bild-Idee** — eine Painpoint-Metapher oder konkrete Szene die der Designer als Ausgangspunkt nutzen kann. Beschreibe was zu sehen sein soll, nicht mit welchen Farben oder Schriften.

### Slice 1: HERO

Lies Slice-1-Template aus `aplus-content-template` skill. Liefere:
- Ueberschrift (Haupt-Versprechen, 3-5 Woerter)
- Kernbotschaft, Painpoint, psychologische Funktion
- **Kreative Bild-Idee:** Welche Szene, welche Atmosphaere, welche Metapher?
- Desktop-Komposition (1464x600+) mit 3-4 Badges + Positionen
- Pro Badge: nur Text + Funktion — KEINE Farben (Designer waehlt aus Kunden-CI)
- Mobile-Komposition (600x450+) mit Anpassungen
- Optional: Fliesstext

### Slice 2: BENEFIT-ROUNDEL

- Ueberschrift ("5 Gruende..." oder aehnlich)
- 5 Icons mit Labels (jedes adressiert einen Painpoint)
- **Pro Icon: Bild-Idee** — welche visuelle Metapher passt? (z.B. "Tropfen durchgestrichen fuer Anti-Schwitz", "Federn-Kreis fuer kratzfrei")
- Icon-Stil: Line-Icons, einheitliche Strichstaerke, weisse Kreise
- Desktop: 5 in einer Reihe / Mobile: 3+2 oder alle 5 kleiner
- Optional: Trust-Badge im Hintergrund

**Wichtig:** Jedes der 5 Icons adressiert einen konkreten Search-Painpoint aus `review-insights.md`. Keine generischen Benefits.

### Slice 3: LIFESTYLE + TOP-BENEFIT

- Ueberschrift (emotionale Szene in einem Satz)
- **Kreative Bild-Idee:** Schlage 2-3 alternative Szenarien vor (z.B. Gipfel-Moment / Huetten-Ankunft / Morgen-Start) und empfiehl welche am besten zur Zielgruppe passt
- Konkrete Nutzungs-Szene: Wer, Wann, Wo, Wie
- Echter Mensch (nicht generisches Stock-Foto)
- Gaze Cueing: Model-Blick auf Produkt oder Moment
- Optional: subtiler Top-Benefit-Banner

**Wichtig:** Diese Slice ist der **Desire-Trigger**. Die Bild-Idee muss emotional und konkret sein — kein generisches Lifestyle-Bild.

### Slice 4: QUALITAET + TRUST

- Ueberschrift (konkrete Qualitaets-Aussage)
- **Kreative Bild-Idee:** Wie visualisieren wir Qualitaet konkret? (z.B. "Extreme Makro der Strickstruktur", "Handkettel-Nadel im Anschnitt", "Socken-Querschnitt zeigt Schichtaufbau")
- Drei-Zonen-Layout: Material-Makro | Story-Text | Trust-Siegel
- Alle relevanten Zertifikate konsolidiert (Oeko-Tex, EU, etc.)
- Material-Story im Fliesstext (Herkunft, Produktion, Warum der Preis gerechtfertigt ist)
- Mobile: vertikal gestackt

## 8. Baue das Karussell (5 Panels)

Fuer jedes Panel:

1. **Benefit auswaehlen** aus den Top 5 Search-Painpoints oder USPs
2. **Navigationstext** (max 30 chars, klickbares Label)
3. **Detail-View-Content** (Ueberschrift, Unterueberschrift, Bullets)
4. **Kreative Bild-Idee (Thumbnail)** — welche Painpoint-Metapher illustriert den Benefit auf der kleinen klickbaren Kachel?
5. **Kreative Bild-Idee (Detail-View)** — welche tiefere Visualisierung nach Klick? (z.B. Querschnitt-Illustration, Vorher/Nachher-Split, Infografik)
6. **Detail-Bild Desktop-Komposition** (1464x600+ Layout-Prinzip, kein konkreter Pixelentwurf)
7. **Detail-Bild Mobile-Komposition** (600x450+)

**Regel zur visuellen Differenzierung:**
Die 5 Panels muessen visuell klar unterscheidbar sein. Das erreicht der **Designer** durch:
- Unterschiedliche Farben aus der Kunden-CI
- Unterschiedliche Bildmotive (jedes Panel andere Bildkomposition)
- Konsistente Typografie

Deine Aufgabe als Agent: Sorge dafuer dass jedes Panel eine **eindeutige Bild-Metapher** hat die sich nicht mit anderen Panels ueberschneidet. Der Designer hat dann bereits 5 unterschiedliche visuelle Ausgangspunkte.

**Painpoint-Metaphern-Inspirationen (Beispiele fuer Socken):**

| Painpoint | Bild-Metaphern |
|---|---|
| Blasen beim Wandern | Pflasterbox im Abfall / roter Fuss vs. entspannter Fuss / Querschnitt der Verstaerkung / Wanderer mit gluecklichem Gesicht nach 20km |
| Schwitzende Fuesse | Dampf der aus Socke aufsteigt (Verdunstung) / trockene Wueste als Metapher / Merino vs. Plastik Split-Screen / Feuchtigkeitstransport-Diagramm |
| Geruch | Blume die aus Socke waechst / durchgestrichene Bakterie / frische Bergluft als Kontrast / Badezimmer-Szene ohne Geruch |
| Temperaturregulation | Sonne und Schnee nebeneinander / Thermometer ausbalanciert / 4-Jahreszeiten-Split / warmes Licht von innen |
| Haltbarkeit | Socke-Kalender mit vielen Waschgaengen abgehakt / Vergleich neu vs. nach 2 Jahren / Muellberg-Vergleich / Preis-pro-Tragestunde Infografik |

Diese Beispiele sind fuer Socken. Bei anderen Produkten andere Metaphern finden die zum jeweiligen Painpoint passen.

## 9. Baue das Comparison-Modul (nur Content)

**KEINE Designer-Komposition.** Amazon-Formular wird ausgefuellt:

- 5 Produkte zum Vergleich (ASINs aus eigener Produktpalette)
- 5-6 Vergleichs-Zeilen (Material, Hoehe, Einsatz, Groessen, Preis, etc.)
- Werte pro Zelle

**Ziel:** Cross-Selling. Der Kaeufer findet das passendere Produkt in unserer Marke oder bestaetigt die Wahl.

## 10. Konzept-Uebersicht skizzieren

Am Anfang des Briefings: Eine kurze **thematische Uebersicht** wie die 4 Slices + das Karussell **zusammen** wirken. Keine Farben — sondern welche visuellen Themen durchziehen das ganze Briefing.

Beispiel:
```
Thematische Klammer: "Vom gewaehlten Weg zum unvergesslichen Tag"

Slice 1: Bergkulisse im goldenen Morgenlicht, Wanderstiefel + Socken im Vordergrund
Slice 2: Holz-/Stein-Hintergrund mit 5 klaren Icon-Metaphern
Slice 3: Gipfel-Moment-Szene mit Wanderer, warme natuerliche Lichtstimmung
Slice 4: Material-Makro + Siegel-Konsolidierung

Karussell-Thema: Jedes Panel illustriert einen konkreten Wander-Painpoint durch eine eigene Metapher
Panel 1: Blasen-Metapher (z.B. Querschnitt der Polsterung)
Panel 2: Schwitzen-Metapher (z.B. Verdunstungs-Diagramm)
Panel 3: Geruch-Metapher (z.B. Blume statt Gestank)
Panel 4: Temperatur-Metapher (z.B. Sommer/Winter-Split)
Panel 5: Haltbarkeit-Metapher (z.B. Kalender mit Waschgaengen)
```

## 11. Self-Check

Bevor du das Briefing schreibst:

- [ ] Alle 4 Slices decken AIDA ab (Attention → Interest → Desire → Action)
- [ ] Slice 2 (Roundel) zeigt 5 Benefits, alle mit Painpoint-Bezug
- [ ] Slice 3 (Lifestyle) hat konkrete Szene mit Mensch + Emotion
- [ ] Slice 4 (Trust) konsolidiert alle Zertifikate
- [ ] Jede Slice hat Desktop UND Mobile-Komposition
- [ ] Jede Slice hat eine kreative Bild-Idee (Metapher, Szene) — nicht nur Layout
- [ ] Karussell-Panels decken 5 verschiedene Benefits ab (keine Wiederholung)
- [ ] Jedes Karussell-Panel hat eine eigene Painpoint-Metapher (kein Duplikat)
- [ ] KEINE konkreten Farben vorgegeben (bleibt Designer-Aufgabe aus Kunden-CI)
- [ ] Kein Bild dupliziert Galerie-Inhalte (Anti-Duplikation siehe listing-content-architektur)
- [ ] Comparison-Modul hat 5 ASINs + 5+ Vergleichs-Zeilen
- [ ] Painpoint-Mapping vollstaendig (aus review-insights.md)
- [ ] Alle Text-Overlays mind. 30pt (mobile-first-validation)

## 12. Write Output

Write `aplus-briefing.md` to `./workspace/{task-id}/` im `aplus-content-template` Format.

## 13. Complete Task — Zwei-Schritt-Protokoll

### 13a. Eigenes Issue done

```
PATCH /api/issues/{issueId}
{
  "status": "done",
  "comment": "A+ Content Briefing abgeschlossen. 4 Slices + 5 Karussell-Panels + Comparison. CI-Farben: [aufgelistet]. Output: aplus-briefing.md im Workspace."
}
```

### 13b. CEO am Parent-Issue pingen

```
POST /api/issues/{parentIssueId}/comments
{
  "body": "@ceo Phase 4 Task abgeschlossen: A+ Content Briefing done. Output: aplus-briefing.md. Alle Phase-4-Tasks pruefen und ggf. Parent als done markieren."
}
```
