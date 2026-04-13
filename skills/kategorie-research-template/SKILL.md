---
name: kategorie-research-template
description: "Template und Anleitung fuer Kategorie-Research. Wird von Produkt-Analyst, Review-Analyst und Keyword Researcher genutzt um eine neue Kategorie systematisch zu erforschen. Output: kategorie-research.md die spaeter in den dauerhaften Kategorie-Skill einfliesst."
---

# Kategorie-Research Template

Dieses Skill wird aktiviert wenn der CEO einen **Kategorie-Research** Task erstellt. Ziel: Eine neue Produktkategorie systematisch erforschen, damit alle Agents bessere Ergebnisse liefern.

**Wann:** Einmalig pro Kategorie, bevor das erste Kundenprojekt in dieser Kategorie startet.
**Wer:** Produkt-Analyst + Review-Analyst + Keyword Researcher arbeiten parallel.
**Output:** `kategorie-research.md` im Workspace — wird danach in einen dauerhaften Kategorie-Skill ueberarbeitet.

---

## Output-Format: kategorie-research.md

```markdown
# Kategorie-Research: [Kategorie-Name]

**Marktplatz:** [amazon.de / PAN-EU / etc.]
**Recherche-Datum:** [Datum]
**Anzahl analysierter Listings:** [X]
**Agents beteiligt:** Produkt-Analyst, Review-Analyst, Keyword Researcher

---

## 1. Marktueberblick (Produkt-Analyst)

### 1.1 Top 15 Listings — Stammdaten

| # | ASIN | Titel | Marke | Preis | Bewertung | Reviews | BSR | FBA |
|---|---|---|---|---|---|---|---|---|
| 1 | [ASIN] | [Titel] | [Marke] | [EUR] | [Sterne] | [Anzahl] | [Rang] | [Ja/Nein] |
| ... | | | | | | | | |

### 1.2 Preis-Analyse

| Segment | Preisrange | Durchschnitt | Marktanteil (geschaetzt) |
|---|---|---|---|
| Budget | [EUR-EUR] | [EUR] | [%] |
| Mid-Range | [EUR-EUR] | [EUR] | [%] |
| Premium | [EUR-EUR] | [EUR] | [%] |

**Preisschwelle:** Ab [EUR] erwarten Kaeufer [bestimmte Qualitaet/Feature].
**Sweet Spot:** [EUR] — bestes Verhaeltnis Preis/Bewertung.

### 1.3 Bild-Analyse der Top 15

| ASIN | Slots genutzt | Slot 1 (Hero) | Slot 2 | Slot 3 | Slot 4 | Slot 5 | Slot 6 | Slot 7 |
|---|---|---|---|---|---|---|---|---|
| [ASIN] | [X/7] | [Typ] | [Typ] | [Typ] | [Typ] | [Typ] | [Typ] | [Typ] |

**Bild-Typen Codierung:** H=Hero, L=Lifestyle, I=Infografik, D=Dimension, M=Material, P=Pack/Lieferumfang, V=Vergleich, G=Groessentabelle, T=Trust/Zertifikat

**Dominante Muster:**
- [X von 15] nutzen alle 7 Slots
- [X von 15] zeigen [bestimmten Bildtyp] in Slot 2
- [X von 15] haben Groessentabelle
- [X von 15] nutzen Infografiken

**Visuelle Luecken (was KEINER zeigt):**
1. [Luecke 1 — z.B. "Kein Listing zeigt das Material in Nahaufnahme"]
2. [Luecke 2]
3. [Luecke 3]

**Haeufigste Bild-Fehler:**
1. [Fehler 1 — z.B. "Flat-Lay statt Tragebild"]
2. [Fehler 2]

### 1.4 Titel-Analyse der Top 15

| Muster | Haeufigkeit | Beispiel |
|---|---|---|
| [Titel-Element 1] | [X/15] | "[Beispiel]" |
| [Titel-Element 2] | [X/15] | "[Beispiel]" |

**Dominante Titel-Formel:** [Brand] + [was] + [wie viel] + [fuer wen] + [Hauptbenefit]
**Was fehlt in den meisten Titeln:** [Element das differenzieren koennte]

### 1.5 Bullet-Point-Analyse der Top 15

**Haeufigste BP1-Themen:** [X/15 schreiben ueber...]
**Haeufigste BP2-Themen:** [...]
**Gemeinsame Schwaechen:**
1. [z.B. "12 von 15 listen nur Features, keine Benefits"]
2. [z.B. "Kein Listing adressiert das Top-Einwand-Thema aus Reviews"]

### 1.6 A+ Content Analyse

| Typ | Haeufigkeit |
|---|---|
| Kein A+ | [X/15] |
| Basic A+ | [X/15] |
| Premium A+ | [X/15] |
| Brand Story | [X/15] |

**Beste A+ Module in der Kategorie:**
1. [Was funktioniert gut]
2. [Was funktioniert gut]

**A+ Luecken:**
1. [Was keiner macht aber sollte]

---

## 2. Kundenstimmen-Analyse (Review-Analyst)

### 2.1 Aggregierte Review-Analyse (ueber alle Top 15)

**Gesamt analysierte Reviews:** [X]
**Durchschnittliche Bewertung der Kategorie:** [X.X Sterne]

### 2.2 Top-Lob (was Kaeufer lieben)

| # | Thema | Haeufigkeit (gesamt) | Typische Formulierung | Slot/BP-Empfehlung |
|---|---|---|---|---|
| 1 | [Thema] | [X Nennungen / X%] | "[exaktes Zitat]" | [Slot X / BP Y] |
| 2 | | | | |
| 3 | | | | |
| 4 | | | | |
| 5 | | | | |
| 6 | | | | |
| 7 | | | | |
| 8 | | | | |
| 9 | | | | |
| 10 | | | | |

### 2.3 Top-Kritik (was Kaeufer hassen)

| # | Thema | Haeufigkeit | Typische Formulierung | Wie adressieren |
|---|---|---|---|---|
| 1 | [Thema] | [X Nennungen / X%] | "[exaktes Zitat]" | [Slot X / BP Y / Vermeiden] |
| 2 | | | | |
| ... bis 10 | | | | |

### 2.4 Einwand-Cluster

| Cluster | Einzelne Einwaende | Gesamt-Haeufigkeit | Kritikalitaet |
|---|---|---|---|
| [z.B. "Passform"] | "zu eng", "rutscht", "faellt klein aus" | [X%] | [Hoch/Mittel/Niedrig] |
| [z.B. "Haltbarkeit"] | "Loch", "Pilling", "duenn" | [X%] | |
| [z.B. "Groesse"] | "Tabelle stimmt nicht", "zwischen Groessen" | [X%] | |

### 2.5 Kunden-Vokabular-Bank

| Kategorie | Phrasen (exakte Kunden-Zitate) |
|---|---|
| **Positiv-Passform** | "[Phrase 1]", "[Phrase 2]", "[Phrase 3]", ... |
| **Positiv-Material** | "[Phrase 1]", "[Phrase 2]", ... |
| **Positiv-Haltbarkeit** | ... |
| **Positiv-Preis-Leistung** | ... |
| **Negativ-Einwaende** | ... |
| **Kauf-Trigger** | "[direkt nachbestellt]", "[als Geschenk]", ... |

**Minimum:** 20 Phrasen gesamt, mindestens 3 pro Kategorie.

### 2.6 Q&A-Luecken

| Haeufigste Frage | Haeufigkeit | Beantwortet in Listings? | Sollte beantwortet werden in |
|---|---|---|---|
| [Frage 1] | [X Nennungen] | [Ja/Nein/Schlecht] | [Slot X / BP Y / A+ Modul] |
| [Frage 2] | | | |
| ... bis 10 | | | |

### 2.7 Kaeufer-Personas (aus Review-Profilen)

| Persona | Anteil (geschaetzt) | Kauftreiber | Typische Sprache |
|---|---|---|---|
| [z.B. "Sportler"] | [X%] | [Feature] | "[Zitat]" |
| [z.B. "Geschenk-Kaeufer"] | [X%] | [Preis/Optik] | "[Zitat]" |

### 2.8 Search-Painpoints (was Kaeufer zur Suche getrieben hat)

**Kritische Sektion.** Extrahiere diese aus Solution-Statements in positiven Reviews ("endlich keine X mehr", "nie wieder Y", "genau fuer Z gesucht"). Siehe Review-Analyst HEARTBEAT Step 4f fuer Methode.

| # | Search-Painpoint | Haeufigkeit | Solution-Statement (Zitat) | Vermuteter Such-Kontext | Emotionaler Trigger |
|---|---|---|---|---|---|
| 1 | [z.B. "Blasen beim Wandern"] | [X von Y Reviews] | "[exaktes Review-Zitat]" | [Wanderer mit Blasenproblem auf mehrtaegigen Touren] | "Nie wieder mit Pflaster wandern" |
| 2 | | | | | |
| 3 | | | | | |
| 4 | | | | | |
| 5 | | | | | |
| ... bis mind. 10 | | | | | |

**Painpoint → Adressierungs-Empfehlung:**

| Painpoint | Empfohlene Slot-Platzierung | Empfohlener Bullet Point | Keyword-Empfehlung |
|---|---|---|---|
| [Painpoint 1] | [Slot X: Typ] | [BPn: Thema] | [Keyword-Tier] |
| ... | | | |

**Minimum:** 10 Search-Painpoints. Jeder mit Frequenz, Zitat und Platzierungs-Empfehlung.

---

## 3. Keyword-Landschaft (Keyword Researcher)

### 3.1 Primaere Suchbegriffe (hoechstes Volumen)

| # | Keyword | Geschaetztes Volumen | Intent | Wettbewerb |
|---|---|---|---|---|
| 1 | [Keyword] | [Hoch/Mittel/Niedrig] | [Trans./Navig./Info.] | [Hoch/Mittel/Niedrig] |
| ... bis 20 | | | | |

### 3.2 Long-Tail Goldgruben (niedrige Konkurrenz, hoher Intent)

| # | Keyword | Warum wertvoll |
|---|---|---|
| 1 | [z.B. "wandersocken merino damen 39-42 blasenschutz"] | Sehr spezifisch, kaufbereit, wenig Wettbewerb |
| ... bis 20 | | |

### 3.3 Autocomplete-Analyse

| Seed-Keyword | Top Autocomplete-Vorschlaege |
|---|---|
| [Hauptkeyword] | 1. [...], 2. [...], 3. [...], 4. [...], 5. [...] |
| [Variation 1] | 1. [...], 2. [...], ... |
| [Variation 2] | 1. [...], 2. [...], ... |

### 3.4 Saisonale Muster

| Saison | Keywords die steigen | Keywords die fallen |
|---|---|---|
| Fruehling | [Keywords] | [Keywords] |
| Sommer | | |
| Herbst | | |
| Winter | | |

### 3.5 PAN-EU Keywords (wenn PAN-EU Markt)

| Marktplatz | Top 5 Keywords | Besonderheiten |
|---|---|---|
| DE | [Keywords] | [Anmerkung] |
| FR | [Keywords] | |
| IT | [Keywords] | |
| ES | [Keywords] | |
| UK | [Keywords] | |
| NL | [Keywords] | |

### 3.6 Backend-Keyword-Empfehlungen

```
[Komma-separierte Liste: Synonyme, Schreibfehler, fremdsprachige Begriffe, 
 Anlassbezogen, Material-Synonyme, Funktions-Keywords]
```

---

## 4. Synthese: Kategorie-Strategie (alle Agents)

### 4.1 Die 5 wichtigsten Erkenntnisse

1. **[Erkenntnis 1]** — [Beleg: X/15 Listings, Y% Reviews]
2. **[Erkenntnis 2]** — [Beleg]
3. **[Erkenntnis 3]** — [Beleg]
4. **[Erkenntnis 4]** — [Beleg]
5. **[Erkenntnis 5]** — [Beleg]

### 4.2 Differenzierungs-Chancen

| Chance | Warum | Aufwand |
|---|---|---|
| [Chance 1 — z.B. "Kein Listing zeigt Materialnahaufnahme"] | [X/15 verpassen das] | [Niedrig/Mittel/Hoch] |
| [Chance 2] | | |
| [Chance 3] | | |

### 4.3 Empfohlene Slot-Sequenz fuer diese Kategorie

| Slot | Bildtyp | Begruendung aus Research |
|---|---|---|
| 1 | [Typ] | [X/15 machen es so, Top-Performer zeigen...] |
| 2 | [Typ] | [Reviews zeigen dass Kaeufer X brauchen] |
| 3 | [Typ] | [Keywords zeigen dass Y gesucht wird] |
| 4 | [Typ] | [Einwand Z muss hier adressiert werden] |
| 5 | [Typ] | |
| 6 | [Typ] | |
| 7 | [Typ] | |

### 4.4 Empfohlene Titel-Formel fuer diese Kategorie

```
[Formel basierend auf Titel-Analyse der Top 15]
Beispiel: [konkretes Beispiel]
```

### 4.5 Kritische Einwaende die JEDES Listing adressieren muss

1. **[Einwand]** — [X% der Reviews] — adressieren in: [Slot/BP]
2. **[Einwand]** — [X%] — adressieren in: [Slot/BP]
3. **[Einwand]** — [X%] — adressieren in: [Slot/BP]
```

---

## Rainforest API — Research-Requests

### Produkt-Analyst: Kategorie-Scan

```
# Schritt 1: Top-Listings der Kategorie finden
GET /request?api_key={KEY}&type=search&search_term={HAUPTKEYWORD}&amazon_domain=amazon.de&sort_by=relevance&number_of_results=15&exclude_sponsored=true

# Schritt 2: Fuer jede ASIN die Produktdaten ziehen
GET /request?api_key={KEY}&type=product&asin={ASIN}&amazon_domain=amazon.de

# Schritt 3: Angebote vergleichen
GET /request?api_key={KEY}&type=offers&asin={ASIN}&amazon_domain=amazon.de

# Credit-Budget: ~35 Requests (1 Search + 15 Products + 15 Offers + 4 Buffer)
```

### Review-Analyst: Kategorie-Reviews

```
# Fuer jede der Top 15 ASINs:

# Positive Reviews (Top-Lob extrahieren)
GET /request?api_key={KEY}&type=reviews&asin={ASIN}&amazon_domain=amazon.de&star_rating=positive&sort_by=most_helpful

# Kritische Reviews (Einwaende extrahieren)
GET /request?api_key={KEY}&type=reviews&asin={ASIN}&amazon_domain=amazon.de&star_rating=critical&sort_by=most_helpful

# Q&A
GET /request?api_key={KEY}&type=questions&asin={ASIN}&amazon_domain=amazon.de

# Credit-Budget: ~45 Requests (15x positive + 15x critical + 15x Q&A)
```

### Keyword-Researcher: Kategorie-Keywords

```
# Hauptkeyword + 10 Variationen durch Autocomplete
GET /request?api_key={KEY}&type=autocomplete&search_term={KEYWORD}&amazon_domain=amazon.de
# x10 Seeds = 10 Requests

# Bestseller der Kategorie
GET /request?api_key={KEY}&type=bestsellers&amazon_domain=amazon.de&category_id={CAT_ID}
# 1 Request

# Credit-Budget: ~15 Requests
```

### Gesamt-Budget pro Kategorie-Research: ~95 Requests
