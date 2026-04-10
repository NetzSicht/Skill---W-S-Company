---
name: rainforest-api
description: "Rainforest API (Traject Data) fuer Amazon-Datenabfragen. Liefert Produktdaten, Reviews, Suchergebnisse, Q&A, Angebote, Bestseller-Ranks und Autocomplete. Wird von Produkt-Analyst, Keyword Researcher, Review-Analyst und PPC Specialist genutzt. API-Key liegt als Environment-Variable RAINFOREST_API_KEY."
---

# Rainforest API — Amazon-Datenquelle

Die Rainforest API (trajectdata.com) ist die primaere Datenquelle fuer alle Amazon-Recherchen bei NetzSicht. Kein Scraping — strukturierte API-Abfragen mit 99.9% Datengenauigkeit.

**API-Key:** Liegt als Environment-Variable `RAINFOREST_API_KEY`
**Base-URL:** `https://api.rainforestapi.com/request`
**Format:** GET-Requests mit Query-Parametern, Antwort als JSON

---

## Welcher Agent nutzt welche Endpoints

| Agent | Endpoints | Wofuer |
|---|---|---|
| **Produkt-Analyst** | `product`, `offers`, `also_bought` | Produktdaten, Wettbewerber-Preise, verwandte Produkte |
| **Keyword Researcher** | `search`, `autocomplete`, `bestsellers` | Keyword-Discovery, Suchvolumen-Proxy, Kategorie-Rankings |
| **Review-Analyst** | `reviews`, `questions` | Bewertungstexte, Q&A, Kundenstimmen |
| **PPC Specialist** | `search`, `bestsellers`, `stock_estimation` | Wettbewerber-Positionen, Kategorie-Trends, Lagerbestaende |

---

## Gemeinsame Parameter (alle Requests)

```
api_key={RAINFOREST_API_KEY}    # Pflicht
amazon_domain=amazon.de          # Marktplatz (amazon.de, amazon.com, etc.)
type={endpoint}                  # Welcher Endpoint (product, search, reviews, etc.)
```

---

## Endpoint 1: Product — Produktdaten abrufen

**Wann:** Produkt-Analyst braucht Stammdaten zu einer ASIN

```
GET /request?api_key={KEY}&type=product&asin={ASIN}&amazon_domain=amazon.de
```

**Liefert:**
- Titel, Marke, Kategorie-Pfad
- Preis (aktuell, UVP, Sale)
- Alle Bilder (URLs + Dimensionen)
- Bullet Points (Feature-Liste)
- Produktbeschreibung
- Bewertung (Sterne, Anzahl, Breakdown 1-5)
- Verfuegbarkeit, FBA/FBM
- Abmessungen, Gewicht, Material
- Varianten (Farben, Groessen)
- Bestseller-Rank in Kategorie
- Haeufig zusammen gekauft

**Relevante Felder fuer Interface A (Produkt-Analyse):**

| API-Feld | Mapping zu Interface A |
|---|---|
| `product.title` | Produktname |
| `product.brand` | Marke |
| `product.categories` | Kategorie |
| `product.buybox_winner.price` | Preis |
| `product.main_image` + `product.images` | Bestehende Bilder |
| `product.feature_bullets` | USP-Kandidaten |
| `product.description` | Produktbeschreibung |
| `product.rating` + `product.ratings_total` | Bewertungsueberblick |
| `product.dimensions` + `product.weight` | Abmessungen |
| `product.variants` | Varianten |
| `product.bestsellers_rank` | BSR (Kategorie-Position) |

---

## Endpoint 2: Search — Suchergebnisse & Wettbewerber

**Wann:** Keyword Researcher sucht Wettbewerber, PPC Specialist prueft Positionen

```
GET /request?api_key={KEY}&type=search&search_term={KEYWORD}&amazon_domain=amazon.de&sort_by=relevance
```

**Optionale Parameter:**
- `number_of_results=50` — Anzahl Ergebnisse
- `page=1` — Ergebnisseite
- `max_page=3` — Mehrere Seiten in einem Request
- `exclude_sponsored=true` — Nur organische Ergebnisse
- `sort_by=` — `relevance`, `price_low_to_high`, `price_high_to_low`, `average_review`, `most_recent`

**Liefert pro Ergebnis:**
- ASIN, Titel, Link
- Position im Ranking
- Preis, Bewertung, Rezensionsanzahl
- Prime-Status
- Produktbild
- Sponsored/Promoted Badge
- Verkaufszahlen-Indikatoren

**Fuer Wettbewerber-Analyse:**
```
# Top 10 organische Ergebnisse fuer Hauptkeyword
GET /request?api_key={KEY}&type=search&search_term=heissluftfritteuse+xxl&amazon_domain=amazon.de&number_of_results=10&exclude_sponsored=true
```

---

## Endpoint 3: Reviews — Bewertungstexte

**Wann:** Review-Analyst extrahiert Kundenstimmen

```
GET /request?api_key={KEY}&type=reviews&asin={ASIN}&amazon_domain=amazon.de&sort_by=most_recent
```

**Optionale Parameter:**
- `sort_by=` — `most_recent`, `most_helpful`
- `star_rating=` — Filter: `all_stars`, `five_star`, `four_star`, `three_star`, `two_star`, `one_star`, `positive` (4-5), `critical` (1-3)
- `verified_purchases_only=true` — Nur verifizierte Kaeufe
- `page=1` — Paginierung

**Liefert pro Review:**
- Volltext der Bewertung
- Titel
- Sternebewertung (1-5)
- Verifizierter Kauf (ja/nein)
- Hilfreiche Stimmen
- Datum
- Reviewer-Name

**Strategie fuer Review-Analyse:**
```
# Schritt 1: Kritische Reviews (Einwaende finden)
GET ...&type=reviews&asin={ASIN}&star_rating=critical&sort_by=most_helpful

# Schritt 2: Top-Reviews (Lob finden)
GET ...&type=reviews&asin={ASIN}&star_rating=positive&sort_by=most_helpful

# Schritt 3: Neueste Reviews (aktuelle Stimmung)
GET ...&type=reviews&asin={ASIN}&sort_by=most_recent

# Fuer jeden Wettbewerber wiederholen
```

---

## Endpoint 4: Questions — Q&A Sektion

**Wann:** Review-Analyst sucht unbeantwortete Kundenfragen

```
GET /request?api_key={KEY}&type=questions&asin={ASIN}&amazon_domain=amazon.de&search_term={optional}
```

**Liefert (max. 20 pro Request):**
- Fragetext
- Antworttext
- Datum
- Fragesteller / Antwortender

**Fuer Listing-Luecken-Analyse:** Jede haeufig gestellte Frage = ein Slot, Bullet Point oder A+ Modul das die Antwort liefern sollte.

---

## Endpoint 5: Autocomplete — Keyword-Discovery

**Wann:** Keyword Researcher sucht verwandte Suchbegriffe

```
GET /request?api_key={KEY}&type=autocomplete&search_term={KEYWORD}&amazon_domain=amazon.de
```

**Liefert:**
- Array von Suchvorschlaegen
- Typ (Keyword, Produkt, Kategorie)
- Korrektur-Flag (Tippfehler erkannt?)

**Strategie: Seed → Expand**
```
# Seed-Keyword eingeben
GET ...&type=autocomplete&search_term=heissluftfritteuse

# Liefert z.B.: "heissluftfritteuse xxl", "heissluftfritteuse testsieger",
# "heissluftfritteuse edelstahl", "heissluftfritteuse mit sichtfenster"

# Jeden Vorschlag als neuen Seed nutzen fuer Long-Tail
GET ...&type=autocomplete&search_term=heissluftfritteuse+xxl
# Liefert: "heissluftfritteuse xxl 8 liter", "heissluftfritteuse xxl family", ...
```

---

## Endpoint 6: Offers — Wettbewerber-Preise

**Wann:** Produkt-Analyst vergleicht Preise und Angebote

```
GET /request?api_key={KEY}&type=offers&asin={ASIN}&amazon_domain=amazon.de
```

**Liefert pro Anbieter:**
- Verkaeufer-Name, Rating, Bewertungsanzahl
- Preis (inkl. Versand)
- Prime-Status
- Zustand (neu/gebraucht)
- Lieferzeit

---

## Endpoint 7: Bestsellers — Kategorie-Rankings

**Wann:** PPC Specialist / Keyword Researcher analysieren Kategorie-Trends

```
GET /request?api_key={KEY}&type=bestsellers&amazon_domain=amazon.de&category_id={CATEGORY_ID}
```

**Auch verfuegbar:**
- `type=new_releases` — Neuheiten
- `type=movers_and_shakers` — Groesste Ranking-Veraenderungen

---

## Budget & Credits-Planung

| Plan | Preis/Monat | Credits | Pro Request |
|---|---|---|---|
| Starter | $83 | 10.000 | $0.012 |
| Production | $375 | 250.000 | $0.003 |
| BigData | $1.000 | 1.000.000 | $0.002 |

**Typischer Verbrauch pro Listing-Projekt:**

| Aktion | Requests | Credits ca. |
|---|---|---|
| Produktdaten (eigenes Produkt) | 1 | 1 |
| Wettbewerber-Produkte (5x) | 5 | 5 |
| Eigene Reviews (3 Seiten) | 3 | 3 |
| Wettbewerber-Reviews (5x3) | 15 | 15 |
| Q&A (eigenes + 5 Wettbewerber) | 6 | 6 |
| Keyword-Suche (10 Keywords) | 10 | 10 |
| Autocomplete (20 Seeds) | 20 | 20 |
| Offers (5 Wettbewerber) | 5 | 5 |
| **Gesamt pro Projekt** | **~65** | **~65** |

→ Starter-Plan (10.000 Credits) = ~150 Listing-Projekte/Monat

---

## Credit-Check vor Abfragen

Vor groesseren Research-Sessions den Account-Stand pruefen:

```
GET https://api.rainforestapi.com/account?api_key={KEY}
```

Liefert: Credits used, remaining, reset date. Kostet keine Credits.

---

## Fehlerbehandlung

| HTTP Status | Bedeutung | Aktion |
|---|---|---|
| 200 | Erfolg | Daten verarbeiten |
| 400 | Falsche Parameter | Request pruefen |
| 401 | Ungültiger API-Key | Key pruefen |
| 404 | ASIN nicht gefunden | ASIN/Marktplatz pruefen |
| 429 | Rate Limit | 1 Sekunde warten, retry |
| 500 | Server-Fehler | Retry nach 5 Sekunden |

---

## Wichtig fuer alle Agents

1. **Immer `amazon_domain` setzen** — Default ist `amazon.com`, fuer DE-Markt immer `amazon.de`
2. **Credits sparen:** Nur abfragen was gebraucht wird. Nicht pauschal alles ziehen.
3. **Keine Bulk-Abfragen ohne Grund** — 65 Requests pro Projekt reichen fuer eine vollstaendige Analyse
4. **Account-Check** vor grossen Sessions — Credits sind endlich
5. **Daten zwischenspeichern** — Gleiche ASIN nicht mehrfach abfragen innerhalb eines Projekts
