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

### Step 4d2: Exploit Competitor Weaknesses

Lies die **Exploitation-Matrix** aus `produkt-analyse.md` Sektion 7. Jeder "Unser Move" MUSS im Briefing umgesetzt werden — im Slot/BP das der Produkt-Analyst markiert hat.

Beispiele:
- "Wettbewerber hat keine Groessentabelle" → Slot 4 wird **prominent** mit EU+UK+US Tabelle
- "Wettbewerber nutzt nur 4 Slots" → Wir fuellen alle 7 Slots (Slot 5-7 als Differenzierung)
- "Wettbewerber zeigt nur 1 Socke im Hero trotz 3er Pack" → Unser Slot 1 zeigt **explizit** alle 3 Socken im Knolling-Layout
- "Wettbewerber hat 23% Naht-Beschwerden" → Unser BP4/Slot 5 adressiert Nahtfrei-Konstruktion prominent

Pro Exploitation-Move im Briefing markieren: `[EXPLOITS: Wettbewerber X Schwaeche Y]`. Der Quality-Reviewer prueft ob alle Moves umgesetzt sind.

### Step 4e: Map Search-Painpoints to Slots (KRITISCH)

**Der wichtigste Schritt.** Aus `review-insights.md` die Search-Painpoints lesen (Was hat den Kunden ueberhaupt zur Suche getrieben?). Bei aktivem Kategorie-Skill zusaetzlich die dort hinterlegte Such-Painpoint-Map konsultieren.

**Regel:** Jeder der 7 Slots MUSS mindestens einen Search-Painpoint adressieren. Ein Slot ohne adressierten Painpoint ist verschwendet und wird vom Quality-Reviewer zurueckgewiesen.

**Painpoint-Slot-Mapping Tabelle erstellen:**

```markdown
| Slot | Primaerer Painpoint | Sekundaerer Painpoint | Emotionaler Trigger |
|---|---|---|---|
| 1 | [Kategorie-Schmerz] | — | Der Kunde erkennt sofort: "Das ist was ich gesucht habe" |
| 2 | [Top-Painpoint] | [Optional] | Spiegelneuronen: Der Kunde sieht sich selbst mit dem Problem geloest |
| 3 | [Top 3 Painpoints] | — | Rationale Rechtfertigung der Loesung |
| 4 | [Groessen-/Passform-Pain] | — | Unsicherheit eliminieren |
| 5 | [Qualitaets-/Material-Pain] | — | Taktile Bestaetigung der Qualitaet |
| 6 | [Wert-Pain] | — | "Das bekomme ich alles dafuer" |
| 7 | [Vergleichs-Pain] | — | Differenzierung vom Wettbewerb |
```

**Beispiel fuer Wandersocken:**

| Slot | Painpoint | Trigger |
|---|---|---|
| 1 | "Ich will Wandersocken die funktionieren" | Hero zeigt sofort Produkt + Hoehe + Menge |
| 2 | "Ich hatte schon Blasen beim Wandern" | Wanderszene — Fuss im Stiefel, nach Stunden noch komfortabel |
| 3 | "Schwitzen, Druckstellen, Geruch" | Infografik: Merino + Polsterzonen + Antibakteriell |
| 4 | "Passt die Groesse? Kaufe ich die falsche?" | Groessentabelle EU/UK/US + Fusslaenge |
| 5 | "Ist das wirklich hochwertig oder billiger Nachbau?" | Nahaufnahme Merino-Strick + handgekettelte Spitze |
| 6 | "Lohnt sich der Preis fuer was ich bekomme?" | 3er Pack arrangiert, Oeko-Tex sichtbar |
| 7 | "Warum diese und nicht die guenstigen bei Decathlon?" | Material-Vergleich 80% Merino vs. 60% Polyester |

## 5. Generate Briefing

For each of 7 slots, write a complete block per **briefing-template** skill. **Ergaenze ein Pflichtfeld:**

1. **Adressierter Painpoint** ← NEU PFLICHT
2. **Emotionaler Trigger** ← NEU PFLICHT
3. Kernbotschaft
4. Psychologische Funktion
5. Pflicht-Elemente
6. Optionale Elemente
7. Text-Overlay
8. Technische Vorgaben
9. Farbwelt & Stimmung
10. Designer-Notizen
11. Referenz/Inspiration
12. A/B-Test-Vorschlag

Include header (strategic summary, USP mapping, objection mapping, **painpoint mapping**) and footer.

## 5b. Video-Slot pruefen (wenn Brand Registry)

Lies `produkt-analyse.md` Sektion 1: Ist Brand Registry aktiv?

**Wenn JA:** Erstelle zusaetzlich zu den 7 Bild-Slots ein **Video-Briefing** (siehe Skill `video-briefing-framework`). Das Video-Briefing folgt der 30-Sekunden-Formel (Hook → Problem+Produkt → Demo → Trust → Close).

**Wenn NEIN:** Ueberspringe Video-Slot. Notiere im Briefing: "Video-Slot nicht verfuegbar — Brand Registry fehlt. Empfehlung: Brand Registry beantragen fuer +9-15% Conversion."

## 5c. Mobile-First Validation

Nach Erstellung des Briefings fuer JEDEN Slot: Mobile-First Validation durchfuehren (siehe Skill `mobile-first-validation`). Pro Slot im Briefing ergaenzen:

```markdown
**Mobile-Check:** [PASS / WARN / FAIL]
**Mobile-Anpassung:** [Was der Designer fuer Mobile beachten muss]
```

Bei FAIL: Slot ueberarbeiten, bevor das Briefing rausgeht.

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
  "comment": "@ceo Bild-Briefing abgeschlossen. Strategie: [Type]. 7 Slots definiert. A+ Uebergabe enthalten. Output: listing-briefing.md im Workspace."
}
```

## Handling Revisions

When you receive a revision issue (from Quality-Reviewer):
1. Read the linked `review-ergebnis.md` — focus on FAIL and WARN items
2. Read specific fix instructions per slot
3. Apply fixes to existing `listing-briefing.md`
4. Re-run self-check (Step 7)
5. Update issue as done with comment noting what was fixed
