# NetzSicht — Amazon Marketing Agency

Full-Service Amazon Listing-Optimierung mit 9 spezialisierten AI Agents. Laeuft auf [paperclip.ing](https://paperclip.ing).

## Architektur

```
                                    CEO
                                     |
              ┌──────────┬───────────┼───────────┬──────────┐
              |          |           |           |          |
        Bild-Pipeline  Text-Pipe   Ads      Research    A+ Content
         ┌────┼────┐     |          |       ┌───┼───┐      |
         |    |    |     |          |       |       |      |
       Prod. List. Qual. Cont.    PPC    Keyw.   Rev.   A+Cont.
       Anal. Brief Rev.  Mast.   Spec.   Res.   Anal.   Des.
```

## Agents

| Slug | Title | Team | Model |
|---|---|---|---|
| `ceo` | CEO | — | Opus 4.6 |
| `produkt-analyst` | Product Research Analyst | Bild-Pipeline | Sonnet 4.6 |
| `listing-briefer` | Creative Strategist | Bild-Pipeline | Opus 4.6 |
| `quality-reviewer` | Quality Assurance | Bild-Pipeline | Sonnet 4.6 |
| `content-master` | Content Master — Copywriting | Text-Pipeline | Opus 4.6 |
| `ppc-specialist` | PPC Specialist | Ads-Pipeline | Sonnet 4.6 |
| `keyword-researcher` | Keyword Researcher | Research | Sonnet 4.6 |
| `review-analyst` | Review-Analyst | Research | Sonnet 4.6 |
| `aplus-content-designer` | A+ Content Designer | A+ Content | Opus 4.6 |

## Full Listing Pipeline

```
Phase 1 (parallel — Datensammlung):
  Produkt-Analyst ────────┐
  Keyword Researcher ─────┤── feeds Phase 2
  Review-Analyst ─────────┘

Phase 2 (parallel — Content-Erstellung):
  Listing-Briefer (Bilder) ──┐
  Content Master (Texte) ────┤── feeds Phase 3

Phase 3 (Quality Gate):
  Quality-Reviewer ──── APPROVED / REVISION / ABGELEHNT

Phase 4 (nach Approval):
  A+ Content Designer
  PPC Specialist

Phase 5:
  CEO → Client Delivery
```

## Teams

| Team | Slug | Agents | Purpose |
|---|---|---|---|
| Bild-Pipeline | `bild-pipeline` | 3 | Produktanalyse → Bild-Briefing → Quality Review |
| Text-Pipeline | `text-pipeline` | 1 | Listing-Texte (Titel, Bullets, Backend) |
| Ads-Pipeline | `ads-pipeline` | 1 | PPC Kampagnen (SP, SB, SD) |
| Research | `research` | 2 | Keyword-Strategien + Review-Intelligence |
| A+ Content | `aplus-content` | 1 | Enhanced Brand Content Briefings |

## Verzeichnisstruktur

```
netzsicht/
├── .paperclip.yaml
├── COMPANY.md
├── README.md
│
├── agents/                            Instruction Files (4 pro Agent)
│   ├── ceo/                           AGENTS.md, SOUL.md, HEARTBEAT.md, TOOLS.md
│   ├── produkt-analyst/
│   ├── listing-briefer/
│   ├── quality-reviewer/
│   ├── content-master/
│   ├── ppc-specialist/
│   ├── keyword-researcher/
│   ├── review-analyst/
│   ├── aplus-content-designer/
│   └── clickup-manager/
│
├── skills/                            Company-Level Skills (SKILL.md pro Skill)
│   ├── 7-slot-framework/              Conversion-Daten, Neuromarketing, AIDA
│   ├── amazon-compliance/             Amazon Bild-Richtlinien & Checkliste
│   ├── amazon-kategorien/             Kategorie-spezifische Analyseschwerpunkte
│   ├── briefing-template/             Output-Format + Beispiel
│   ├── kategorie-adaptionen/          Slot-Anpassungen pro Kategorie
│   ├── kategorie-regeln/              Kategorie-Anforderungen (Review-Basis)
│   ├── produkt-analyse-interface/     Output-Schema Interface A
│   └── review-interface/              Output-Schema Interface C
│
├── teams/
│   ├── listing-pipeline/              Bild-Pipeline (3 agents)
│   ├── text-pipeline/                 Text-Pipeline (1 agent)
│   ├── ads-pipeline/                  Ads-Pipeline (1 agent)
│   ├── research/                      Research (2 agents)
│   └── aplus-content/                 A+ Content (1 agent)
│
├── pipeline/
│   ├── agents.yaml                    Agent-Konfigurationen
│   └── interfaces.md                  Datenvertraege zwischen Agents
│
├── content/                           Deep Research Reports (Wissensbasis)
└── workspace/                         Laufzeit-Outputs pro Task
```

## Setup (paperclip.ing)

1. **Agents anlegen** — 10 Agents mit den Slugs aus der Tabelle oben
2. **Instruction Files** — Pro Agent: AGENTS.md (ENTRY), SOUL.md, HEARTBEAT.md, TOOLS.md hochladen
3. **Skills importieren** — Die `skills/*/SKILL.md` Dateien werden als Company Skills geladen. Jeder Agent waehlt per Checkbox welche Skills er nutzt:

| Agent | Skills (per Checkbox aktivieren) |
|---|---|
| `produkt-analyst` | produkt-analyse-interface, amazon-kategorien |
| `listing-briefer` | 7-slot-framework, amazon-compliance, kategorie-adaptionen, briefing-template |
| `quality-reviewer` | amazon-compliance, kategorie-regeln, review-interface |
| `content-master` | (eigene Skills folgen) |
| `ppc-specialist` | (eigene Skills folgen) |
| `keyword-researcher` | (eigene Skills folgen) |
| `review-analyst` | (eigene Skills folgen) |
| `aplus-content-designer` | (eigene Skills folgen) |
| `clickup-manager` | ClickUp Automation (extern) |

4. **Modelle zuweisen** — Kreative Agents (CEO, Briefer, Content Master, A+ Designer): Opus 4.6 / Rest: Sonnet 4.6
5. **Erster Task** — Issue an CEO mit Client-Brief oder ASIN
