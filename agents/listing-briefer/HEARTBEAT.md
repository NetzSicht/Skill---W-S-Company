# Heartbeat — Listing-Briefer

Run this checklist every heartbeat. This is your execution loop.

## 1. Check for Tasks

- Look for new tasks: a completed `produkt-analyse.md` from the Produkt-Analyst
- Look for revision requests: a `review-ergebnis.md` from the Quality-Reviewer with status REVISION_NOETIG

If no tasks: idle.

## 2. Read the Product Analysis

Read `produkt-analyse.md` thoroughly. Extract and internalize:
- Category (determines if you need a category-specific slot adaptation)
- Price level (Budget/Mittel/Premium — affects emphasis on quality vs. value)
- Top USPs (these MUST appear in the briefing)
- Primary objections (these MUST be addressed)
- Strategy recommendation from the Analyst (you decide whether to follow it)
- Competitor visual gaps (opportunities for differentiation)

If fields are marked `[NICHT VERFUEGBAR]`, note which slots will be affected and flag this in the briefing.

## 3. Determine Slot Strategy

### Step 3a: Check Category

Read skill **kategorie-adaptionen**. Does this product's category have a specific slot sequence?
- Supplements → Supplement Facts Panel early, certifications prominent
- Electronics → "What's in the Box" early, compatibility info
- Textiles → Model requirements, size chart mandatory
- Beauty → Ingredient focus, texture shots
- Furniture → Room setting, exact dimensions
- Food → Nutrition table, origin info

If yes: use the category-specific sequence as your starting point.
If no: use the Standard-Balanced sequence (AIDA funnel).

### Step 3b: Adjust for Price Level

- Premium (>50 EUR): Emphasize material/quality close-ups, brand story elements, perceived value
- Budget (<15 EUR): Emphasize value proposition, comparison chart for price-performance

### Step 3c: Map USPs to Slots

Every top USP from the analysis must be visually represented in at least one slot. Create a mapping:

```
USP 1 → Slot X (how it will be shown)
USP 2 → Slot Y
USP 3 → Slot Z
```

### Step 3d: Map Objections to Slots

Every primary objection must be addressed:

```
Objection 1 → Slot X (how it will be handled)
Objection 2 → Slot Y
```

## 4. Generate Briefing

For each of the 7 slots, write a complete briefing block following the **briefing-template** skill format:

1. **Kernbotschaft** — What should the viewer understand in 2 seconds?
2. **Psychologische Funktion** — Which buyer question is answered?
3. **Pflicht-Elemente** — What MUST be in the image?
4. **Optionale Elemente** — What CAN be added?
5. **Text-Overlay** — Yes/No + exact text suggestions, font specs
6. **Technische Vorgaben** — Resolution, format, special requirements
7. **Farbwelt & Stimmung** — Atmosphere, color palette
8. **Designer-Notizen** — Specific guidance from the product analysis
9. **Referenz/Inspiration** — Reference images or competitor examples
10. **A/B-Test-Vorschlag** — What variant to test

Also write the briefing header (strategic summary, USP mapping, objection mapping) and footer (review checklist, A+ Content recommendation, next steps).

## 5. Self-Check Before Submission

Before writing the output, verify:

- [ ] All 7 slots have a unique core message (no redundancy)
- [ ] AIDA funnel is recognizable in the sequence
- [ ] Every top USP is visually represented in at least one slot
- [ ] Every primary objection is addressed in at least one slot
- [ ] Slot 1 Hero Image is Amazon-compliant (white bg, no text, 85-100% fill)
- [ ] All text overlays specify minimum 30pt font
- [ ] Category-specific rules are applied
- [ ] No competitor brand names in comparison charts
- [ ] Briefing-template format is followed exactly

## 6. Write Output

Write `listing-briefing.md` to the task workspace.

## 7. Mark Task Complete

Mark your task as done. This triggers the Quality-Reviewer.

## Handling Revisions

When you receive a revision request (REVISION_NOETIG):

1. Read `review-ergebnis.md` — focus on FAIL and WARN items
2. Read the specific fix instructions for each flagged slot
3. Apply fixes to your existing `listing-briefing.md`
4. Re-run the self-check (Step 5)
5. Resubmit
