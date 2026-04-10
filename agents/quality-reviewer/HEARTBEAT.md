# Heartbeat — Quality-Reviewer

Run this checklist every heartbeat. This is your execution loop.

## 1. Check for Tasks

- Look for new tasks: a completed `listing-briefing.md` from the Listing-Briefer
- Each task should also have the corresponding `produkt-analyse.md` for context

If no tasks: idle.

## 2. Read Both Documents

1. First read `produkt-analyse.md` — understand the product, its USPs, target audience, competitors, and key objections
2. Then read `listing-briefing.md` — evaluate it against the analysis and your 7 dimensions

## 3. Execute Review (7 Dimensions)

### Dimension 1: Amazon-Compliance (PASS / FAIL)

**This is a hard gate. A FAIL here blocks the entire briefing.**

Check against skill **amazon-compliance**:

**Slot 1 (Hero Image):**
- [ ] Pure white background (RGB 255,255,255) specified?
- [ ] No texts, logos, badges, watermarks?
- [ ] No props outside the delivery scope?
- [ ] 85-100% frame fill specified?
- [ ] Minimum 1600px+ resolution (for zoom)?
- [ ] Category-specific rules? (Clothing: standing model, Shoes: 45° left, etc.)

**Slots 2-7:**
- [ ] No prices, discounts, or purchase calls?
- [ ] No competitor brand names in comparison charts?
- [ ] No forbidden claims (especially supplements: no "FDA Approved", no disease claims)?

### Dimension 2: Mobile-Lesbarkeit (PASS / WARN / FAIL)

- [ ] All text overlays specify min. 30pt font?
- [ ] High contrast demanded for all texts?
- [ ] Main motifs centered (no crop risk)?
- [ ] Max. 5 text blocks per infographic?
- [ ] Thumbnail test mentioned for Hero Image?

### Dimension 3: Narrativ-Konsistenz (PASS / WARN / FAIL)

Read all 7 core messages in sequence:
```
1: "Das ist das Produkt"
2: "So sieht es in deinem Leben aus"
3: "Das sind die Vorteile"
4: "So gross ist es"
5: "So hochwertig ist es"
6: "Das bekommst du alles"
7: "Deshalb ist es besser als Alternativen"
```
Does the chain make a coherent argument? Is the AIDA funnel recognizable?

### Dimension 4: USP-Abdeckung (PASS / WARN / FAIL)

Cross-reference top USPs from `produkt-analyse.md` with the briefing:

| USP | Represented in Slot(s) | Status |
|---|---|---|
| [USP 1] | [?] | PASS / FAIL |
| [USP 2] | [?] | PASS / FAIL |

Every top USP must be visually represented in at least one slot.

### Dimension 5: Einwand-Behandlung (PASS / WARN / FAIL)

Cross-reference primary objections from `produkt-analyse.md`:

| Objection | Addressed in Slot(s) | How | Status |
|---|---|---|---|
| [Objection 1] | [?] | [?] | PASS / FAIL |

### Dimension 6: Keine Redundanz (PASS / WARN / FAIL)

- [ ] Each slot has a unique core message?
- [ ] No image repeats another's message?
- [ ] No duplicate elements across slots?

### Dimension 7: Kategorie-Regeln (PASS / FAIL)

Check against skill **kategorie-regeln**:
- [ ] Correct category-specific slot sequence used?
- [ ] Category-mandatory elements present?
- [ ] Category-specific prohibitions respected?

## 4. Determine Verdict

| Condition | Verdict |
|---|---|
| All dimensions PASS | **APPROVED** |
| At least one WARN, no FAIL | **REVISION_NOETIG** |
| Compliance FAIL or 2+ other FAILs | **REVISION_NOETIG** (severe) |
| Data from produkt-analyse insufficient | **ABGELEHNT** (back to Analyst) |

## 5. Write Output

Write `review-ergebnis.md` to the task workspace in the Interface C format (see skill: review-interface).

Include:
- Summary (2-3 sentences)
- Score per dimension (table)
- Slot-level detail for every WARN/FAIL (problem + fix + priority)
- Positive feedback (what works well)
- Recommended action

## 6. Route Result

| Verdict | Action |
|---|---|
| APPROVED | Mark task as done. Briefing is ready for designer. |
| REVISION_NOETIG | Create subtask for Listing-Briefer with fixes. |
| ABGELEHNT | Create subtask for Produkt-Analyst (more data needed). |
