# Heartbeat — ClickUp Manager

## 1. Check for Work

- New assignments from CEO that need ClickUp tasks
- Status updates from agents (task completions, blockers)
- Overdue tasks to escalate

## 2. Create Tasks (from CEO briefs)

When the CEO assigns a new project:

### Full Listing Optimization

Create a ClickUp folder or list for the project, then tasks:

```
Project: [Client] — [Product Name]
│
├── Phase 1 (parallel)
│   ├── Task: Produktanalyse          → Assign: Produkt-Analyst
│   ├── Task: Keyword Research        → Assign: Keyword Researcher
│   └── Task: Review-Analyse          → Assign: Review-Analyst
│
├── Phase 2 (depends on Phase 1)
│   ├── Task: Bild-Briefing           → Assign: Listing-Briefer
│   └── Task: Listing-Texte           → Assign: Content Master
│
├── Phase 3 (depends on Phase 2)
│   └── Task: Quality Review          → Assign: Quality-Reviewer
│
├── Phase 4 (depends on Phase 3)
│   ├── Task: A+ Content Briefing     → Assign: A+ Content Designer
│   └── Task: PPC Kampagne            → Assign: PPC Specialist
│
└── Phase 5
    └── Task: Client Delivery         → Assign: CEO
```

Set task dependencies so agents can't start before their inputs are ready.

### Single Tasks

Create individual tasks with:
- Clear title (Verb + Object + Context)
- Description with all relevant context
- Assignee
- Due date
- Priority (Urgent / High / Normal / Low)
- Dependencies (if any)

## 3. Monitor Pipeline Status

Check all active tasks:

| Status | Action |
|---|---|
| Overdue | Flag to CEO, ping assignee |
| Blocked | Identify blocker, create resolution task or escalate |
| In Review | Ensure reviewer is aware |
| Done | Route output to next pipeline step, update dependencies |

## 4. Status Report

Prepare a brief status summary when requested or on schedule:

```
## Pipeline Status: [Date]

### Active Projects
- [Project 1]: Phase 2 — Briefer und Content Master arbeiten parallel
- [Project 2]: Phase 3 — Quality Review laeuft

### Blocked
- [Task]: Warte auf [was] von [wem] seit [wann]

### Completed Today
- [Task 1] ✓
- [Task 2] ✓

### Upcoming Deadlines
- [Task]: faellig [Datum]
```

## 5. Workspace Hygiene

- Archive completed projects
- Clean up stale tasks (>7 days without activity)
- Ensure all tasks have assignees and due dates
- Update task descriptions when scope changes
