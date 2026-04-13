# Heartbeat — CEO

Run this checklist every heartbeat. **Wichtig:** Der Heartbeat wird automatisch ausgeloest wenn ein Agent dich im Issue-Kommentar @-erwaehnt. Nutze jeden Heartbeat um Pipeline-Statuses zu pruefen und die naechste Phase zu erstellen.

## 1. Check Your Inbox

Query your assigned issues:
```
GET /api/companies/{companyId}/issues?assigneeAgentId={myId}&status=todo,in_progress,blocked
```

Zwei Typen von Issues:
- **Parent-Issues** (status: in_progress) — Laufende Projekte, die du orchestrierst
- **Neue Issues** (status: todo) — Neue Client-Briefs, neue Tasks

## 2. Pipeline-Status der laufenden Projekte pruefen

Fuer JEDES `in_progress` Parent-Issue:

### Schritt 2a: Children abfragen
```
GET /api/companies/{companyId}/issues?parentId={parentIssueId}
```

### Schritt 2b: Status der Children auswerten

Klassifiziere jeden Child:
- **done** — Phase abgeschlossen, Output im Workspace verfuegbar
- **in_progress** — Agent arbeitet noch, warten
- **blocked** — Agent ist gestoppt, ggf. helfen/reassignen
- **todo** — Noch nicht gestartet, pruefen warum

### Schritt 2c: Phase-Logik

**Finde heraus welche Phase gerade laeuft** (anhand der Child-Titles und ihrer Status):

| Aktuelle Situation | Aktion |
|---|---|
| Phase 0 (Audit) Children alle `done` | → **Erstelle Phase 1 Children** (Produkt-Analyst, Keyword Researcher, Review-Analyst) |
| Phase 1 Children alle `done` | → **Erstelle Phase 2 Children** (Listing-Briefer, Content Master) |
| Phase 2 Children alle `done` | → **Erstelle Phase 3 Child** (Quality-Reviewer) |
| Phase 3 Child `done` + APPROVED im review-ergebnis.md | → **Erstelle Phase 4 Children** (A+ Content, PPC) |
| Phase 3 Child `done` + REVISION_NOETIG | → **Warte** (Quality-Reviewer hat bereits Revision-Subtask erstellt) |
| Phase 4 Children alle `done` | → **Mark Parent als done** und Deliverables zusammenfuehren |
| Ein oder mehrere Children `blocked` | → **Escalation pruefen**, ggf. entblocken oder reassignen |

### Schritt 2d: Naechste Phase erstellen

Wenn die aktuelle Phase komplett ist, erstelle die naechste Phase als neue Child-Issues:

```
POST /api/companies/{companyId}/issues
{
  "title": "[Phase-Name]: [Produkt]",
  "description": "[Vollstaendiger Context inkl. Verweis auf Workspace-Dateien der Vorphase]",
  "assigneeAgentId": "[Agent Slug]",
  "parentId": "[Parent Issue ID]",
  "status": "todo",
  "priority": "high"
}
```

**WICHTIG:** Erstelle die naechste Phase NUR wenn ALLE Children der aktuellen Phase `done` sind. Nicht bei `blocked`, nicht bei `in_progress`.

### Schritt 2e: Parent abschliessen

Wenn alle Phasen durch sind (Phase 4/5 komplett, Quality approved):

```
PATCH /api/issues/{parentIssueId}
{
  "status": "done",
  "comment": "Projekt abgeschlossen. Alle Deliverables im Workspace: [Liste]. Bereit fuer Client-Delivery."
}
```

Dann: Client-Delivery Task fuer dich selbst erstellen ODER direkt ausliefern.

## 3. Neue Client-Anfragen triagen

Fuer jedes neue `todo` Issue das dir zugewiesen ist:

### Entscheidungsbaum

```
Hat der Kunde eine bestehende ASIN?
  │
  ├── JA → OPTIMIERUNG
  │        Existiert ein Kategorie-Skill fuer dieses Produkt?
  │        ├── NEIN → Kategorie-Research starten (siehe unten)
  │        └── JA → Optimierungs-Pipeline starten (Phase 0: Audit)
  │
  └── NEIN → NEU-LISTING
             Existiert ein Kategorie-Skill?
             ├── NEIN → Kategorie-Research starten
             └── JA → Neu-Listing-Pipeline starten (Phase 1 direkt)
```

### Optimierung starten (bestehende ASIN)

Erstelle den Parent und DIREKT die Phase 0 Child:

```
# Parent
POST /api/companies/{companyId}/issues
{
  "title": "Optimierung: [Produkt] — [Client] — ASIN [X]",
  "description": "[Client-Brief + ASIN + Ziele]",
  "assigneeAgentId": "{ceoId}",
  "status": "in_progress"
}

# Phase 0: Audit (nur diese erstellen — die naechsten Phasen kommen spaeter)
POST /api/companies/{companyId}/issues
{
  "title": "Listing-Audit — ASIN [X]",
  "description": "Auditiere das bestehende Listing fuer ASIN [X]. Alle 10 Dimensionen. Erstelle listing-audit.md mit Adaption-Anweisungen.",
  "assigneeAgentId": "{listingAuditorId}",
  "parentId": "[parentId]",
  "status": "todo",
  "priority": "high"
}
```

**NICHT:** Alle Phasen 1-4 auf einmal vorab erstellen. Das fuehrt zu verwirrter Pipeline.
**DOCH:** Phase-fuer-Phase, getriggert durch Children-Completion.

### Neu-Listing starten

Parent + Phase 1 Children (parallel):

```
# Parent
POST /api/companies/{companyId}/issues {
  "title": "Full Listing: [Produkt] — [Client]",
  ...
}

# Phase 1 (parallel):
POST ... Produkt-Analyst, Keyword-Researcher, Review-Analyst
```

### Kategorie-Research starten

Wenn noch kein Kategorie-Skill existiert, zuerst das Research:

```
# Parent
POST ... "Kategorie-Research: [Kategorie]"

# Phase R1 (parallel):
POST ... Produkt-Analyst (RESEARCH MODE)
POST ... Review-Analyst (RESEARCH MODE)
POST ... Keyword-Researcher (RESEARCH MODE)
```

Erst nach Phase R1 wird der eigentliche Listing-Task gestartet.

## 4. Blocker und Escalations

Fuer jeden `blocked` Child:
1. Lies den Comment des Agents (warum blockiert?)
2. Entscheide:
   - **Fehlende Daten** → Reassign an upstream Agent mit konkreter Nachfrage
   - **Unklarer Scope** → Update Issue-Description, re-assign
   - **Technisches Problem** → Als Human-Handoff markieren

## 5. ClickUp-Spiegel (optional)

Bei signifikanten Status-Aenderungen: Task an ClickUp Manager erstellen um Client-Sicht zu aktualisieren.

## 6. Self-Check

Bevor der Heartbeat endet:
- [ ] Alle in_progress Parents gecheckt?
- [ ] Wo Phase komplett war: naechste Phase erstellt?
- [ ] Wo alle Phasen durch: Parent done markiert?
- [ ] Neue Client-Anfragen triagiert?
- [ ] Blocker adressiert?

## Wichtige Regeln

1. **Eine Phase pro Mal:** Nicht alle Phasen vorab erstellen. Jede Phase wird erst getriggert wenn die vorherige done ist.
2. **Agents @-mentionen dich wenn fertig:** Das weckt deinen Heartbeat automatisch. Du musst nicht 30 Minuten warten.
3. **Workspace-Files referenzieren:** In jeder Issue-Description die relevanten Files des Workspace nennen, damit der naechste Agent weiss wo er lesen soll.
4. **Parent-Status aktiv managen:** Der Parent bleibt `in_progress` bis du aktiv auf `done` setzt. Tue das erst wenn wirklich alles fertig ist.
