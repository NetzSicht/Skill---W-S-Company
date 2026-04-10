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
├── agents/
│   ├── ceo/                    (AGENTS, SOUL, HEARTBEAT, TOOLS)
│   ├── produkt-analyst/        (+ skills/)
│   ├── listing-briefer/        (+ skills/)
│   ├── quality-reviewer/       (+ skills/)
│   ├── content-master/         (+ skills/)
│   ├── ppc-specialist/         (+ skills/)
│   ├── keyword-researcher/     (+ skills/)
│   ├── review-analyst/         (+ skills/)
│   └── aplus-content-designer/ (+ skills/)
│
├── teams/
│   ├── listing-pipeline/       Bild-Pipeline (3 agents)
│   ├── text-pipeline/          Text-Pipeline (1 agent)
│   ├── ads-pipeline/           Ads-Pipeline (1 agent)
│   ├── research/               Research (2 agents)
│   └── aplus-content/          A+ Content (1 agent)
│
├── pipeline/
│   ├── agents.yaml             Agent-Konfigurationen
│   └── interfaces.md           Datenvertraege zwischen Agents
│
├── content/                    Deep Research Reports (Wissensbasis)
└── workspace/                  Laufzeit-Outputs pro Task
```

## Setup (paperclip.ing)

1. **Agents anlegen** — 9 Agents mit den Slugs aus der Tabelle oben
2. **Instruction Files** — Pro Agent: AGENTS.md (ENTRY), SOUL.md, HEARTBEAT.md, TOOLS.md
3. **Skills anhaengen** — `skills/*.md` ueber den Skills-Tab zuweisen
4. **Modelle zuweisen** — Kreative Agents (Briefer, Content Master, A+ Designer): Opus 4.6 / Rest: Sonnet 4.6
5. **Erster Task** — Issue an CEO mit Client-Brief oder ASIN
