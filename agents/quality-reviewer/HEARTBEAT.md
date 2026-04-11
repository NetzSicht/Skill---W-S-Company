# Heartbeat — Quality-Reviewer

Run this checklist every heartbeat.

## 1. Check for Work

```
GET /api/companies/{companyId}/issues?assigneeAgentId={myId}&status=todo,in_progress,blocked
```

If no issues: idle.

## 2. Checkout Task

```
POST /api/issues/{issueId}/checkout
```

Read issue description. Identify which files to review in `./workspace/{task-id}/`.

## 2b. Load Category Skill

Read the product category from `produkt-analyse.md`. If a category-specific skill is attached (e.g., `kategorie-textil-socken`), read your agent section BEFORE reviewing. The category skill provides:
- Category-specific quality checks (additional to the 7 dimensions)
- Mandatory elements for this product type (FAIL if missing)
- Common category mistakes to watch for

## 3. Read Both Documents

1. Read `produkt-analyse.md` — understand product, USPs, target audience, objections
2. Read `listing-briefing.md` — evaluate against analysis and 7 dimensions

## 4. Execute Review (7 Dimensions)

### Dimension 1: Amazon-Compliance (PASS / FAIL)
Hard gate. Check Slot 1 rules + Slots 2-7 prohibitions per skill **amazon-compliance**.

### Dimension 2: Mobile-Lesbarkeit (PASS / WARN / FAIL)
30pt minimum, high contrast, centered motifs, max 5 text blocks, thumbnail test.

### Dimension 3: Narrativ-Konsistenz (PASS / WARN / FAIL)
Read all 7 core messages in sequence. AIDA funnel recognizable?

### Dimension 4: USP-Abdeckung (PASS / WARN / FAIL)
Cross-reference top USPs from analysis with briefing. Every USP in at least one slot?

### Dimension 5: Einwand-Behandlung (PASS / WARN / FAIL)
Cross-reference primary objections. Each addressed?

### Dimension 6: Keine Redundanz (PASS / WARN / FAIL)
Each slot unique? No duplicated messages?

### Dimension 7: Kategorie-Regeln (PASS / FAIL)
Correct category sequence? Mandatory elements present? Per skill **kategorie-regeln**.

### Bonus: Galerie-A+ Abstimmung
If A+ briefing also present: check per skill **listing-content-architektur**. No duplicated images, no repeated messages, A+ Uebergabe section complete.

## 5. Determine Verdict

| Condition | Verdict |
|---|---|
| All PASS | **APPROVED** |
| ≥1 WARN, no FAIL | **REVISION_NOETIG** |
| Compliance FAIL or 2+ FAILs | **REVISION_NOETIG** (severe) |
| Analysis data insufficient | **ABGELEHNT** |

## 6. Write Output

Write `review-ergebnis.md` to `./workspace/{task-id}/` in Interface C format (see skill: review-interface).

## 7. Route Result

### APPROVED
```
PATCH /api/issues/{issueId}
{ "status": "done", "comment": "APPROVED. Briefing ist freigegeben fuer den Designer." }
```

### REVISION_NOETIG
Create subtask for Listing-Briefer with fixes:
```
POST /api/companies/{companyId}/issues
{
  "title": "Revision Bild-Briefing — [Produkt]",
  "description": "Review-Ergebnis: REVISION_NOETIG. Fixes: [konkrete Anweisungen]. Siehe review-ergebnis.md im Workspace.",
  "assigneeAgentId": "[listing-briefer-id]",
  "parentId": "[parent-issue-id]",
  "status": "todo",
  "priority": "high"
}
```
Then mark own issue as done:
```
PATCH /api/issues/{issueId}
{ "status": "done", "comment": "REVISION_NOETIG. Subtask fuer Listing-Briefer erstellt." }
```

### ABGELEHNT
Create subtask for Produkt-Analyst:
```
POST /api/companies/{companyId}/issues
{
  "title": "Nachlieferung Produktdaten — [Produkt]",
  "description": "Analyse unzureichend. Fehlend: [was fehlt]. Siehe review-ergebnis.md.",
  "assigneeAgentId": "[produkt-analyst-id]",
  "parentId": "[parent-issue-id]",
  "status": "todo",
  "priority": "high"
}
```
