# Heartbeat — Listing-Briefer

Run this checklist every heartbeat.

## 1. Check for Work

```
GET /api/companies/{companyId}/issues?assigneeAgentId={myId}&status=todo,in_progress,blocked
```

Two types of work:
- **New briefing:** Fresh issue from CEO (status: todo)
- **Revision:** Subtask from Quality-Reviewer with fixes (check for parentId)

Prioritize: revisions first, then new work.

## 2. Checkout Task

```
POST /api/issues/{issueId}/checkout
```

Read issue description for context. Check which files are available in `./workspace/{task-id}/`.

## 2b. Load Category Skill

Read the product category from `produkt-analyse.md` (Section 1: Kategorie). If a category-specific skill is attached (e.g., `kategorie-textil-socken`), read your agent section BEFORE creating the briefing. The category skill provides:
- Category-specific slot sequence (overrides Standard-Balanced)
- Slot-by-slot depth rules and callout templates
- Subtype-specific adaptations
- Common visual mistakes to avoid in this category

If no category skill is attached: use standard slot sequence from `kategorie-adaptionen` skill.

## 2c. Check: Audit Available? (Optimization Mode)

Look for `listing-audit.md` in `./workspace/{task-id}/`. If it exists:

1. Read the complete audit, especially Section 9 "Fuer Listing-Briefer" — the slot-by-slot status table.
2. The audit tells you for each of the 7 slots: **KEEP / ENHANCE / REBUILD / MISSING**
3. Your briefing must respect these statuses:

| Audit Status | What You Do |
|---|---|
| **KEEP** | Copy the current slot description unchanged into your new briefing. Mark it clearly: "Slot X: KEEP — uebernehmen wie aktuell auf ASIN [X]". Do NOT redesign. |
| **ENHANCE** | Use the current slot as the baseline. Improve specific elements named in the audit fix-instruction. Preserve what works. |
| **REBUILD** | Create a completely new slot briefing from scratch. Ignore the current version. |
| **MISSING** | Create a new slot briefing for an element that doesn't exist yet. |

This is critical: **do not redo work that already works**. The audit has already validated it. Your job in optimization mode is to fix the broken 30%, not rebuild the 70% that performs.

Your output format stays the same (briefing-template), but each slot block now starts with the audit status:
```markdown
## Slot [X]: [Bildtyp] — Audit-Status: [KEEP/ENHANCE/REBUILD/MISSING]
[Rest of briefing block]
```

If no audit exists: proceed as normal (new listing mode).

## 3. Read Product Analysis

Read `./workspace/{task-id}/produkt-analyse.md` thoroughly. Extract:
- Category → determines slot adaptation
- Price level → affects emphasis
- Top USPs → MUST appear in briefing
- Primary objections → MUST be addressed
- Strategy recommendation → you decide whether to follow
- Competitor visual gaps → opportunities

If fields marked `[NICHT VERFUEGBAR]`: note which slots are affected.

## 4. Determine Slot Strategy

### Step 4a: Check Category
Read skill **kategorie-adaptionen**. Category-specific sequence? Use it. Otherwise: Standard-Balanced.

### Step 4b: Adjust for Price Level
- Premium: emphasize quality close-ups, brand story, perceived value
- Budget: emphasize value proposition, price-performance comparison

### Step 4c: Map USPs to Slots
Every top USP visually represented in at least one slot.

### Step 4d: Map Objections to Slots
Every primary objection addressed in at least one slot.

## 5. Generate Briefing

For each of 7 slots, write a complete block per **briefing-template** skill:
1. Kernbotschaft
2. Psychologische Funktion
3. Pflicht-Elemente
4. Optionale Elemente
5. Text-Overlay
6. Technische Vorgaben
7. Farbwelt & Stimmung
8. Designer-Notizen
9. Referenz/Inspiration
10. A/B-Test-Vorschlag

Include header (strategic summary, USP mapping, objection mapping) and footer.

## 6. A+ Content Uebergabe

Per skill **listing-content-architektur**, include at the end of the briefing:

```markdown
## A+ Content Uebergabe

### In der Galerie abgedeckt:
- [What each slot covers]

### NICHT abgedeckt — A+ muss uebernehmen:
- [Technology explanation, extended use cases, FAQ, etc.]

### Bilder die A+ NICHT wiederholen darf:
- [List each slot's key visual]
```

## 7. Self-Check

- [ ] All 7 slots unique (no redundancy)
- [ ] AIDA funnel recognizable
- [ ] Every top USP visually represented
- [ ] Every primary objection addressed
- [ ] Slot 1 Amazon-compliant (white bg, no text, 85-100% fill)
- [ ] All text overlays ≥30pt
- [ ] Category-specific rules applied
- [ ] No competitor brand names
- [ ] A+ Uebergabe section complete
- [ ] Briefing-template format exact

## 8. Write Output

Write `listing-briefing.md` to `./workspace/{task-id}/`.

## 9. Complete Task

```
PATCH /api/issues/{issueId}
{
  "status": "done",
  "comment": "Bild-Briefing abgeschlossen. Strategie: [Type]. 7 Slots definiert. A+ Uebergabe enthalten."
}
```

## Handling Revisions

When you receive a revision issue (from Quality-Reviewer):
1. Read the linked `review-ergebnis.md` — focus on FAIL and WARN items
2. Read specific fix instructions per slot
3. Apply fixes to existing `listing-briefing.md`
4. Re-run self-check (Step 7)
5. Update issue as done with comment noting what was fixed
