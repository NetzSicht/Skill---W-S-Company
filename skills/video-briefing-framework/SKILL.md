---
name: video-briefing-framework
description: "Framework fuer Amazon Listing Video-Briefings. Definiert Struktur fuer 30-Sekunden-Videos im Bild-Slot (Brand Registry Pflicht). Script-Aufbau, Scene-by-Scene, Voice-Over-Regeln, Text-Overlays, B-Roll Ideen. Genutzt vom Listing-Briefer. Listings mit Video konvertieren 9-15% hoeher."
---

# Video-Briefing Framework

Amazon erlaubt fuer Brand-Registry-Seller ein Video als **zusaetzlicher Bild-Slot** in der Galerie. Dieser Skill definiert wie der Listing-Briefer das Video-Briefing erstellt.

**Wichtige Zahlen:**
- Listings mit Video: **+9-15% Conversion-Rate**
- Kaeufer sind **3.6x wahrscheinlicher** kaufbereit nach Video-Ansicht
- Effekt primaer von Mobile-Nutzern getrieben
- Ideal-Laenge: **20-30 Sekunden** (laenger = hohe Drop-off-Rate)

**Voraussetzung:** Brand Registry aktiv. Ohne Brand Registry: Video-Slot nicht verfuegbar, Skill nicht aktivieren.

---

## Wann ein Video erstellen?

Nicht jedes Listing braucht ein Video. Kriterien:

| Produkt | Video-Prioritaet |
|---|---|
| Technisches Produkt mit Demo-Potenzial | HOCH (Elektronik, Kuechengeraete) |
| Komplexe Anwendung | HOCH (Werkzeug, DIY) |
| Transformation sichtbar | HOCH (Beauty, Fitness) |
| Groesse/Passform schwer darstellbar | MITTEL (Moebel, Bekleidung) |
| Einfaches Produkt ohne Demo | NIEDRIG (Standardartikel, Bueroartikel) |

Bei NIEDRIG: Video ist optional. Bei HOCH: Pflicht.

---

## Video-Struktur: Die 30-Sekunden-Formel

Ein erfolgreiches Amazon-Listing-Video folgt dieser Struktur:

```
0:00-0:03  HOOK (3 Sekunden)
           → Den Kaeufer fesseln bevor er wegscrollt
           → Zeigt das Problem oder die finale Transformation

0:03-0:10  PROBLEM + PRODUKT (7 Sekunden)
           → "Kennst du das Problem?"
           → Produkt wird eingefuehrt als Loesung

0:10-0:22  DEMO / BENEFITS (12 Sekunden)
           → 3 Schluesselfeatures in Aktion
           → Jedes Feature: Kurze Demonstration + Text-Overlay

0:22-0:27  SOCIAL PROOF / TRUST (5 Sekunden)
           → Bewertungen, Zertifikate, Kunden-Zitate
           → Oder: Vorher-Nachher-Effekt

0:27-0:30  CALL TO ACTION (3 Sekunden)
           → Marke + Produkt-Shot
           → Kein "Kaufen!" — Amazon verbietet das
           → Stattdessen: Hauptbenefit als letzter Eindruck
```

---

## Video-Briefing Output-Format

Der Listing-Briefer erstellt im Briefing einen zusaetzlichen Abschnitt:

```markdown
## Video-Briefing (Slot 8 / Gallery Video)

**Brand Registry:** [Ja/Nein] — nur wenn Ja: Video erstellen
**Empfohlene Prioritaet:** [HOCH / MITTEL / NIEDRIG]
**Ziel-Laenge:** 20-30 Sekunden
**Format:** Quadratisch (1:1) oder Vertikal (9:16) fuer Mobile-first

### Kernbotschaft
[Eine Saetze: Was ist der zentrale Benefit den das Video kommunizieren MUSS]

### Adressierter Painpoint
[Welches Problem des Kaeufers wird geloest — aus review-insights.md]

---

### Szene 1: HOOK (0:00-0:03)

**Visual:** [Beschreibung was zu sehen ist]
**Sound/VO:** [Voice-Over Text oder "Kein VO, nur Sound"]
**Text-Overlay:** [Ja/Nein + Text]
**Zweck:** [Warum dieser Einstieg? Welche Emotion?]

---

### Szene 2: PROBLEM + PRODUKT (0:03-0:10)

**Visual:** [Szene mit Problem, dann Produkt als Loesung]
**Sound/VO:** [Problem-Beschreibung in 1 Satz + Produkt-Intro]
**Text-Overlay:** [z.B. Marke einblenden]
**Zweck:** Identifikation + Loesungsversprechen

---

### Szene 3: DEMO / BENEFITS (0:10-0:22)

**Sub-Szene 3a (0:10-0:14) — Benefit 1:**
- Visual: [Produkt in Aktion, Feature X]
- Text-Overlay: [Benefit in 2-3 Woertern]
- VO: [Kurze Erklaerung]

**Sub-Szene 3b (0:14-0:18) — Benefit 2:**
- Visual: [...]
- Text-Overlay: [...]
- VO: [...]

**Sub-Szene 3c (0:18-0:22) — Benefit 3:**
- Visual: [...]
- Text-Overlay: [...]
- VO: [...]

---

### Szene 4: TRUST (0:22-0:27)

**Visual:** [z.B. Zertifikat-Close-up / Kunde mit Produkt / Vorher-Nachher]
**Text-Overlay:** [z.B. "Oeko-Tex zertifiziert" / "Tausende zufriedene Kunden"]
**VO:** [Kurze Vertrauens-Statement]
**Zweck:** Risiko-Reduktion

---

### Szene 5: CLOSE (0:27-0:30)

**Visual:** [Produkt-Shot + Marke]
**Text-Overlay:** [Marke + Hauptbenefit]
**VO:** [Optional: Marken-Tagline]
**Zweck:** Letzter emotionaler Eindruck

---

### Technische Vorgaben

- **Aufloesung:** 1920x1080 min, 4K empfohlen
- **Format:** MP4 (H.264)
- **Dateigroesse:** Max 500 MB
- **Seitenverhaeltnis:** 1:1 oder 9:16 (Mobile-first)
- **Untertitel:** PFLICHT (80% werden ohne Sound geschaut)
- **Frame Rate:** 30 FPS
- **Audio:** Stereo 48kHz
- **Dauer:** 15-30 Sekunden (nicht laenger)

### Voice-Over Regeln

- **Sprache:** Pro Marktplatz eigene Version (PAN-EU!)
- **Geschwindigkeit:** 150-170 WPM (natuerlich, nicht gehetzt)
- **Sprecher:** Passend zur Zielgruppe (Alter, Geschlecht, Ton)
- **Lautstaerke:** Normalisiert auf -16 LUFS
- **Musik:** Hintergrund max. -20 dB unter VO

### Untertitel-Regeln (PFLICHT)

- Gut lesbar auch auf Mobile (min. 40pt equivalent)
- Hoher Kontrast (weisser Text + schwarzer Schatten)
- Untere Bildhaelfte, mittig
- Max. 2 Zeilen gleichzeitig
- Zeigen was der Sprecher sagt (nicht nur Key-Words)

### Amazon Compliance

**Verboten:**
- Preise nennen oder zeigen
- "Jetzt kaufen!"-Aufrufe
- Wettbewerber-Markennamen
- Medizinische Heilsversprechen
- Kinder unter 13 als Hauptfokus
- Urheberrechtlich geschuetzte Musik ohne Lizenz

**Erlaubt:**
- Produkt-Demo
- Kunden-Testimonials (mit Einverstaendnis)
- Lizenzfreie oder lizenzierte Musik
- Text-Overlays mit Benefits
```

---

## Kategorie-spezifische Anpassungen

### Socken (wenn `kategorie-textil-socken` aktiv)

**Ideale Video-Szenen:**
- Nahaufnahme Material (Strick, Merino-Struktur)
- Tragebild — Fuss im Schuh in Bewegung (Laufen, Wandern)
- Stretch-Test (Socke wird auseinandergezogen)
- Vergleich: Wasser perlt ab bei atmungsaktiver Socke
- Wander-/Sport-Szene in Natur
- Waschmaschinen-Szene (Haltbarkeit)

**Key Benefits fuer Socken-Video:**
1. Material / Tragekomfort
2. Passform / Anti-Rutsch
3. Haltbarkeit / Geruchshemmung

**Dauer-Empfehlung:** 20 Sekunden (einfache Produkte)

---

## Prioritaets-Matrix

Wenn der Kunde begrenztes Video-Budget hat, diese Reihenfolge empfehlen:

| Prioritaet | Video-Typ | Aufwand | Erwarteter CVR-Lift |
|---|---|---|---|
| 1 | Einfache Produkt-Demo (30 Sek) | Niedrig | +9-12% |
| 2 | Lifestyle-Szenario (30 Sek) | Mittel | +12-15% |
| 3 | Premium Markengeschichte (45-60 Sek) | Hoch | +10-13% (bei Premium-Produkten) |

**Empfehlung fuer Erst-Listings:** Start mit Prioritaet 1, Upgrade wenn Listing etabliert ist.
