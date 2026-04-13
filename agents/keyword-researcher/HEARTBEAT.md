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

## 2b. Load Category Skill

Read the product category from `produkt-analyse.md`. If a category-specific skill is attached (e.g., `kategorie-textil-socken`), read your agent section BEFORE researching keywords. The category skill provides:
- Category-specific keyword architecture with tier examples
- Seasonal keyword shifts for this product type
- Intent scoring adapted to category buying behavior
- PAN-EU keyword lists per marketplace language

## 3. Read Input

- `produkt-analyse.md` — Product category, USPs, target audience, competitors

## 3b. Check: Research Mode?

If issue description contains **"RESEARCH MODE"**: you are doing a Kategorie-Research for the entire category, NOT a single-product keyword strategy.

### Research Mode — Kategorie-Keywords

1. Identify the top 10 seed keywords for this category (from issue description or common sense).

2. For each seed keyword, run Autocomplete:
   ```
   GET /request?api_key={KEY}&type=autocomplete&search_term={SEED}&amazon_domain=amazon.de
   ```

3. Run Bestsellers for the category:
   ```
   GET /request?api_key={KEY}&type=bestsellers&amazon_domain=amazon.de&category_id={CAT_ID}
   ```

4. For PAN-EU: Repeat Autocomplete for the same seeds in FR, IT, ES, UK:
   ```
   GET /request?api_key={KEY}&type=autocomplete&search_term={SEED_TRANSLATED}&amazon_domain=amazon.fr
   ```

5. Write Sektionen 3.1 - 3.6 of `kategorie-research.md` per template:
   - **3.1 Primaere Suchbegriffe (20)** — Keyword, geschaetztes Volumen, Intent, Wettbewerb
   - **3.2 Long-Tail Goldgruben (20)** — Niedrige Konkurrenz, hoher Intent
   - **3.3 Autocomplete-Analyse** — Seed → Top 5 Vorschlaege
   - **3.4 Saisonale Muster** — Welche Keywords steigen/fallen pro Saison
   - **3.5 PAN-EU Keywords** — Top 5 pro Marktplatz mit Besonderheiten
   - **3.6 Backend-Empfehlungen** — Synonyme, Schreibfehler, fremdsprachig

**Tiefenregel Intent-Scoring (3.1):**
- NICHT raten. Intent aus der Keyword-Struktur ableiten:
  - Generisch ("socken") = Informational (2/10)
  - Kategorie+Gender ("sportsocken herren") = Navigational (5/10)
  - Kategorie+Gender+Feature ("sportsocken herren gepolstert") = Transactional (8/10)
  - Kategorie+Gender+Feature+Groesse ("sportsocken herren 43-46 gepolstert") = Transactional (10/10)
  - Problem-basiert ("socken gegen schweissfuesse") = Solution-seeking (8/10)

**Tiefenregel PAN-EU (3.5):**
- NICHT einfach uebersetzen! Jeder Markt hat eigene Suchgewohnheiten
- FR: "chaussettes" ist Standard, aber "bas" wird auch genutzt
- IT: "calzini" (umgangssprache) vs. "calze" (formeller)
- ES: "calcetines" — aber regionale Varianten beachten

After writing your sections: mark issue as done.

---

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

### Step 4f: Painpoint-Klassifikation

**Wichtig:** Keywords sind nicht nur Suchbegriffe — sie sind Ausdruck eines Problems. Klassifiziere jedes Primary und Secondary Keyword nach dem zugrunde liegenden Painpoint.

| Keyword-Muster | Painpoint-Typ | Beispiel |
|---|---|---|
| `[Produkt]` allein | Kategorie-Browse (kein spezifischer Pain) | "sportsocken" |
| `[Produkt] + [Feature]` | Feature-gesucht (latenter Pain) | "sportsocken gepolstert" |
| `[Produkt] + [Loesungs-Keyword]` | Expliziter Pain | "sportsocken rutschfest", "sportsocken blasenfrei" |
| `[Produkt] + [Negativ-Wort]` | Frustrations-getrieben | "socken ohne naht", "socken ohne gummi" |
| `[Produkt] gegen [Problem]` | Expliziter Pain | "socken gegen schweissfuesse", "socken gegen blasen" |
| `[Problem] + [Loesung]` | Sehr spezifischer Pain | "schwitzige fuesse sommer socken" |
| `bester/beste [Produkt]` | Vergleichs-Shopping | "beste wandersocken test" |
| `[Produkt] fuer [Kontext]` | Kontext-spezifischer Pain | "socken fuer lange flugreisen" |

**Pro Keyword ergaenzen:**

```markdown
| Keyword | Volumen | Intent | Painpoint-Typ | Adressiertes Problem |
|---|---|---|---|---|
| "wandersocken blasenfrei" | Hoch | Transactional | Expliziter Pain | Blasen beim Wandern |
| "merinowolle wandersocken" | Mittel | Navigational | Feature-gesucht | Materialqualitaet (latent: Temperaturregulation) |
| "socken gegen schweissfuesse" | Mittel | Solution | Frustrations-getrieben | Schwitzende Fuesse |
```

**Ableitung fuer Content Master:**

Aus den Keywords mit "Expliziter Pain" und "Frustrations-getrieben" ableitbar:
- **Welche Painpoints treiben die meisten Suchen?**
- **Welche Painpoints werden oft gesucht, aber selten adressiert?** (= Chance)
- **Welche Keywords gehoeren zu welchem Bullet Point?** (Keyword-zu-Pain-zu-BP Mapping)

**Regel:** Wenn ein Kategorie-Skill mit Pain-Point-Map aktiv ist (z.B. `kategorie-textil-socken`) → jedem Keyword den passenden Painpoint aus der Map zuordnen. Wenn ein Keyword zu keinem Painpoint passt: Ist es relevant? Oder nur generisches Kategorie-Rauschen?

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
  "comment": "@ceo Keyword-Strategie abgeschlossen. [X] Primary, [X] Secondary, [X] Long-tail Keywords. Placement-Plan enthalten. Output: keyword-strategie.md im Workspace."
}
```
