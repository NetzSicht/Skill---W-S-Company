# Heartbeat — ClickUp Manager

Run this checklist every heartbeat.

## 1. Check for Work

```
GET /api/companies/{companyId}/issues?assigneeAgentId={myId}&status=todo,in_progress,blocked
```

Typical tasks from CEO:
- "Mirror new project to ClickUp"
- "Update client project status"
- "Create time entry for [project]"

## 2. Checkout Task

```
POST /api/issues/{issueId}/checkout
```

## 3. Mirror Project Status

When asked to update client visibility:

1. Read the parent issue and all child issues in paperclip.ing
2. Map internal status to client-friendly ClickUp status:

| paperclip.ing Status | ClickUp Status | Client-Friendly Label |
|---|---|---|
| Phase 1 complete | In Progress | "Datenanalyse abgeschlossen" |
| Phase 2 in progress | In Progress | "Briefings werden erstellt" |
| Phase 3 (Review) | In Review | "Quality Check laeuft" |
| APPROVED | Ready | "Briefings freigegeben — bereit fuer Design" |
| REVISION_NOETIG | In Progress | "Ueberarbeitung laeuft" |
| All phases done | Complete | "Projekt abgeschlossen" |

3. Update ClickUp task with status + brief summary
4. Add time entries if tracked

## 4. New Project Setup

When CEO creates a new project:

1. Create ClickUp folder/list for the client project
2. Create high-level tasks (client-visible milestones, not internal agent tasks):
   - "Produktanalyse & Research"
   - "Bild-Briefing & Listing-Texte"
   - "Quality Review"
   - "A+ Content & PPC"
   - "Finale Lieferung"
3. Set due dates from CEO's brief
4. Assign to NetzSicht team in ClickUp (not to individual agents)

## 5. Complete Task

```
PATCH /api/issues/{issueId}
{
  "status": "done",
  "comment": "ClickUp aktualisiert. [Was gemacht wurde]."
}
```
