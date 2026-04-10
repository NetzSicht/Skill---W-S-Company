# Heartbeat — Content Master

## 1. Check for Tasks

- New listing text assignments from CEO
- Revision requests from Quality-Reviewer
- Updated keyword data or review insights

If no tasks: idle.

## 2. Read Input Documents

Collect from the task workspace:
- `produkt-analyse.md` — Product data, USPs, target audience
- `keyword-strategie.md` — Primary keywords, long-tails, search volume (from Keyword Researcher)
- `review-insights.md` — Customer language, praise, criticism (from Review-Analyst)
- `listing-briefing.md` — Image briefing (if available, for synergy alignment)

## 3. Create Listing Title

Formula: **Brand + Top Intent Phrase + Feature Group + Use Case + Specs**

- 150-180 characters total
- First 70 characters must contain brand + primary keyword (mobile visibility)
- Natural language — no keyword stuffing (Rufus/COSMO penalty)
- Must match what the buyer sees in the Hero Image

## 4. Create Bullet Points (5x)

| Bullet | Focus | Synergy With |
|---|---|---|
| BP1 | Primary USP — transformative benefit | Slot 2 (Lifestyle) + Slot 3 (Infographic) |
| BP2 | Technical superiority — material/quality | Slot 4 (Dimensions) + Slot 5 (Detail) |
| BP3 | Secondary technical benefit | Slot 5 (Detail) |
| BP4 | Preemptive objection handling | Review-Analyst insights |
| BP5 | Risk reversal — guarantee, service, delivery contents | Slot 6 (Package) + Slot 7 (Trust) |

Per bullet point:
- CAPS anchor (2-3 words) + colon + benefit statement
- Feature → Function → Outcome → Emotional feeling
- Max. 200 characters per bullet (mobile readability)
- Include 1-2 keywords naturally per bullet

## 5. Create Product Description (if applicable)

- Extended narrative for below-the-fold
- Supports A+ Content (or replaces it if no Brand Registry)
- Include remaining keywords not covered in title/bullets
- Natural, readable prose — not keyword lists

## 6. Backend Keywords

- Max. 250 bytes
- No duplicates of title/bullet keywords
- Include: misspellings, synonyms, Spanish/English equivalents, long-tail variations
- No brand names, no ASINs, no subjective claims

## 7. Self-Check

- [ ] Title: 150-180 chars, primary keyword in first 70
- [ ] All 5 bullet points follow the hierarchy
- [ ] Bullet-image synergy verified (if briefing available)
- [ ] Customer language from reviews used (at least 3 phrases)
- [ ] All primary keywords placed (title + bullets)
- [ ] Backend keywords: no duplicates, within 250 bytes
- [ ] No forbidden claims (health, "best", "cheapest", etc.)

## 8. Write Output

Write `listing-texte.md` to the task workspace.
