# Heartbeat — CEO

Run this checklist every heartbeat.

## 1. Check Inbox

Query your assigned issues:
```
GET /api/companies/{companyId}/issues?assigneeAgentId={myId}&status=todo,in_progress,blocked
```

Look for:
- New client requests or briefs (status: todo)
- Escalations from agents (status: blocked)
- Completed subtasks that need routing (check child issue statuses)

## 2. Triage New Work

For each new request, create issues via the Issues API and assign to the right agents:

### Neu-Listing vs. Optimierung entscheiden

**Hat der Kunde eine ASIN eines bestehenden Listings?**

- **Ja → OPTIMIERUNG** (mit Audit in Phase 0)
- **Nein → NEU-LISTING** (direkt Phase 1)

### Zusaetzlich pruefen: Gibt es einen Kategorie-Skill?

Wenn NEIN → Zuerst Kategorie-Research starten, DANN Listing-Projekt.
Wenn JA → Direkt zum Listing-Projekt.

### Optimierung (bestehende ASIN)

```
Parent: "Optimierung: [Product] — [Client] — ASIN [X]"

Phase 0 (zuerst — Audit des bestehenden Listings):
  └── "Listing-Audit — ASIN [X]"  → assigneeAgentId: listing-auditor
        Description: "Auditiere das bestehende Listing fuer ASIN [X]
        auf [amazon.de]. Pruefe alle 10 Dimensionen. Erstelle
        listing-audit.md mit Adaption-Anweisungen fuer alle
        downstream Agents."

Phase 1 (nach Audit — parallel):
  ├── "Produktanalyse"         → assigneeAgentId: produkt-analyst
  │     Description: "OPTIMIERUNG. Lies listing-audit.md und
  │     arbeite adaptiv — nicht alles neu erforschen, nur was
  │     im Audit als FOKUS markiert ist."
  ├── "Keyword Research"       → assigneeAgentId: keyword-researcher
  └── "Review-Analyse"         → assigneeAgentId: review-analyst

Phase 2 (parallel):
  ├── "Bild-Briefing"         → assigneeAgentId: listing-briefer
  │     Description: "OPTIMIERUNG. Respektiere Slot-Status aus
  │     listing-audit.md: KEEP Slots uebernehmen, ENHANCE
  │     verbessern, REBUILD neu machen, MISSING ergaenzen."
  └── "Listing-Texte"         → assigneeAgentId: content-master
        Description: "OPTIMIERUNG. Respektiere Text-Status aus
        listing-audit.md: KEEP Elemente unveraendert uebernehmen,
        ENHANCE nur chirurgisch verbessern, REBUILD neu."

Phase 3:
  └── "Quality Review"        → assigneeAgentId: quality-reviewer

Phase 4 (nach Approval):
  ├── "A+ Content Briefing"   → assigneeAgentId: aplus-content-designer
  └── "PPC Optimierung"       → assigneeAgentId: ppc-specialist

Phase 5:
  └── "Client Delivery"       → assigneeAgentId: ceo (self)
```

### Neu-Listing (keine bestehende ASIN)

```
Parent: "Full Listing: [Product] — [Client]"

Phase 1 (parallel — assign immediately):
  ├── "Produktanalyse"         → assigneeAgentId: produkt-analyst
  ├── "Keyword Research"       → assigneeAgentId: keyword-researcher
  └── "Review-Analyse"        → assigneeAgentId: review-analyst

Phase 2 (create after Phase 1 completes):
  ├── "Bild-Briefing"         → assigneeAgentId: listing-briefer
  └── "Listing-Texte"         → assigneeAgentId: content-master

Phase 3 (create after Phase 2 completes):
  └── "Quality Review"        → assigneeAgentId: quality-reviewer

Phase 4 (create after Phase 3 approved):
  ├── "A+ Content Briefing"   → assigneeAgentId: aplus-content-designer
  └── "PPC Kampagne"          → assigneeAgentId: ppc-specialist

Phase 5:
  └── "Client Delivery"       → assigneeAgentId: ceo (self)
```

Each issue needs: title, description with full context, assigneeAgentId, priority, parentId.

Assigning an agent triggers their heartbeat automatically.

### Kategorie-Research (einmalig pro neue Kategorie)

Wird gestartet wenn ein Produkt in einer Kategorie kommt fuer die es noch keinen tiefen Kategorie-Skill gibt. Das Research fuettert den Kategorie-Skill mit echten Daten aus der Kategorie.

```
Parent: "Kategorie-Research: [Kategorie-Name] — [Marktplatz]"

Phase R1 (parallel — alle drei gleichzeitig):
  ├── "Kategorie-Scan: Top 15 Listings"    → assigneeAgentId: produkt-analyst
  │     Description: "RESEARCH MODE. Nutze Rainforest API um die Top 15 
  │     organischen Listings fuer [Hauptkeyword] auf [amazon.de] zu analysieren.
  │     Ziehe Produktdaten, Bilder, Titel, Bullets, Preise. Schreibe Ergebnis
  │     in kategorie-research.md Sektionen 1.1 bis 1.6.
  │     Skill: kategorie-research-template"
  │
  ├── "Kategorie-Reviews: Kundenstimmen Top 15"  → assigneeAgentId: review-analyst
  │     Description: "RESEARCH MODE. Nutze Rainforest API um positive und
  │     kritische Reviews + Q&A der Top 15 ASINs zu analysieren. Extrahiere
  │     Lob, Kritik, Einwaende, Vokabular, Personas. Schreibe in 
  │     kategorie-research.md Sektionen 2.1 bis 2.7.
  │     Skill: kategorie-research-template"
  │
  └── "Kategorie-Keywords: Suchlandschaft"  → assigneeAgentId: keyword-researcher
        Description: "RESEARCH MODE. Nutze Rainforest API Autocomplete + 
        Search + Bestsellers um die Keyword-Landschaft der Kategorie zu 
        kartieren. Schreibe in kategorie-research.md Sektionen 3.1 bis 3.6.
        Skill: kategorie-research-template"

Phase R2 (nach Phase R1):
  └── "Kategorie-Synthese"  → assigneeAgentId: ceo (self)
        Alle drei Sektionen zusammenfuehren, Synthese (Sektion 4) schreiben,
        Erkenntnisse in den dauerhaften Kategorie-Skill einpflegen.
```

**Credit-Budget pro Kategorie-Research: ~95 Rainforest API Requests**
- Produkt-Analyst: ~35 (1 Search + 15 Products + 15 Offers + Buffer)
- Review-Analyst: ~45 (15x positive Reviews + 15x critical Reviews + 15x Q&A)
- Keyword Researcher: ~15 (10 Autocomplete + Bestsellers + Buffer)

### Single Tasks

Create one issue, assign directly:
```
POST /api/companies/{companyId}/issues
{
  "title": "[Verb] [Object] — [Context]",
  "description": "[Full context: what, why, inputs available, success criteria]",
  "assigneeAgentId": "[target-agent-id]",
  "status": "todo",
  "priority": "[critical/high/medium/low]"
}
```

## 3. Monitor Active Pipelines

Check child issue statuses of active parent issues:

| Child Status | Action |
|---|---|
| `done` | Create next-phase issue if dependencies met |
| `blocked` | Read comment, resolve or reassign |
| `in_progress` | No action — agent is working |
| `in_review` | Check if you need to review |

## 4. Route Completed Work

When a phase completes (all child issues in that phase = done):
- Create next-phase issues (Phase 1 done → create Phase 2 issues)
- Include in description: which files are available in workspace, what upstream agents found

When Quality-Reviewer marks done:
- Read `review-ergebnis.md` in workspace
- If APPROVED → create Phase 4 issues
- If REVISION_NOETIG → no action needed (Quality-Reviewer already created subtask back to Briefer)
- If ABGELEHNT → no action needed (Quality-Reviewer already created subtask back to Analyst)

## 5. Client Delivery

When all phases are done:
- Collect all outputs from `./workspace/{task-id}/`
- Prepare client-ready summary
- If ClickUp Manager is active: ask them to mirror status to ClickUp for client visibility
- Mark parent issue as `done`

## 6. Update ClickUp (optional)

If client needs external visibility:
- Create issue for ClickUp Manager: "Update client project status"
- Include: what's done, what's in progress, any delays
