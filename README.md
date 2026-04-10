# NetzSicht Listing Pipeline

3-Agent-Pipeline fuer Amazon-Produktlisting Bild-Briefings. Laeuft auf [paperclip.ing](https://paperclip.ing).

## Architektur

```
                          ┌─────────────────────┐
                          │   Neuer Task:        │
                          │   ASIN / Produktinfo │
                          └─────────┬───────────┘
                                    │
                                    v
                     ┌──────────────────────────┐
                     │   PRODUKT-ANALYST         │
                     │   Sonnet 4.6              │
                     │   Sammelt & strukturiert   │
                     └─────────┬────────────────┘
                               │ produkt-analyse.md
                               v
                     ┌──────────────────────────┐
                     │   LISTING-BRIEFER         │
                     │   Opus 4.6                │
                     │   Slot-fuer-Slot Briefing  │
                     └─────────┬────────────────┘
                               │ listing-briefing.md
                               v
                     ┌──────────────────────────┐
                     │   QUALITY-REVIEWER        │
                     │   Sonnet 4.6              │
                     │   7-Dimensionen-Check      │
                     └─────────┬────────────────┘
                               │ review-ergebnis.md
                               v
                  ┌────────────┼────────────┐
                  v            v            v
             APPROVED    REVISION       ABGELEHNT
            -> Designer  -> Briefer     -> Analyst
```

## Agents

| Slug | Title | Model | Input | Output |
|---|---|---|---|---|
| `produkt-analyst` | Product Research Analyst | Sonnet 4.6 | ASIN / Produktinfo | `produkt-analyse.md` |
| `listing-briefer` | Creative Strategist | Opus 4.6 | `produkt-analyse.md` | `listing-briefing.md` |
| `quality-reviewer` | Quality Assurance | Sonnet 4.6 | Briefing + Analyse | `review-ergebnis.md` |

## Verzeichnisstruktur

```
netzsicht-listing-pipeline/
│
├── .paperclip.yaml                        <- paperclip.ing Schema & Config
├── COMPANY.md                             <- Company Definition & Goals
├── README.md                              <- Du bist hier
│
├── agents/
│   ├── produkt-analyst/
│   │   ├── AGENTS.md                      <- Entry (Rolle, Pipeline, Handoff)
│   │   ├── SOUL.md                        <- Identitaet & Prinzipien
│   │   ├── HEARTBEAT.md                   <- Ausfuehrungs-Checklist (9 Phasen)
│   │   ├── TOOLS.md                       <- Dateizugriff & Ressourcen
│   │   └── skills/
│   │       ├── produkt-analyse-interface.md
│   │       └── amazon-kategorien.md
│   │
│   ├── listing-briefer/
│   │   ├── AGENTS.md                      <- Entry (Rolle, Pipeline, Handoff)
│   │   ├── SOUL.md                        <- Identitaet & Neuromarketing
│   │   ├── HEARTBEAT.md                   <- Ausfuehrungs-Checklist (7 Steps)
│   │   ├── TOOLS.md                       <- Dateizugriff & Ressourcen
│   │   └── skills/
│   │       ├── slot-framework.md
│   │       ├── compliance-checkliste.md
│   │       ├── kategorie-adaptionen.md
│   │       └── briefing-template.md
│   │
│   └── quality-reviewer/
│       ├── AGENTS.md                      <- Entry (Rolle, Routing, Verdicts)
│       ├── SOUL.md                        <- Identitaet & Review-Prinzipien
│       ├── HEARTBEAT.md                   <- Ausfuehrungs-Checklist (7 Dimensionen)
│       ├── TOOLS.md                       <- Dateizugriff & Ressourcen
│       └── skills/
│           ├── amazon-compliance.md
│           ├── kategorie-regeln.md
│           └── review-interface.md
│
├── teams/
│   └── listing-pipeline/
│       └── TEAM.md                        <- Team-Definition (alle 3 Agents)
│
├── pipeline/
│   ├── agents.yaml                        <- Agent-Konfigurationen (Modelle, Prompts)
│   └── interfaces.md                      <- Datenvertraege: Interface A, B, C
│
├── content/                               <- Wissensbasis (Deep Research Reports)
│   ├── deep-research-report_ChatGPT.md
│   ├── deep-research-report_Claude.md
│   └── deep-research-report_Gemini.md
│
└── workspace/                             <- Laufzeit-Outputs pro Task
    └── {task-id}/
        ├── produkt-analyse.md
        ├── listing-briefing.md
        └── review-ergebnis.md
```

## Setup

1. **Company importieren:** `npx paperclipai company import` oder manuell anlegen
2. **Agents erstellen** — 3 Agents mit den Slugs `produkt-analyst`, `listing-briefer`, `quality-reviewer`
3. **Instruction Files hochladen** — Pro Agent die 4 Files (AGENTS.md als ENTRY, SOUL.md, HEARTBEAT.md, TOOLS.md)
4. **Skills anhaengen** — Pro Agent die `skills/*.md` Dateien ueber den Skills-Tab zuweisen:

| Agent | Skills |
|---|---|
| `produkt-analyst` | `produkt-analyse-interface`, `amazon-kategorien` |
| `listing-briefer` | `7-slot-framework`, `amazon-compliance`, `kategorie-adaptionen`, `briefing-template` |
| `quality-reviewer` | `amazon-compliance`, `kategorie-regeln`, `review-interface` |

5. **Modelle zuweisen** — Analyst & Reviewer: Sonnet 4.6 / Briefer: Opus 4.6
6. **Erster Task** — Issue erstellen, dem `produkt-analyst` zuweisen

## Feedback-Loop

- **APPROVED** → Briefing geht an Designer
- **REVISION_NOETIG** → Zurueck an Listing-Briefer mit konkreten Fixes
- **ABGELEHNT** → Zurueck an Produkt-Analyst (Daten unzureichend)

## Wissensbasis

Konsolidiert aus 3 Deep Research Reports:
- Amazon Bild-Richtlinien & Compliance (Stand 2026)
- 7-Slot-Framework mit Conversion-Daten & Neuromarketing
- Kategorie-spezifische Adaptionen
- A+ Content Strategie & KI-Bildgenerierung
