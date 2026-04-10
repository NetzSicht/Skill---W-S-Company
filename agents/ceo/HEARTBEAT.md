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

### Full Listing Optimization

Create a parent issue, then child issues with dependencies:

```
POST /api/companies/{companyId}/issues

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
