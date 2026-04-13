---
name: mobile-first-validation
description: "Mobile-First Validierungs-Loop fuer Listing-Outputs. Konkrete Checks auf iPhone-Viewports (320px, 375px, 414px), Thumbnail-Tests (150x150px), Text-Lesbarkeit und visuelle Hierarchie auf kleinen Screens. Genutzt von Listing-Briefer, Content Master, A+ Content Designer, Quality-Reviewer. 70%+ des Amazon-Traffics ist mobil — jedes Deliverable muss diese Checks bestehen."
---

# Mobile-First Validation

70% des Amazon-Traffics kommt von Mobilgeraeten. Ein Listing das auf dem Desktop gut aussieht aber auf dem iPhone faellt, verliert die Mehrheit der Kaeufer. Dieser Skill definiert die konkreten Pruefschritte pro Agent.

---

## Die 3 kritischen Viewports

| Viewport | Geraet | Wichtigkeit |
|---|---|---|
| **320px** | iPhone SE (kleinster noch relevanter Screen) | Jeder Text MUSS hier lesbar sein |
| **375px** | iPhone 12/13/14/15 (aktuelle Standard-Groesse) | Hauptoptimierungs-Ziel |
| **414px** | iPhone Plus/Max | Komfort-Anzeige |

Regel: **Wenn es auf 320px nicht funktioniert, funktioniert es nicht.**

---

## Test 1: Thumbnail-Test (150x150px)

Das erste Bild erscheint in Suchergebnissen als 150x150px Thumbnail. Auf dem Desktop als 300px.

**Pruefe fuer Slot 1:**
- [ ] Kann man das Produkt in <0.5 Sekunden erkennen?
- [ ] Ist bei Multipacks die Menge auf 150px noch zaehlbar?
- [ ] Ist die Hoehe bei Bekleidung (Sneaker vs. Quarter vs. Crew) erkennbar?
- [ ] Keine Detail-Texte die bei 150px unlesbar werden?
- [ ] Ist das Produkt zentral genug dass nichts weggeschnitten wirkt?

**Fehlerbilder:**
- Zu viel weisser Raum um das Produkt → Thumbnail zeigt winziges Produkt
- Detail-Text im Bild → unlesbar bei 150px
- Komplexe Komposition → bei 150px visuelles Rauschen
- Dunkles Produkt auf dunklem Schatten → kein Kontrast

---

## Test 2: First-Screen-Hierarchy (iPhone Standard-Ansicht)

Was sieht der Kaeufer **ohne zu scrollen** auf einem iPhone 12/13/14?

```
┌─────────────────────┐
│   Produktbild       │  ← Slot 1
│   (Quadrat)         │
│                     │
├─────────────────────┤
│   Titel (2-3 Zeilen)│  ← ersten 70 Zeichen wichtig
│   Marke             │
│   Sterne + Anzahl   │
├─────────────────────┤
│   Preis prominent   │
│   Prime-Hinweis     │
└─────────────────────┘
                       ← Hier wird gescrollt
```

**Pruefe:**
- [ ] Sind die ersten 70 Zeichen des Titels aussagekraeftig?
- [ ] Ist der Hauptbenefit im Titel erkennbar ohne den vollen Titel zu lesen?
- [ ] Ist das Produkt im Bild gross genug dass der Daumen nicht am Preis landet?
- [ ] Gibt es einen Kaufgrund bevor gescrollt werden muss?

---

## Test 3: Bullet-Point-Lesbarkeit auf 320px

Mobile zeigt Bullets in reduzierter Schrift. Lange Bullets werden abgeschnitten.

**Pro Bullet pruefen:**
- [ ] Max. 200 Zeichen (sonst Abschnitt oder "mehr anzeigen"-Button)
- [ ] CAPS-Anker (2-3 Woerter) am Anfang — scanbar auf Mobile
- [ ] Wichtigste Info in den ersten 50 Zeichen
- [ ] Keine langen Schachtelsaetze
- [ ] Benefit zuerst, Feature dann (nicht umgekehrt)

**Formel fuer Mobile-optimierte Bullets:**
```
[CAPS ANKER 2-3 WOERTER] — [Benefit in 10 Woertern]. [Mechanismus/Beleg in 15 Woertern]. [Optional: Szene oder Zahl]
```

---

## Test 4: Slot-Infografik Text-Lesbarkeit

Text-Overlays in Slots 2-7 muessen auf Mobile lesbar bleiben.

**Mindestanforderungen:**

| Element | Desktop | Mobile (min) |
|---|---|---|
| Hauptueberschriften | 60pt | 40pt |
| Benefit-Callouts | 40pt | 30pt |
| Kleingedrucktes | 24pt | Vermeiden — auf Mobile unlesbar |
| Zeilenabstand | 1.2 | 1.4 (mehr Luft) |
| Kontrast | WCAG AA | WCAG AAA (hoeher) |

**Regel:** Wenn Text im Bild unter 30pt (relativ zur Bildgroesse) ist, gehoert er nicht ins Bild sondern in den Bulletpoint.

---

## Test 5: Content-Density-Check

Mobile verzeiht keine ueberladenen Bilder. Weniger ist mehr.

**Pro Slot:**
- [ ] Max. 5 Informationselemente pro Bild (Produkt + 4 Callouts)
- [ ] Eine Kernbotschaft — nicht drei halbe Botschaften
- [ ] Weissraum um wichtige Elemente
- [ ] Kein Text am Bildrand (wird auf Mobile angeschnitten)

---

## Test 6: A+ Content Mobile-Check

A+ Content Module haben eigene Mobile-Herausforderungen:

- [ ] Basic A+: 970px Breite — skaliert auf 360px Mobile (3x kleiner!)
- [ ] Premium A+: Full-Width — skaliert besser aber braucht mobile Variants
- [ ] Vergleichstabelle: Wird auf Mobile zu schmalen Spalten — max. 4-5 Kriterien
- [ ] Bilder in A+: JPG/PNG Dateigroesse unter 500KB (Mobile-Loading)
- [ ] Alt-Texte gefuellt (Mobile Screen Reader + Rufus-SEO)

---

## Pro Agent: Was genau pruefen?

### Listing-Briefer

Nach Erstellung des Briefings fuer jeden Slot:
1. Test 1 (Thumbnail) fuer Slot 1
2. Test 2 (First Screen) fuer Titel-Synergie
3. Test 4 (Text Overlays) fuer Slots 2-7
4. Test 5 (Content Density) fuer alle Slots

**Ergaenze im Briefing pro Slot ein Feld:**
```markdown
**Mobile-Check:** [PASS / WARN / FAIL]
**Mobile-Anpassung:** [Was der Designer fuer Mobile beachten muss]
```

### Content Master

Nach Erstellung von Titel und Bullets:
1. Test 2 (ersten 70 Zeichen Titel)
2. Test 3 (Bullet-Lesbarkeit)
3. Check: Sind Bullets unter 200 Zeichen?

**Ergaenze:**
```markdown
**Mobile-Check Titel:** Erste 70 Zeichen: "[Auszug]" — [PASS/WARN]
**Mobile-Check Bullets:** BP1 [X chars], BP2 [X chars], ...
```

### A+ Content Designer

Nach Erstellung des A+ Briefings:
1. Test 6 (A+ Mobile-Check)
2. Test 4 (Text in Modulen)
3. Check: Alt-Texte vorhanden?

### Quality-Reviewer

Als **Pflicht-Dimension** im Review (add zu den 7 Dimensionen):

**Dimension 11: Mobile-First Compliance**
- Alle 6 Tests durchgehen
- Bei FAIL in einem Test: Revision noetig
- Bei WARN: Flag mit Begruendung

---

## Self-Check Protokoll

Bevor ein Agent sein Output ausliefert:

```markdown
## Mobile-First Self-Check

- [ ] Thumbnail-Test (Slot 1) bestanden
- [ ] First-Screen-Hierarchy plausibel
- [ ] Bullet-Lesbarkeit auf 320px gegeben
- [ ] Text-Overlays mind. 30pt
- [ ] Content-Density max. 5 Elemente pro Slot
- [ ] A+ Content mobile-skalierbar
- [ ] Keine Elemente am Bildrand
- [ ] Keine langen Schachtelsaetze in Bullets

**Ergebnis:** [PASS / WARN mit Anmerkungen / FAIL mit Fixes]
```

Wenn du FAIL hast: fix und erneut pruefen, BEVOR du das Issue als done markierst.
