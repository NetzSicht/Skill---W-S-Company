# Heartbeat — CEO

**WICHTIG: Dies ist dein Ausfuehrungs-Protokoll. Jeder Heartbeat MUSS diese Schritte in exakt dieser Reihenfolge ausfuehren. Keine Ausnahmen.**

---

## Schritt 1 (PFLICHT): Alle in_progress Parent-Issues durchgehen

**Dies ist immer der erste Schritt. Egal ob du gerade durch eine @-mention geweckt wurdest oder durch Heartbeat-Timer.**

### 1.1 Alle laufenden Parents holen

```
GET /api/companies/{companyId}/issues?assigneeAgentId={myId}&status=in_progress
```

Du bekommst eine Liste aller Projekte die gerade laufen.

### 1.2 Fuer JEDES Parent die Children durchgehen

Fuer jeden Parent in der Liste:

```
GET /api/companies/{companyId}/issues?parentId={parentIssueId}
```

### 1.3 Children nach Phase gruppieren und Status zaehlen

Pro Parent ermitteln:

- **Welche Phase laeuft aktuell?** (anhand der Issue-Titel: "Phase 0: Audit", "Phase 1: Analyse", etc.)
- **Wie viele Children in dieser Phase?**
- **Wie viele sind `done`?**
- **Wie viele sind `in_progress`?**
- **Wie viele sind `blocked`?**

### 1.4 Die Entscheidungs-Tabelle

Fuer jeden Parent durchgehen:

| Situation | Aktion — JETZT in diesem Heartbeat |
|---|---|
| Alle Children der aktuellen Phase `done` **und** naechste Phase existiert noch nicht | **SOFORT** naechste Phase-Children erstellen |
| Alle Children aller Phasen `done` (Projekt vollstaendig) | **SOFORT** Parent als `done` markieren + Client Delivery vorbereiten |
| Mindestens 1 Child `in_progress` | Nichts tun — warten auf Agent-Completion (naechster Heartbeat wird triggered) |
| Mindestens 1 Child `blocked` | Blocker-Resolution (Schritt 4) |
| Keine Children vorhanden obwohl Parent in_progress | Pipeline wurde nicht gestartet — Phase 1 jetzt starten |

**KRITISCHE REGEL:** Wenn die aktuelle Phase komplett `done` ist, erstellst du in DIESEM Heartbeat die naechste Phase. Nicht "naechstes Mal". Nicht "sobald ich Zeit habe". **JETZT.**

### 1.5 Beispiel-Durchlauf

```
Parent "Full Listing: Coolmax Wandersocken" (NETAAA-2, in_progress)
  |
  GET /api/companies/{id}/issues?parentId=NETAAA-2
  |
  Children:
    - NETAAA-2a "Phase 0: Audit" → done ✓
    - NETAAA-3 "Phase 1: Produktanalyse" → done ✓
    - NETAAA-4 "Phase 1: Keyword Research" → done ✓
    - NETAAA-5 "Phase 1: Review-Analyse" → done ✓
  
  Phase 1 Status: 3/3 done
  Phase 2 existiert: NEIN
  
  → AKTION: Erstelle Phase 2 Children JETZT:
    - "Phase 2: Bild-Briefing" → Listing-Briefer
    - "Phase 2: Listing-Texte" → Content Master
```

---

## Schritt 2: Phase-Erstellung (die API-Calls)

Wenn Schritt 1.4 sagt "naechste Phase erstellen", hier die konkreten Calls:

### Von Phase 0 (Audit) → Phase 1

```
POST /api/companies/{companyId}/issues
{
  "title": "Phase 1: Produktanalyse — [Produkt]",
  "description": "Lies listing-audit.md im Workspace und arbeite adaptiv. FOKUS: [was Auditor als FOKUS markiert hat]. SKIP: [was Auditor als SKIP markiert hat].",
  "assigneeAgentId": "[produkt-analyst-id]",
  "parentId": "{parentIssueId}",
  "status": "todo",
  "priority": "high"
}

POST /api/companies/{companyId}/issues
{
  "title": "Phase 1: Keyword Research — [Produkt]",
  "description": "Keyword-Strategie fuer [Hauptkeyword]. Berücksichtige Audit-Befunde.",
  "assigneeAgentId": "[keyword-researcher-id]",
  "parentId": "{parentIssueId}",
  "status": "todo",
  "priority": "high"
}

POST /api/companies/{companyId}/issues
{
  "title": "Phase 1: Review-Analyse — [Produkt]",
  "description": "Review-Analyse inkl. Search-Painpoint-Extraktion per Solution-Statements.",
  "assigneeAgentId": "[review-analyst-id]",
  "parentId": "{parentIssueId}",
  "status": "todo",
  "priority": "high"
}
```

### Von Phase 1 → Phase 2

```
POST /api/companies/{companyId}/issues
{
  "title": "Phase 2: Bild-Briefing — [Produkt]",
  "description": "Erstelle Slot-fuer-Slot Briefing. Inputs im Workspace: produkt-analyse.md, keyword-strategie.md, review-insights.md, listing-audit.md (falls Optimierung).",
  "assigneeAgentId": "[listing-briefer-id]",
  "parentId": "{parentIssueId}",
  "status": "todo",
  "priority": "high"
}

POST /api/companies/{companyId}/issues
{
  "title": "Phase 2: Listing-Texte — [Produkt]",
  "description": "Titel, Bullets, Backend-Keywords. Inputs im Workspace: produkt-analyse.md, keyword-strategie.md, review-insights.md, listing-briefing.md.",
  "assigneeAgentId": "[content-master-id]",
  "parentId": "{parentIssueId}",
  "status": "todo",
  "priority": "high"
}
```

### Von Phase 2 → Phase 3

```
POST /api/companies/{companyId}/issues
{
  "title": "Phase 3: Quality Review — [Produkt]",
  "description": "Pruefe listing-briefing.md und listing-texte.md gegen alle 9 Dimensionen. Inputs: alle Workspace-Files.",
  "assigneeAgentId": "[quality-reviewer-id]",
  "parentId": "{parentIssueId}",
  "status": "todo",
  "priority": "high"
}
```

### Von Phase 3 (APPROVED) → Phase 4

```
POST /api/companies/{companyId}/issues
{
  "title": "Phase 4: A+ Content Briefing — [Produkt]",
  "description": "Erstelle A+ Content Briefing basierend auf approved listing-briefing.md und listing-texte.md.",
  "assigneeAgentId": "[aplus-content-designer-id]",
  "parentId": "{parentIssueId}",
  "status": "todo",
  "priority": "high"
}

POST /api/companies/{companyId}/issues
{
  "title": "Phase 4: PPC Kampagne — [Produkt]",
  "description": "PPC-Strategie basierend auf keyword-strategie.md und approved listings.",
  "assigneeAgentId": "[ppc-specialist-id]",
  "parentId": "{parentIssueId}",
  "status": "todo",
  "priority": "high"
}
```

### Von Phase 4 → Projekt abschliessen

```
PATCH /api/issues/{parentIssueId}
{
  "status": "done",
  "comment": "Projekt abgeschlossen. Alle Deliverables im Workspace: listing-audit.md (falls Optimierung), produkt-analyse.md, keyword-strategie.md, review-insights.md, listing-briefing.md, listing-texte.md, review-ergebnis.md, aplus-briefing.md, ppc-strategie.md. Bereit fuer Client-Delivery."
}
```

---

## Schritt 3: Neue Client-Anfragen triagen

Nach Pipeline-Check: pruefe auch deine `todo` Issues (neue Anfragen).

```
GET /api/companies/{companyId}/issues?assigneeAgentId={myId}&status=todo
```

Fuer jedes neue todo Issue: Entscheide Optimization vs. Neu-Listing, erstelle Parent-Issue und starte Phase 0 (bei Optimierung) oder Phase 1 (bei Neu-Listing).

### Entscheidungsbaum

```
Hat der Kunde eine bestehende ASIN?
  │
  ├── JA → OPTIMIERUNG
  │        Existiert ein Kategorie-Skill?
  │        ├── NEIN → Kategorie-Research starten zuerst
  │        └── JA → Parent + Phase 0 (Audit) erstellen
  │
  └── NEIN → NEU-LISTING
             Existiert ein Kategorie-Skill?
             ├── NEIN → Kategorie-Research starten zuerst
             └── JA → Parent + Phase 1 (parallel) erstellen
```

### Optimierung starten

```
# Parent
POST /api/companies/{companyId}/issues
{
  "title": "Optimierung: [Produkt] — [Client] — ASIN [X]",
  "description": "[Client-Brief + ASIN + Ziele]",
  "assigneeAgentId": "{myId}",
  "status": "in_progress"
}

# Phase 0
POST /api/companies/{companyId}/issues
{
  "title": "Phase 0: Listing-Audit — ASIN [X]",
  "description": "Auditiere Listing. Alle 10 Dimensionen. Erstelle listing-audit.md.",
  "assigneeAgentId": "[listing-auditor-id]",
  "parentId": "[parentId]",
  "status": "todo",
  "priority": "high"
}
```

### Neu-Listing starten

```
# Parent
POST /api/companies/{companyId}/issues { "title": "Full Listing: [Produkt]", ... }

# Phase 1 (parallel — alle drei sofort)
POST ... Phase 1: Produktanalyse → produkt-analyst
POST ... Phase 1: Keyword Research → keyword-researcher
POST ... Phase 1: Review-Analyse → review-analyst
```

### Kategorie-Research starten

```
# Parent
POST ... "Kategorie-Research: [Kategorie]"

# Phase R1 (alle drei mit "RESEARCH MODE" in Description)
POST ... Produkt-Analyst
POST ... Review-Analyst
POST ... Keyword Researcher
```

---

## Schritt 4: Blocker adressieren

Fuer jeden `blocked` Child in Schritt 1 gefunden:

1. Lies den Comment des Agents (warum blockiert?)
2. Entscheide:
   - **Fehlende Daten** → Reassign an upstream Agent mit konkreter Nachfrage
   - **Unklarer Scope** → Update Issue-Description, re-assign
   - **Technisches Problem (z.B. API-Key fehlt)** → Eskaliere als Human-Handoff, Parent als `blocked` markieren

---

## Schritt 5: Self-Check am Ende jedes Heartbeats

Bevor der Heartbeat endet, MUSS stimmen:

- [ ] Alle `in_progress` Parents wurden geprueft
- [ ] Alle Phasen die komplett `done` sind, haben eine naechste Phase erstellt bekommen
- [ ] Alle Parents deren Phasen alle durch sind, wurden als `done` markiert
- [ ] Neue `todo` Issues wurden triagiert
- [ ] Blocker wurden adressiert

**Wenn ein Heartbeat endet ohne dass eine dieser Aktionen passiert ist, war der Heartbeat fehlerhaft.**

---

## Regeln die IMMER gelten

1. **Schritt 1 ist nicht optional.** Jeder Heartbeat startet mit dem Pipeline-Check, auch wenn du durch eine @-mention geweckt wurdest.

2. **Kein "warten" als aktive Aktion.** Wenn du feststellst dass Phase X noch laeuft, beendest du den Heartbeat einfach. Schreibe keinen Kommentar wie "warte auf...". Das ist kein Fortschritt und verlaengert den Cycle unnoetig.

3. **Eine Phase pro Mal.** Erstelle nie alle Phasen vorab. Jede Phase wird erst getriggert wenn die vorherige komplett `done` ist.

4. **Workspace-Files in jeder Description erwaehnen.** In der Description jedes Phase-Issues musst du die relevanten Workspace-Files nennen damit der Agent weiss wo er lesen soll.

5. **Parent-Status aktiv managen.** Der Parent bleibt `in_progress` bis DU ihn auf `done` setzt. Das passiert nicht automatisch.

6. **Wenn ein Agent `@ceo` in einem Comment schreibt**, wurde dein Heartbeat wahrscheinlich wegen dieser Mention getriggered — aber das ist egal: Du machst trotzdem Schritt 1 durch. Die @-mention ist nur ein Wake-Up-Signal, keine Anweisung.
