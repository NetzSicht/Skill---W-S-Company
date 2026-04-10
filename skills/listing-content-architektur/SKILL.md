---
name: listing-content-architektur
description: "Koordination zwischen 7-Slot Bildergalerie und A+ Content. Definiert welche Inhalte wohin gehoeren, die No-Duplication-Regeln, den narrativen Uebergang und das Zusammenspiel beider Ebenen als ein Conversion-System. Wird von Listing-Briefer UND A+ Content Designer genutzt."
---

# Listing Content Architektur

Die Amazon-Produktseite ist ein geschichtetes Ueberzeugungssystem. Galerie und A+ Content sind keine getrennten Projekte — sie sind **ein Funnel mit zwei Ebenen**.

---

## Das Schichtenmodell

```
┌─────────────────────────────────────────────┐
│  ABOVE THE FOLD — Schnelle Ueberzeugung     │
│  (3-5 Sekunden Entscheidungszeit)           │
│                                              │
│  7-Slot Galerie    → Emotion + Quick Facts   │
│  Titel             → Suchrelevanz + Klarheit │
│  Bullet Points     → Features als Benefits   │
├─────────────────────────────────────────────┤
│  BELOW THE FOLD — Tiefe Ueberzeugung        │
│  (fuer High-Involvement-Kaeufer)            │
│                                              │
│  Brand Story       → Vertrauen + Cross-Sell  │
│  A+ Content        → Edukation + Einwaende   │
│  (3-7 Module)       + Vergleich + FAQ        │
└─────────────────────────────────────────────┘
```

**Wer scrollt bis A+?**
- Kaeufer mit hohem Involvement (teure Produkte, Erstkaeufe, komplexe Produkte)
- Kaeufer die noch zwoegern (brauchen mehr Ueberzeugung)
- Kaeufer die aktiv vergleichen (suchen Details)

**Wer kauft schon above the fold?**
- Impulskäufer (guenstige Produkte, bekannte Marke)
- Wiederkäufer (kennen das Produkt schon)

→ Die Galerie muss ALLEINE konvertieren koennen. A+ Content ist der Booster, nicht die Grundlage.

---

## Die Aufteilungsregel: Was gehoert wohin?

### Galerie (7 Slots) — "Schnell ueberzeugen"

| Gehoert HIERHIN | Warum |
|---|---|
| Produkt-Gesamtbild (Hero) | Erste Impression, CTR |
| Emotionale Verankerung (Lifestyle) | Kaufentscheidung ist emotional |
| Top 3-5 Benefits (Infografik) | Schnelle rationale Rechtfertigung |
| Groesse/Dimensionen | Retouren-Praevention |
| Material/Qualitaet (Nahaufnahme) | Preis-Rechtfertigung |
| Lieferumfang | Erwartungsmanagement |
| Vergleich/Trust | Finaler Conversion-Schubs |

### A+ Content — "Tief ueberzeugen"

| Gehoert HIERHIN | Warum |
|---|---|
| Markengeschichte (Brand Story) | Emotionale Bindung + Cross-Selling |
| Technologie-Erklaerung | Zu komplex fuer eine Infografik |
| Anwendungsszenarien (erweitert) | Galerie zeigt 1 Szene, A+ zeigt 2-3 weitere |
| Interaktive Details (Premium A+) | Hotspots, aufklappbare Sektionen |
| Shoppable Vergleichstabelle | Eigene Varianten (defensive Retention) |
| FAQ / Haeufige Bedenken | Proaktive Einwand-Behandlung |
| Zutatentiefe / Herkunft | Fuer ingredient-educated Kaeufer |
| Video-Demo | Produkt in Aktion (nur Premium A+) |

---

## Die No-Duplication-Matrix

**Absolutes Verbot:** Kein A+ Bild darf identisch mit einem Galerie-Bild sein.

| Element | Galerie | A+ | Erlaubt? |
|---|---|---|---|
| Gleiches Foto, gleicher Ausschnitt | ✓ | ✓ | VERBOTEN |
| Gleiches Foto, anderer Ausschnitt/Kontext | ✓ | ✓ | ERLAUBT (mit Vorsicht) |
| Gleiche Botschaft, andere Visualisierung | ✓ | ✓ | ERLAUBT |
| Gleicher Benefit, tiefere Erklaerung | ✓ (Headline) | ✓ (Detail) | IDEAL |
| Komplett neuer Inhalt | — | ✓ | IDEAL |

### Konkrete Beispiele

**FALSCH:**
- Galerie Slot 3: Infografik "3 Benefits" → A+ Modul: Dieselbe Infografik, selbes Layout
- Galerie Slot 2: Lifestyle-Bild Kueche → A+ Hero: Exakt dasselbe Foto

**RICHTIG:**
- Galerie Slot 3: Infografik "3 Benefits" (Ueberblick) → A+ Modul: Jeden Benefit einzeln erklaert mit Querschnitt/Animation
- Galerie Slot 2: Lifestyle-Bild Kueche (Frau kocht) → A+ Lifestyle: Anderes Setting (Familie am Tisch, Ergebnis des Kochens)

---

## Der Narrative Uebergang

Die Geschichte muss nahtlos von der Galerie in A+ fliessen:

```
GALERIE erzaehlt:
  "Das ist das Produkt. Es passt zu dir. Es hat diese Vorteile.
   So gross ist es. So hochwertig. Das bekommst du. Besser als andere."

BRAND STORY ergaenzt:
  "Das sind die Menschen hinter dem Produkt. Das treiben sie an.
   Hier sind weitere Produkte die dich interessieren koennten."

A+ CONTENT vertieft:
  "So funktioniert die Technologie dahinter. Hier sind weitere
   Anwendungsfaelle. Das sagen andere Kaeufer. Hier sind Antworten
   auf deine restlichen Fragen."
```

Die Galerie beantwortet: **"Soll ich das kaufen?"**
A+ Content beantwortet: **"Habe ich etwas uebersehen?"**

---

## Koordinations-Protokoll

### Fuer den Listing-Briefer (Galerie)

Wenn du das Bild-Briefing erstellst:

1. **Markiere am Ende jedes Slots** was NICHT abgedeckt wurde und was A+ vertiefen sollte
2. **Im Briefing-Footer** erstelle eine "A+ Uebergabe"-Sektion:

```markdown
## A+ Content Uebergabe

### In der Galerie abgedeckt:
- [Benefit 1 in Slot 3]
- [Groesse in Slot 4]
- [Material in Slot 5]

### NICHT abgedeckt — A+ muss uebernehmen:
- [Technologie-Erklaerung hinter dem Produkt]
- [Weitere Anwendungsszenarien]
- [Detaillierte Zutatenliste / Herkunftsinfos]
- [FAQ: Haeufigste Kundenfragen]

### Bilder die A+ NICHT wiederholen darf:
- Slot 2 Lifestyle: [Beschreibung]
- Slot 3 Infografik: [Beschreibung]
```

### Fuer den A+ Content Designer

Wenn du das A+ Briefing erstellst:

1. **Lies zuerst das Bild-Briefing** — die "A+ Uebergabe"-Sektion ist dein Startpunkt
2. **Kein Modul darf eine Galerie-Botschaft wiederholen** — nur vertiefen oder ergaenzen
3. **Pruefe jedes geplante A+ Bild** gegen die Galerie-Bilder (keine Duplikate)
4. **Die Vergleichstabelle in A+** ist ANDERS als in Slot 7:
   - Slot 7: Eigenes Produkt vs. generische Alternative (einfach, binaer)
   - A+ Vergleich: Eigene Produktvarianten untereinander (shoppable, cross-selling)

---

## Conversion-Metriken — Wer traegt was bei

| Ebene | Primaere Metrik | Benchmark-Uplift |
|---|---|---|
| Galerie (7 Slots) | CTR + CVR above-the-fold | +15-32% CVR bei Optimierung |
| Standard A+ | CVR below-the-fold + Dwell Time | +3-10% CVR |
| Premium A+ | CVR + Engagement + Cross-Sell | +15-20% CVR |
| Brand Story | Trust + Cross-Sell Rate | Prerequisite fuer Premium A+ |
| Galerie + A+ zusammen | Gesamt-CVR | Multiplikativ, nicht additiv |

**Wichtig:** Die 7-Slot-Galerie allein muss die Conversion tragen. A+ ist der Multiplikator — aber kein Ersatz fuer eine schwache Galerie.

---

## Checkliste: Galerie-A+ Abstimmung

Vor dem Quality Review pruefen:

- [ ] Kein A+ Bild ist identisch mit einem Galerie-Bild
- [ ] Kein A+ Modul wiederholt eine Galerie-Botschaft 1:1
- [ ] Die "A+ Uebergabe" im Bild-Briefing ist ausgefuellt
- [ ] A+ vertieft was die Galerie anreisst (nicht umgekehrt)
- [ ] Galerie konvertiert auch OHNE A+ (A+ ist Booster, nicht Basis)
- [ ] A+ Vergleichstabelle zeigt eigene Varianten (nicht wie Slot 7 Generika)
- [ ] Brand Story ist enthalten (Cross-Selling + Premium A+ Prerequisite)
- [ ] Narrativer Bogen: Galerie → Brand Story → A+ fuehlt sich wie eine Geschichte an
