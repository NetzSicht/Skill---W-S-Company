---
name: NetzSicht Listing Pipeline
description: 3-Agent-Pipeline fuer Amazon-Produktlisting Bild-Briefings. Analysiert Produkte, erstellt Slot-fuer-Slot Designer-Briefings und prueft gegen Amazon-Compliance. Output sind umsetzungsfertige Briefing-Dokumente fuer Grafiker und KI-Bilder-Experten.
slug: netzsicht-listing-pipeline
schema: agentcompanies/v1
version: 1.0.0
license: MIT
authors:
  - name: NetzSicht (Moritz)
goals:
  - Konsistente, datengestuetzte Bild-Briefings fuer Amazon-Listings erstellen
  - Conversion-Rate durch psychologisch optimierte Bildstrategie maximieren
  - Amazon-Compliance in jedem Briefing sicherstellen
  - Briefing-Erstellung von Stunden auf Minuten reduzieren
---

# NetzSicht Listing Pipeline

Eine spezialisierte 3-Agent-Pipeline die Amazon-Produktdaten in umsetzungsfertige Bild-Briefings verwandelt.

## How It Works

1. Ein neuer Task wird mit einer ASIN oder Produktbeschreibung erstellt
2. Der **Produkt-Analyst** sammelt und strukturiert alle relevanten Daten
3. Der **Listing-Briefer** erstellt daraus ein Slot-fuer-Slot Bild-Briefing
4. Der **Quality-Reviewer** prueft gegen 7 Qualitaets-Dimensionen
5. Bei APPROVED geht das Briefing an den Designer — bei REVISION zurueck in die Pipeline

## Pipeline

| Agent | Title | Reports To | Model |
|---|---|---|---|
| `produkt-analyst` | Product Research Analyst | — | Sonnet 4.6 |
| `listing-briefer` | Creative Strategist | — | Opus 4.6 |
| `quality-reviewer` | Quality Assurance | — | Sonnet 4.6 |

## Team

| Team | Agents | Purpose |
|---|---|---|
| `listing-pipeline` | 3 | End-to-end Bild-Briefing Erstellung |

## Wissensbasis

Das Framework basiert auf drei unabhaengigen Deep Research Reports (ChatGPT, Claude, Gemini) und konsolidiert:
- Amazon Bild-Richtlinien & Compliance (Stand 2026)
- 7-Slot-Framework mit Conversion-Daten und Neuromarketing-Prinzipien
- Kategorie-spezifische Adaptionen (Supplements, Elektronik, Textil, Beauty, Moebel, Food)
- A/B-Testing Methodik und KPI-Benchmarks
