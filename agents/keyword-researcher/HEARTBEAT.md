# Heartbeat — Keyword Researcher

Run this checklist every heartbeat.

## 1. Check for Work

```
GET /api/companies/{companyId}/issues?assigneeAgentId={myId}&status=todo,in_progress,blocked
```

## 2. Checkout Task

```
POST /api/issues/{issueId}/checkout
```

## 3. Read Input

- `produkt-analyse.md` — Product category, USPs, target audience, competitors

## 4. Research Process

### Step 4a: Seed Keywords
Extract core terms from product name, category, USPs. Identify primary search intent.

### Step 4b: Expand
Synonyms, long-tail variations, question-based queries (Rufus/COSMO), competitor reverse-engineering, seasonal variations.

### Step 4c: Qualify
Per keyword: search volume, competition level, purchase intent, relevance.

### Step 4d: Tier & Prioritize

| Tier | Placement |
|---|---|
| Primary (5-10) | Title + BP1 |
| Secondary (10-20) | BP2-5 |
| Long-tail (20-50) | Bullets + Description |
| Backend | Backend Search Terms |
| PPC-only | PPC campaigns only |
| Negative | Negative keyword list |

### Step 4e: Placement Plan
Map every primary/secondary keyword to: Title, Bullet (which one?), Description, Backend, PPC campaign type.

## 5. Self-Check

- [ ] All keywords have: volume, competition, intent, relevance
- [ ] Clear tier assignment
- [ ] Placement plan for Primary + Secondary
- [ ] Question-based keywords included
- [ ] Competitor keywords analyzed
- [ ] Negative keyword list provided

## 6. Write Output

Write `keyword-strategie.md` to `./workspace/{task-id}/`.

## 7. Complete Task

```
PATCH /api/issues/{issueId}
{
  "status": "done",
  "comment": "Keyword-Strategie abgeschlossen. [X] Primary, [X] Secondary, [X] Long-tail Keywords. Placement-Plan enthalten."
}
```
