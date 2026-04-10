---
name: NetzSicht
description: Amazon Marketing Agency mit 10 spezialisierten AI Agents. Full-Service Listing-Optimierung — von Produktanalyse ueber Bild-Briefings und Listing-Texte bis zu PPC-Kampagnen und A+ Content.
slug: netzsicht
schema: agentcompanies/v1
version: 2.0.0
license: MIT
authors:
  - name: NetzSicht (Moritz)
goals:
  - Full-Service Amazon Listing-Optimierung mit konsistenter Qualitaet liefern
  - Conversion-Rate durch datengestuetzte Bild- und Text-Strategien maximieren
  - Amazon-Compliance in jedem Deliverable sicherstellen
  - Durchlaufzeit von Listing-Projekten von Tagen auf Stunden reduzieren
  - Skalierbar arbeiten — 9 spezialisierte Agents statt 1 Generalist
---

# NetzSicht — Amazon Marketing Agency

Full-Service Amazon Listing-Optimierung mit 9 spezialisierten AI Agents, orchestriert ueber paperclip.ing.

## How It Works

1. CEO empfaengt Client-Brief und erstellt Tasks fuer die richtigen Agents
2. **Phase 1 (parallel):** Produkt-Analyst + Keyword Researcher + Review-Analyst sammeln Daten
3. **Phase 2 (parallel):** Listing-Briefer erstellt Bild-Briefing, Content Master schreibt Texte
4. **Phase 3:** Quality-Reviewer prueft alles
5. **Phase 4:** A+ Content Designer erstellt Enhanced Content
6. **Phase 5:** PPC Specialist baut Kampagnen
7. CEO liefert das Gesamtpaket an den Client

## Organization

```
                              CEO
                               |
           ┌───────────┬───────┼────────┬──────────┐
           |           |       |        |          |
     Bild-Pipeline  Text-Pipe  Ads   Research    A+ Content  Ops
      ┌────┼────┐      |       |     ┌──┼──┐       |          |
      |    |    |      |       |     |     |       |          |
    Prod. List. Qual. Cont.  PPC   Keyw. Rev.   A+Cont.   ClickUp
    Anal. Brief Rev.  Mast.  Spec. Res.  Anal.  Des.      Mgr.
```

## Agents

| Slug | Title | Reports To | Team | Model |
|---|---|---|---|---|
| `ceo` | CEO | — | — | Opus 4.6 |
| `produkt-analyst` | Product Research Analyst | CEO | Bild-Pipeline | Sonnet 4.6 |
| `listing-briefer` | Creative Strategist | CEO | Bild-Pipeline | Opus 4.6 |
| `quality-reviewer` | Quality Assurance | CEO | Bild-Pipeline | Sonnet 4.6 |
| `content-master` | Content Master — Copywriting | CEO | Text-Pipeline | Opus 4.6 |
| `ppc-specialist` | PPC Specialist | CEO | Ads-Pipeline | Sonnet 4.6 |
| `keyword-researcher` | Keyword Researcher | CEO | Research | Sonnet 4.6 |
| `review-analyst` | Review-Analyst | CEO | Research | Sonnet 4.6 |
| `aplus-content-designer` | A+ Content Designer | CEO | A+ Content | Opus 4.6 |
| `clickup-manager` | PM — ClickUp Task Manager | CEO | Operations | Sonnet 4.6 |

## Teams

| Team | Agents | Purpose |
|---|---|---|
| `bild-pipeline` | 3 | Produktanalyse → Bild-Briefing → Quality Review |
| `text-pipeline` | 1 | Amazon Listing-Texte (Titel, Bullets, Description, Backend) |
| `ads-pipeline` | 1 | PPC Kampagnen (SP, SB, SD) |
| `research` | 2 | Keyword-Strategien + Review-Intelligence |
| `aplus-content` | 1 | A+ Content und Brand Story Briefings |
| `operations` | 1 | ClickUp Task Management, Pipeline Tracking |
