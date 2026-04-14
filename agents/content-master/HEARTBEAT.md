# Heartbeat — Content Master

Run this checklist every heartbeat.

## 1. Check for Work

```
GET /api/companies/{companyId}/issues?assigneeAgentId={myId}&status=todo,in_progress,blocked
```

## 2. Checkout Task

```
POST /api/issues/{issueId}/checkout
```

Read issue description. Check available files in `./workspace/{task-id}/`.

## 2b. Load Category Skill

Read the product category from `produkt-analyse.md`. If a category-specific skill is attached (e.g., `kategorie-textil-socken`), read your agent section BEFORE writing copy. The category skill provides:
- Category-specific title formula with examples
- Bullet point hierarchy adapted to this product type
- Mandatory keywords and keyword patterns
- PAN-EU keyword lists per marketplace

## 2c. Check: Audit Available? (Optimization Mode)

Look for `listing-audit.md` in `./workspace/{task-id}/`. If it exists:

1. Read the complete audit, especially Section 9 "Fuer Content Master".
2. For each text element (Title, BP1-5, Backend Keywords) the audit provides a status: **KEEP / ENHANCE / REBUILD / MISSING**

| Audit Status | What You Do |
|---|---|
| **KEEP** | Copy the current text unchanged into `listing-texte.md`. Mark it: "(KEEP — aus aktuellem Listing uebernommen)". Do NOT rewrite. |
| **ENHANCE** | Use the current text as baseline. Improve only what the audit fix-instruction says. Preserve tone, keywords, structure. |
| **REBUILD** | Write completely new. Ignore the current version. |
| **MISSING** | Write new (e.g., PAN-EU backend keywords not yet present). |

Your output format stays the same, but each element now starts with the status tag.

**Critical:** Do not rewrite working titles or bullets. If the audit says the current BP2 performs well, keep it verbatim. Optimization means surgical changes, not full rewrites.

If no audit exists: proceed as normal (new listing mode).

## 3. Read Input Documents

- `produkt-analyse.md` — Product data, USPs, target audience
- `keyword-strategie.md` — Primary keywords, long-tails, placement plan
- `review-insights.md` — Customer language, praise, criticism
- `listing-briefing.md` — Image briefing (if available, for text-image synergy)

## 4. Create Listing Title

Formula: **Brand + Top Intent Phrase + Feature Group + Use Case + Specs**

- 150-180 characters total
- First 70 characters: brand + primary keyword (mobile visibility)
- Natural language — no keyword stuffing
- Must match what buyer sees in Hero Image

## 4b. Exploit Competitor Weaknesses

Lies die Exploitation-Matrix aus `produkt-analyse.md` Sektion 7. Wenn ein Move auf Titel, Bullets oder Backend zielt, setze ihn explizit um.

Beispiele:
- "Wettbewerber erwaehnt Groesse nicht im Titel" → Unser Titel enthaelt Groessenangabe prominent
- "Wettbewerber-Bullets listen nur Features" → Unsere Bullets sind alle Benefit-basiert
- "Wettbewerber hat keine PAN-EU Backend-Keywords" → Wir haben FR/IT/ES/NL Keywords
- "Wettbewerber-Titel hat Keyword-Stuffing" → Unser Titel liest sich natuerlich (Rufus-Vorteil)

Pro umgesetztem Move: `[EXPLOITS: Wettbewerber X]` Kommentar im Output.

## 5. Create Bullet Points (5x) — Painpoint-driven

**Jeder Bullet Point MUSS einen konkreten Painpoint adressieren.** Lies aus `review-insights.md` die Search-Painpoints (5+ mit Frequenz). Lies aus `keyword-strategie.md` die Painpoint-klassifizierten Keywords. Bei aktivem Kategorie-Skill (z.B. `kategorie-textil-socken`): nutze die Pain-Point-Map.

| Bullet | Focus | Painpoint-Typ | Synergy |
|---|---|---|---|
| BP1 | Transformativer Benefit fuer den **groessten Search-Painpoint** | Top-Painpoint aus Reviews/Keywords | Slot 2 (Lifestyle) |
| BP2 | Zweitgroesster Painpoint — technische Loesung | #2 Painpoint | Slot 3 + 4 |
| BP3 | Dritter Painpoint — Detail/Material | #3 Painpoint | Slot 5 |
| BP4 | Preemptives Einwand-Behandlung | Haeufigster Review-Einwand | Review-Painpoint (Einwand) |
| BP5 | Risk reversal — Garantie, Service, Lieferumfang | — | Slot 6 + 7 |

**Painpoint-Bullet-Formel:**

```
[CAPS ANKER — SCHMERZ ENDLICH GELOEST] — [Mechanismus]. [Konkrete Alltagsszene]. [Emotional payoff]
```

**Beispiel Wandersocken:**

FALSCH (Feature-Liste):
> MERINOWOLLE — 80% Merino, 20% Polyamid, temperaturregulierend, antibakteriell

RICHTIG (Painpoint-Bullet):
> **SCHLUSS MIT NASSEN FUESSEN** — 80% Merinowolle reguliert Temperatur natuerlich. Nach 8 Stunden Wandern bei 25°C fuehlen sich deine Fuesse immer noch trocken an. Kein Wechsel-Sockenpaar mehr noetig.

Pro Bullet MUSS am Anfang (als Kommentar im Output):
```markdown
BP1:
  Painpoint: [Welchen Pain loest dieser Bullet?]
  Quelle: [Reviews X%, Keyword Y, Kategorie-Map]
  Text: [Der tatsaechliche Bullet Point]
```

Per bullet: CAPS anchor + Painpoint-Loesung + konkrete Szene. Max 200 chars. 1-2 keywords naturally.

**Regel:** Wenn du keinen Painpoint fuer einen Bullet benennen kannst — der Bullet ist schwach und muss umgeschrieben werden.

## 6. Backend Keywords

- Max 250 bytes
- No duplicates from title/bullets
- Include: misspellings, synonyms, long-tail variations
- No brand names, ASINs, subjective claims

## 6b. Mobile-First Validation

Nach Erstellung von Titel und Bullets: Mobile-First Validation (siehe Skill `mobile-first-validation`).

Pflicht-Checks:
- [ ] Titel: Ersten 70 Zeichen enthalten Kernbotschaft (iPhone-Vorschau)
- [ ] Alle Bullets <200 Zeichen (sonst Abschnitt auf Mobile)
- [ ] CAPS-Anker in ersten 2-3 Woertern (scanbar auf 320px)
- [ ] Wichtigste Info in den ersten 50 Zeichen jedes Bullets

Ergaenze im Output:
```markdown
## Mobile-First Check
- Titel (erste 70 Zeichen): "[Auszug]" — [PASS/WARN]
- BP1: [X chars] — [PASS/WARN]
- BP2: [X chars] — [PASS/WARN]
- BP3: [X chars] — [PASS/WARN]
- BP4: [X chars] — [PASS/WARN]
- BP5: [X chars] — [PASS/WARN]
```

## 7. Self-Check

- [ ] Title: 150-180 chars, primary keyword in first 70
- [ ] 5 bullet points follow hierarchy
- [ ] Bullet-image synergy verified (if briefing available)
- [ ] Customer language from reviews used (≥3 phrases)
- [ ] All primary keywords placed
- [ ] Backend keywords: no duplicates, ≤250 bytes

## 8. Write Output

Write `listing-texte.md` to `./workspace/{task-id}/`.

## 9. Complete Task — Zwei-Schritt-Protokoll

**PFLICHT: Beide Schritte ausfuehren.**

### 9a. Eigenes Issue done

```
PATCH /api/issues/{issueId}
{
  "status": "done",
  "comment": "Listing-Texte abgeschlossen. Titel: [X] Zeichen. 5 Bullets. Backend: [X] Bytes. Output: listing-texte.md im Workspace."
}
```

### 9b. CEO am Parent-Issue pingen

```
POST /api/issues/{parentIssueId}/comments
{
  "body": "@ceo Phase 2 Task abgeschlossen: Listing-Texte done. Output: listing-texte.md. Alle Phase-2-Tasks pruefen und ggf. Phase 3 starten."
}
```
