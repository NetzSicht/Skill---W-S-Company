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

- `produkt-analyse.md` — Product data, brand info, **CI-Farben (Sektion 1b)**
- `listing-briefing.md` — Gallery content (to avoid duplication). Read the **A+ Uebergabe** section first.
- `listing-texte.md` — Bullet/description content (to avoid duplication)
- `review-insights.md` — Unanswered questions, painpoints, customer vocabulary

**KRITISCH:** Pruefe ob die CI-Farben vollstaendig sind. Wenn `[BEIM KUNDEN ANFRAGEN]` markiert ist, escaliere an CEO — das Briefing kann nicht fertiggestellt werden ohne CI-Farben.

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

- Meta-Daten (Produkt, ASIN, Marktplatz, Brand Registry, CI-Farben)
- Narrativer Bogen (was erzaehlen die 4 Slices zusammen)
- Painpoint-Mapping (aus review-insights.md → Slices und Karussell-Panels)

## 7. Baue die 4 Slices

### Slice 1: HERO

Lies Slice-1-Template aus `aplus-content-template` skill. Liefere:
- Ueberschrift (Haupt-Versprechen, 3-5 Woerter)
- Kernbotschaft, Painpoint, psychologische Funktion
- Desktop-Komposition (1464x600+) mit 3-4 Badges + Positionen
- Mobile-Komposition (600x450+) mit Anpassungen
- Text-Spezifikationen (Schriftgroessen, Farben aus CI)
- Optional: Fliesstext

**Badge-Farbzuordnung aus CI:**
- Top-USP = Primaerfarbe
- Zweiter Benefit = Sekundaerfarbe
- Weitere = abgeleitete Toene

### Slice 2: BENEFIT-ROUNDEL

- Ueberschrift ("5 Gruende..." oder aehnlich)
- 5 Icons mit Labels (jedes adressiert einen Painpoint)
- Icon-Stil: Line-Icons, einheitliche Strichstaerke, weisse Kreise
- Desktop: 5 in einer Reihe / Mobile: 3+2 oder alle 5 kleiner
- Optional: Trust-Badge im Hintergrund

**Wichtig:** Jedes der 5 Icons adressiert einen konkreten Search-Painpoint aus `review-insights.md`. Keine generischen Benefits.

### Slice 3: LIFESTYLE + TOP-BENEFIT

- Ueberschrift (emotionale Szene in einem Satz)
- Konkrete Nutzungs-Szene: Wer, Wann, Wo, Wie
- Echter Mensch (nicht generisches Stock-Foto)
- Gaze Cueing: Model-Blick auf Produkt oder Moment
- Warme Lichtstimmung passend zur CI
- Optional: subtiler Top-Benefit-Banner

**Wichtig:** Diese Slice ist der **Desire-Trigger** — hier entscheidet sich ob der Kaeufer sich mit dem Produkt identifiziert. Nicht langweilig machen.

### Slice 4: QUALITAET + TRUST

- Ueberschrift (konkrete Qualitaets-Aussage)
- Drei-Zonen-Layout: Material-Makro | Story-Text | Trust-Siegel
- Alle relevanten Zertifikate konsolidiert (Oeko-Tex, EU, etc.)
- Material-Story im Fliesstext (Herkunft, Produktion, Warum der Preis gerechtfertigt ist)
- Mobile: vertikal gestackt

## 8. Baue das Karussell (5 Panels)

Fuer jedes Panel:

1. **Benefit auswaehlen** aus den Top 5 Search-Painpoints oder USPs
2. **CI-Farbe zuordnen** mit Begruendung ("Primaerfarbe weil wichtigster Benefit")
3. **Navigationstext** (max 30 chars, klickbares Label)
4. **Detail-View-Content** (Ueberschrift, Unterueberschrift, Bullets)
5. **Thumbnail-Komposition** (Panel-Farbe + Produktausschnitt + Text)
6. **Detail-Bild Desktop** (1464x600+)
7. **Detail-Bild Mobile** (600x450+)

**CI-Farbzuordnung Regel:**
- Panel 1 (wichtigster Benefit) → Primaerfarbe
- Panel 2 → Sekundaerfarbe
- Panel 3-5 → abgeleitete Toene (heller/dunkler/akzentuiert)
- Bei nur 2 CI-Farben: Fallback mit Graustufen + Akzent

**Regel:** Die 5 Panels muessen visuell unterscheidbar sein. Wenn zwei Panels gleich aussehen → verloren.

## 9. Baue das Comparison-Modul (nur Content)

**KEINE Designer-Komposition.** Amazon-Formular wird ausgefuellt:

- 5 Produkte zum Vergleich (ASINs aus eigener Produktpalette)
- 5-6 Vergleichs-Zeilen (Material, Hoehe, Einsatz, Groessen, Preis, etc.)
- Werte pro Zelle

**Ziel:** Cross-Selling. Der Kaeufer findet das passendere Produkt in unserer Marke oder bestaetigt die Wahl.

## 10. Master-Komposition skizzieren

Am Anfang des Briefings: Eine kurze Uebersicht wie die 4 Slices + das Karussell **zusammen** aussehen. ASCII-Skizze oder kurze textuelle Beschreibung reicht — der Designer soll den Gesamt-Look verstehen.

Beispiel:
```
Slice 1: [Warm-Grau Hintergrund, rotes Hauptmotiv, 4 farbige Badges]
Slice 2: [Neutraler Hintergrund, 5 weisse Kreise mit Icons]
Slice 3: [Warmer Indoor-Look, Model mit Produkt]
Slice 4: [Material-Makro, Trust-Siegel-Leiste rechts]
Karussell Panel 1: [Rot/Primaer]
Karussell Panel 2: [Blau/Sekundaer]
Karussell Panel 3: [Gruen/Abgeleitet]
Karussell Panel 4: [Orange/Akzent]
Karussell Panel 5: [Grau/Neutral]
```

## 11. Self-Check

Bevor du das Briefing schreibst:

- [ ] Alle 4 Slices decken AIDA ab (Attention → Interest → Desire → Action)
- [ ] Slice 2 (Roundel) zeigt 5 Benefits, alle mit Painpoint-Bezug
- [ ] Slice 3 (Lifestyle) hat konkrete Szene mit Mensch + Emotion
- [ ] Slice 4 (Trust) konsolidiert alle Zertifikate
- [ ] Jede Slice hat Desktop UND Mobile-Komposition
- [ ] Karussell-Panels decken 5 verschiedene Benefits ab (keine Wiederholung)
- [ ] CI-Farben pro Panel zugeordnet mit Begruendung
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
