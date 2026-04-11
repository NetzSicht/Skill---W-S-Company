# Heartbeat — Review-Analyst

Run this checklist every heartbeat.

## 1. Check for Work

```
GET /api/companies/{companyId}/issues?assigneeAgentId={myId}&status=todo,in_progress,blocked
```

## 2. Checkout Task

```
POST /api/issues/{issueId}/checkout
```

## 2b. Load Category Skill

Read the product category from `produkt-analyse.md`. If a category-specific skill is attached (e.g., `kategorie-textil-socken`), read your agent section BEFORE analyzing reviews. The category skill provides:
- Category-specific review search patterns (exact terms to search for)
- Frequency thresholds for this product type
- Language extraction templates with minimum phrase counts
- Common objection clusters specific to this category

## 3. Read Input

- `produkt-analyse.md` — Product info, competitor ASINs
- Access product and competitor reviews on Amazon

## 4. Analysis Process

### Step 4a: Own Product Reviews (if existing listing)
Analyze last 100-200 reviews: top 5 praise, top 5 criticism, surprise moments, expectation gaps, buyer personas.

### Step 4b: Competitor Reviews
For each top competitor: what customers love (our minimum), what they hate (our opportunity), what they wish existed (our differentiator).

### Step 4c: Q&A Analysis
Unanswered questions = listing content gaps. Map each to: slot, bullet, or A+ module.

### Step 4d: Language Extraction
Positive phrases, pain point descriptions, feature language — real customer vocabulary for the Content Master.

### Step 4e: Objection Map

| Objection | Frequency | Source | Addressable In |
|---|---|---|---|
| [Issue] | [x reviews] | [own/competitor] | [Slot/BP/A+ Module] |

## 5. Self-Check

- [ ] Top 5 praise + criticism with frequency and quotes
- [ ] ≥3 competitor review analyses
- [ ] Q&A gaps identified and mapped
- [ ] Customer vocabulary bank (≥10 phrases)
- [ ] Objection map with placement recommendations
- [ ] Buyer personas segmented

## 6. Write Output

Write `review-insights.md` to `./workspace/{task-id}/`.

## 7. Complete Task

```
PATCH /api/issues/{issueId}
{
  "status": "done",
  "comment": "Review-Analyse abgeschlossen. [X] Praise, [X] Kritik, [X] Einwaende identifiziert. Vokabular-Bank mit [X] Phrasen."
}
```
