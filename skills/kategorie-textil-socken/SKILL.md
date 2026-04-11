---
name: kategorie-textil-socken
description: "Tiefes Kategorie-Wissen fuer Socken-Listings auf Amazon (PAN-EU). Enthält agent-spezifische Anweisungen fuer: Produkt-Analyst, Listing-Briefer, Content Master, Keyword Researcher, Review-Analyst, Quality-Reviewer und A+ Content Designer. Deckt alle Sockentypen ab: Sport, Business, Alltag, Kompression, Wander, Thermo, Sneaker, Kinder. Alle Preissegmente (Budget/Multipack, Mid-Range, Premium). Aktivieren wenn das Produkt Socken sind."
---

# Kategorie-Skill: Textil — Socken

Dieser Skill wird aktiviert wenn das Listing-Projekt **Socken** betrifft. Er enthaelt agentenspezifische Tiefenregeln die ueber das generische Textil-Wissen hinausgehen.

**Maerkte:** PAN-EU (DE, FR, IT, ES, NL, PL, SE + UK)
**Preissegmente:** Budget/Multipack | Mid-Range | Premium/Funktional

---

## Socken-Taxonomie: Subtypen und ihre Besonderheiten

Jeder Subtyp hat eigene Kauftreiber, Einwaende und visuelle Anforderungen. Der Produkt-Analyst muss den Subtyp in Phase 1 identifizieren — alle nachfolgenden Agents passen ihre Arbeit darauf an.

| Subtyp | Kauftreiber | Haeufigste Einwaende | Visuelle Prioritaet |
|---|---|---|---|
| **Sportsocken (Lauf/Fitness)** | Polsterung, Feuchtigkeitsmanagement, Passform | "Rutschen beim Laufen", "Zu duenn an der Ferse", "Schwitzen trotzdem" | Polsterzonen-Infografik, Fuss-am-Schuh-Szene |
| **Wandersocken** | Merinowolle, Blasenpraevention, Polsterung, Hoehe | "Zu warm im Sommer", "Pilling nach 3x Waschen", "Druckstellen am Schienbein" | Materialnahaufnahme (Wolle), Wanderszene, Hoehe-Vergleich |
| **Businesssocken** | Optik, Duennheit, Langlebigkeit, Farbtreue | "Gummibund schneidet ein", "Farbe verblasst", "Rutschen runter" | Schuh-Kombination, Farbpalette, Bunddetail |
| **Alltagssocken** | Komfort, Preis-Leistung, Waschbestaendigkeit | "Loecher nach 2 Monaten", "Naht drueckt an den Zehen", "Laufen ein" | Multipack-Arrangement, Waschsymbol, Nahtdetail |
| **Sneakersocken/Invisible** | Unsichtbarkeit, Anti-Rutsch Silikonpad, Passform | "Rutschen in den Schuh", "Silikonpad loest sich", "Sichtbar ueber Schuhrand" | Schuh-Schnitt-Ansicht, Silikonpad-Detail, "Unsichtbar"-Beweis |
| **Kompressionssocken** | mmHg-Staerke, medizinischer Nutzen, Reise/Sport | "Zu eng zum Anziehen", "Helfen nicht", "Falsche Groesse bestellt" | Kompressionsgradienten-Grafik, Anzieh-Anleitung, Groessentabelle |
| **Thermosocken** | Waerme, Material (Wolle/Fleece), Dicke | "Passen nicht in Schuhe", "Zu dick", "Jucken" | Schichtaufbau-Grafik, Temperaturbereich, Material-Nahaufnahme |
| **Kindersocken** | Rutschfeste Sohle (ABS), Schadstofffrei, Groesse | "Fallen nach 1x Waschen aus", "ABS-Noppen loesen sich", "Groesse stimmt nicht" | ABS-Noppen-Detail, Oeko-Tex Label, Groessentabelle |
| **Zehensocken** | Blasenpraevention, Barfussgefuehl, Material | "Zehen passen nicht", "Unbequem zwischen den Zehen" | Zehen-Passform-Detail, Vergleich normal vs. Zehe |

---

## Fuer den Produkt-Analyst

### Phase 1: Stammdaten — Socken-spezifisch erweitert

Zusaetzlich zu den Standard-Stammdaten MUESSEN erhoben werden:

| Datenpunkt | Warum kritisch | Wo zu finden |
|---|---|---|
| **Subtyp** (aus Tabelle oben) | Bestimmt die gesamte Strategie | Produktbeschreibung, Titel |
| **Materialzusammensetzung** (exakt, in %) | Kaufentscheidend — Baumwolle vs. Merinowolle vs. Synthetik | Etikett, Produktdaten, API `product.specifications` |
| **Groessensystem** | EU vs. US vs. UK — PAN-EU braucht alle drei | Groessentabelle, API `product.variants` |
| **Groessenbereich** | z.B. 35-38 / 39-42 / 43-46 — oder Einheitsgroesse | API `product.variants` |
| **Packungsgroesse** | 1er, 3er, 5er, 6er, 10er, 12er Pack | Titel, API `product.title` |
| **Hoehe** | Sneaker/Invisible, Quarter, Crew, Knielaenge | Bilder, Beschreibung |
| **Polsterzonen** | Ferse, Ballen, Sohle, Rist — wo gepolstert? | Infografiken, Beschreibung |
| **Besondere Features** | Anti-Rutsch, Kompression (mmHg), Mesh-Belueftung, Nahtfrei, ABS-Noppen | Bullets, Beschreibung |
| **Pflegehinweise** | Waschtemperatur, Trockner ja/nein | Etikett, Beschreibung |
| **Zertifizierungen** | Oeko-Tex 100, GOTS, Fair Trade, Bluesign | Bilder, Beschreibung |

### Phase 3: USPs — Socken-Bewertungsmatrix

USPs bei Socken MUESSEN gegen diese Matrix geprueft werden:

| USP-Kandidat | Prueffrage | Schwellenwert | Beispiel |
|---|---|---|---|
| Material | Wird es in ≥15% der positiven Reviews erwaehnt? | ≥15% | "Merinowolle fuehlt sich toll an" (23% der 5-Sterne Reviews) |
| Passform | Ist es ein Differenzierungsmerkmal vs. Wettbewerb? | Ja/Nein + Beleg | "Anatomisch geformt — links/rechts unterschiedlich" (Wettbewerber haben das nicht) |
| Haltbarkeit | Adressiert es den #1 Einwand der Kategorie? | In Top-3 Kritikpunkten? | "Verstaerkte Ferse und Zehen" adressiert "Loecher nach 2 Monaten" |
| Packungsgroesse/Preis | Ist der Stueckpreis konkurrenzfaehig? | Stueckpreis vs. Top 5 Wettbewerber | "6er Pack fuer 14.99 = 2.50/Paar vs. Wettbewerb 3.20/Paar" |

**Regel:** Jeder USP muss die Feature → Funktion → Outcome → Gefuehl Kette haben:
```
FALSCH: "80% gekämmte Baumwolle"
RICHTIG: "80% gekaemmte Baumwolle → weicher als Standard-Baumwolle 
          → kein Kratzen auch nach 8h Tragen → du vergisst dass du sie anhast"
```

### Phase 6: Wettbewerber — Socken-spezifische Analyse

Fuer JEDEN Wettbewerber zusaetzlich erfassen:

| Aspekt | Was genau | Beispiel |
|---|---|---|
| **Packungsgroesse** | Stueckpreis berechnen! | 3er Pack 12.99 = 4.33/Paar |
| **Material-Vergleich** | Exakte Zusammensetzung nebeneinander | Wir: 80% Merino, Sie: 60% Polyester |
| **Groessen-Abdeckung** | Welche Groessen fehlen beim Wettbewerb? | Wettbewerber hat keine 47-50 |
| **Review-Schwaechen** | Top-3 Kritik aus deren Reviews | "Naht drueckt", "Farbe verblasst", "Laufen ein" |
| **Bild-Fehler** | Was zeigen sie NICHT? | Kein Materialbild, keine Groessentabelle, kein Tragebild |

### Phase 7: Kundenstimmen — Socken-typische Muster

**Bei Socken immer nach diesen Mustern suchen:**

| Muster | Suchbegriffe in Reviews | Haeufigkeit-Schwelle |
|---|---|---|
| **Passform-Probleme** | "zu eng", "zu weit", "rutscht", "schneidet ein", "Gummibund" | ≥8% = kritisch |
| **Haltbarkeit** | "Loch", "Loecher", "duenn", "Pilling", "Fusseln", "nach X Waeschen" | ≥10% = muss adressiert werden |
| **Groessen-Verwirrung** | "faellt kleiner aus", "faellt groesser aus", "Groessentabelle stimmt nicht" | ≥5% = Groessentabelle ueberarbeiten |
| **Material-Gefuehl** | "kratzt", "weich", "kuschelig", "schwitzig", "atmungsaktiv" | Immer extrahieren — Kernsprache |
| **Waschverhalten** | "eingelaufen", "Farbe verblasst", "Form verloren" | ≥5% = Pflegehinweis prominent |
| **Naht-Probleme** | "Naht drueckt", "Naht am Zeh", "spuerbare Naht" | ≥5% = nahtfrei als USP oder adressieren |
| **Geruch** | "riecht", "stinkt", "Geruch nach Waschen", "antibakteriell" | Relevant wenn >3 Nennungen |

---

## Fuer den Listing-Briefer

### Slot-Strategie: Socken

**Die Standard-Socken-Sequenz:**

| Slot | Bildtyp | Kernbotschaft | Warum genau HIER |
|---|---|---|---|
| **1** | **Hero: Paar/Pack auf Weiss** | "Das sind die Socken — Menge, Farbe, Hoehe sofort klar" | Packungsgroesse und Hoehe muessen im Thumbnail erkennbar sein. Bei Multipacks ALLE Socken zeigen. |
| **2** | **Tragebild am Fuss** | "So sitzen sie an einem echten Fuss" | Socken-Kaeufer brauchen sofort die Passform-Bestaetigung. KEIN Flat-Lay — das zeigt nicht wie sie SITZEN. |
| **3** | **Material & Feature Infografik** | "Das macht diese Socken besser" | Polsterzonen, Material-Zusammensetzung, Belueftungszonen — als Infografik mit Produkt im Zentrum. |
| **4** | **Groessentabelle + Passform** | "So findest du deine Groesse" | Socken-Retouren-Grund #1 ist falsche Groesse. EU + UK Groessen PFLICHT bei PAN-EU. |
| **5** | **Material-Nahaufnahme** | "So fuehlt sich das an" | Textur zeigen: Strick, Polsterung, Bund, Naht. Muss "haptisch" wirken. |
| **6** | **Lieferumfang / Farbvarianten** | "Das bekommst du / Diese Farben gibt es" | Bei Multipacks: Alle Teile auslegen. Bei Farbvarianten: Alle nebeneinander. |
| **7** | **Vergleich / Trust** | "Warum diese und nicht die guenstigen?" | Materialvergleich (nicht Markenvergleich). Oeko-Tex, Kundenzufriedenheit, Garantie. |

### Slot-Anpassungen nach Subtyp

| Subtyp | Slot 2 aendern zu | Slot 3 fokus | Zusatz |
|---|---|---|---|
| **Sportsocken** | Fuss im Sportschuh (Laufszene) | Polsterzonen + Feuchtigkeitsmanagement | Slot 5: Schweisstest/Mesh-Detail |
| **Wandersocken** | Fuss im Wanderstiefel (Outdoor-Szene) | Merino-Vorteile + Anti-Blasen | Slot 5: Wollstruktur-Makro |
| **Businesssocken** | Fuss im Businessschuh (Buero/Meeting) | Feinheit + Farbtreue | Slot 6: Farbpalette alle Varianten |
| **Sneakersocken** | Fuss im Sneaker — Unsichtbarkeits-Beweis | Anti-Rutsch Silikonpad | Slot 5: Silikonpad Nahaufnahme |
| **Kompressionssocken** | Tragebild Wade (Kompressionseffekt sichtbar) | mmHg-Grafik + Wirkungszonen | Slot 4: Anzieh-Anleitung |
| **Thermosocken** | Fuss in Winterszene | Schichtaufbau-Querschnitt | Slot 5: Dicken-Vergleich im Schuh |
| **Kindersocken** | Kind in Socken auf Boden (ABS sichtbar) | Schadstofffrei + ABS-Noppen | Slot 5: ABS-Detail + Oeko-Tex |

### Tiefenregeln pro Slot

**Slot 1 — Hero bei Socken:**
- Bei Multipacks: ALLE Socken im Bild, geometrisch angeordnet (Knolling oder Faecher)
- Hoehe muss erkennbar sein (Quarter vs. Crew vs. Knie) — im Thumbnail bei 150px!
- Bei Farbvarianten: Hauptfarbe prominent, Varianten angedeutet
- FEHLER vermeiden: Einzelne Socke auf Weiss → sieht billig aus. Immer Paar oder Pack.

**Slot 2 — Tragebild bei Socken:**
- IMMER am echten Fuss, NICHT Flat-Lay (Flat-Lay zeigt nicht Passform)
- Fuss-Perspektive: Leicht von oben (45°) damit Rist und Bundhoehe sichtbar
- Bei Sportsocken: Im passenden Schuh, oberer Rand sichtbar
- Bei Sneakersocken: BEWEIS dass sie unsichtbar sind — Schuh an, Socke nicht sichtbar
- Model-Fuss muss zur Zielgruppe passen (Maenner-/Frauen-/Kinderfuss)
- **Gaze Cueing entfaellt** (keine Gesichter) → stattdessen: Kontext-Setting (Laufband, Wanderweg, Schreibtisch)

**Slot 3 — Infografik bei Socken:**
- Socke als zentrales Element, Callout-Lines zu Features
- Max. 5 Callouts (Mobile-Lesbarkeit!)
- Typische Callouts nach Subtyp:

| Subtyp | Callout 1 | Callout 2 | Callout 3 | Callout 4 |
|---|---|---|---|---|
| Sport | Gepolsterte Ferse | Mesh-Belueftung | Flachnaht | Arch Support |
| Wandern | Merino-Faser | Blasenschutz-Zone | Verstaerkte Sohle | Feuchtigkeits-Ableitung |
| Business | Gekaemmte Baumwolle | Handgekettelte Spitze | Flacher Bund | Farbecht |
| Sneaker | Silikonpad | Invisible Cut | Baumwoll-Sohle | Anti-Rutsch |
| Kompression | 15-20 mmHg | Graduierte Kompression | Offene/geschl. Spitze | Reise-geeignet |

**Slot 4 — Groessentabelle bei Socken (PFLICHT bei PAN-EU):**
- MUSS enthalten: EU, UK, US Groessen
- Fusslaenge in cm pro Groesse
- Empfehlung: "Zwischen zwei Groessen? Nimm die groessere."
- Wadenumfang bei kniehohen/Kompressionssocken
- Bei Kindersocken: Alter + Fusslaenge + EU-Groesse

**Slot 5 — Material-Nahaufnahme bei Socken:**
- Strickstruktur muss sichtbar sein (Feinheit bei Business, Robustheit bei Wandern)
- Bund-Detail: Wie breit? Rollt er? Schneidet er ein?
- Naht-Detail: Handgekettelt vs. Maschinennaht — der Unterschied muss fuehlbar werden
- Bei Polsterung: Querschnitt oder Seitenansicht die Dicke zeigt

**Slot 7 — Vergleich bei Socken:**
- NICHT Markenvergleich, sondern Material-Vergleich:
  - "Unsere Socke (80% Merino)" vs. "Typische Socke (60% Polyester)"
- Vergleichskriterien die bei Socken konvertieren:
  1. Material-Qualitaet
  2. Haltbarkeit (Waeschen)
  3. Passform-Garantie
  4. Preis pro Paar
  5. Zertifizierung (Oeko-Tex)
  6. Geruchshemmung

---

## Fuer den Content Master

### Titel-Formel Socken (PAN-EU)

**Deutsch (amazon.de):**
```
[Marke] [Subtyp] [Packungsgroesse] [Geschlecht] — [Material/Hauptfeature] — [Groessenbereich] [Benefit]
```
Beispiele:
- `BRANDX Sportsocken 6 Paar Herren — Gepolstert, Atmungsaktiv — Gr. 39-46 fuer Laufen & Fitness`
- `BRANDX Businesssocken 5 Paar Herren — Gekaemmte Baumwolle, Farbecht — Gr. 39-46`
- `BRANDX Wandersocken 3 Paar — Merinowolle, Blasenschutz — Gr. 35-46 Damen & Herren`
- `BRANDX Sneakersocken 10 Paar Damen — Unsichtbar, Anti-Rutsch Silikon — Gr. 35-42`

**Englisch (amazon.co.uk):**
```
[Brand] [Subtype] [Pack Size] [Gender] — [Material/Feature] — [Size Range] [Benefit]
```

**PAN-EU Regel:** Titel in der Sprache des jeweiligen Marktplatzes. Keywords pro Markt recherchieren — "chaussettes" (FR), "calzini" (IT), "calcetines" (ES).

### Bullet Points — Socken-Hierarchie

| BP | Fokus | Muster | Beispiel |
|---|---|---|---|
| **BP1** | Material + Hauptbenefit | `PREMIUM MATERIAL — [Material]% [Faser] sorgt fuer [Benefit]` | `PREMIUM MERINOWOLLE — 80% Merinowolle reguliert Temperatur natuerlich, haelt warm ohne zu schwitzen und hemmt Geruch auch nach langen Wandertagen` |
| **BP2** | Passform + Komfort | `PERFEKTE PASSFORM — [Feature] fuer [Outcome]` | `PERFEKTE PASSFORM — Anatomisch geformte L/R-Socken mit Arch Support passen sich deinem Fuss an, kein Rutschen, kein Verdrehen den ganzen Tag` |
| **BP3** | Haltbarkeit + Pflege | `LANGLEBIG — [Feature] haelt [wie lange/wie viel]` | `LANGLEBIG — Verstaerkte Ferse und Zehen ueberstehen 50+ Waschgaenge bei 40°C ohne Formverlust, Pilling oder Farbverlust` |
| **BP4** | Einwand adressieren | `[EINWAND ENTKRAEFTEN] — [Loesung]` | `KEIN EINSCHNEIDEN — Der 3cm breite Komfortbund verteilt den Druck gleichmaessig, hinterlässt keine Abdrücke und rutscht trotzdem nicht` |
| **BP5** | Lieferumfang + Garantie | `[PACK] + [GARANTIE/ZERTIFIKAT]` | `6 PAAR IN GESCHENKBOX — Oeko-Tex 100 zertifiziert, schadstofffrei. Passt nicht? 30 Tage kostenlose Ruecksendung` |

### Keyword-Regeln Socken (PAN-EU)

**Pflicht-Keywords im Titel (DE):**
- Subtyp: "Sportsocken" / "Wandersocken" / "Businesssocken" etc.
- Packungsgroesse: "6 Paar" / "3er Pack"
- Geschlecht: "Herren" / "Damen" / "Unisex" / "Kinder"
- Groesse: "Gr. 39-46"

**Typische Long-Tails (DE):**
- "sportsocken herren 43-46 gepolstert"
- "wandersocken merino damen"
- "sneakersocken damen unsichtbar rutschfest"
- "kompressionssocken reise flug"
- "kindersocken anti rutsch abs"
- "businesssocken herren baumwolle schwarz 5er pack"

**Backend-Keywords (DE) — typisch uebersehene:**
- Synonyme: "Struempfe", "Socke", "Socks", "Tennissocken"
- Schreibfehler: "Sockeen", "Sportscoken"
- Anlass: "Geschenk", "Weihnachten", "Vatertag"
- Material-Synonyme: "Wolle", "Merinowolle", "Bambuswolle"
- Funktion: "Schweissfuesse", "Plattfuss", "Senk-Spreizfuss"

**PAN-EU Backend — pro Marktplatz eigene Keywords:**
- DE: "Socken", "Struempfe", "Sportsocken"
- FR: "chaussettes", "chaussettes de sport", "chaussettes randonnee"
- IT: "calzini", "calzini sportivi", "calze"
- ES: "calcetines", "calcetines deportivos"
- NL: "sokken", "sportsokken"

---

## Fuer den Keyword Researcher

### Socken-Keyword-Architektur

**Tier 1 — Primary (Titel + BP1):**
```
[Subtyp] + [Geschlecht] + [Groesse]
Beispiel: "sportsocken herren 43-46"
```

**Tier 2 — Secondary (BP2-5):**
```
[Subtyp] + [Material/Feature]
Beispiel: "wandersocken merinowolle", "sneakersocken anti rutsch"
```

**Tier 3 — Long-Tail (Description, A+):**
```
[Subtyp] + [Geschlecht] + [Feature] + [Anlass/Saison]
Beispiel: "thermosocken herren wolle winter", "laufsocken damen gepolstert marathon"
```

**Tier 4 — Backend:**
```
Synonyme, Schreibfehler, fremdsprachig (PAN-EU), Anlassbezogen
```

### Saisonale Keyword-Schwankungen Socken

| Saison | Keyword-Shift | Aktion |
|---|---|---|
| **Fruehling** | "Laufsocken", "Fahrradsocken" steigen | Sport-Keywords priorisieren |
| **Sommer** | "Sneakersocken", "duenne Socken" steigen | Invisible/Sneaker Keywords hoch |
| **Herbst** | "Wandersocken", "Merinowolle" steigen | Outdoor/Merino Keywords hoch |
| **Winter** | "Thermosocken", "Wollsocken", "Geschenk" steigen | Thermo + Geschenk-Keywords |
| **Weihnachten** | "Socken Geschenk", "Adventskalender Socken" | Geschenk-Keywords in Backend |

### Intent-Scoring Socken-spezifisch

| Keyword-Muster | Intent | Score |
|---|---|---|
| "socken" (generisch) | Informational | 2/10 — zu breit |
| "sportsocken herren" | Navigational | 5/10 — Kategorie-Browse |
| "sportsocken herren 43-46 gepolstert" | Transactional | 9/10 — kaufbereit |
| "beste wandersocken test" | Comparison | 7/10 — fast kaufbereit |
| "socken gegen schweissfuesse" | Solution-seeking | 8/10 — Problem + Kaufbereitschaft |
| "merino wandersocken 3er pack" | Transactional | 10/10 — weiss genau was er will |

---

## Fuer den Review-Analyst

### Socken-spezifische Review-Muster

Bei Socken-Reviews IMMER nach diesen Mustern suchen und quantifizieren:

**Passform-Cluster:**
| Suchbegriff | Was es bedeutet | Einfluss auf |
|---|---|---|
| "rutscht", "rutschen" | Socke haelt nicht am Fuss/an der Ferse | Slot 2 (Passform), BP2, Groessentabelle |
| "schneidet ein", "Abdruck" | Bund zu eng oder zu schmal | BP4 (Einwand), Slot 5 (Bunddetail) |
| "zu eng", "zu weit" | Grundsaetzliches Groessenproblem | Groessentabelle ueberarbeiten |
| "faellt kleiner/groesser aus" | Groessentabelle stimmt nicht | Titel-Groessensignal + Slot 4 |
| "links/rechts" | Anatomische Form erwaehnt | USP wenn positiv, Einwand wenn negativ |

**Material-Cluster:**
| Suchbegriff | Was es bedeutet | Einfluss auf |
|---|---|---|
| "weich", "kuschelig" | Positives Tragegefuehl | Slot 5 (Material), BP1 |
| "kratzt", "juckt" | Material-Problem | BP4 (Einwand), Material-Spec pruefen |
| "schwitzig", "feucht" | Atmungsaktivitaets-Problem | Slot 3 (Feature), BP2 |
| "Geruch", "riecht" | Antibakterielle Eigenschaft fehlt/funktioniert | BP3 oder USP |
| "Merino", "Wolle", "Baumwolle" | Material-Bewusstsein des Kaeufers | Titel + BP1 Material betonen |

**Haltbarkeits-Cluster:**
| Suchbegriff | Was es bedeutet | Einfluss auf |
|---|---|---|
| "Loch", "Loecher" | Haltbarkeitsproblem (Top-Einwand Socken!) | BP3, Slot 5 (verstaerkte Zonen) |
| "Pilling", "Fusseln" | Oberflaechenqualitaet | BP3, Material-Spec |
| "eingelaufen", "geschrumpft" | Waschprobleme | BP3 (Pflege), Backend-Keywords |
| "Farbe verblasst" | Farbbestaendigkeit | BP3 oder USP wenn gut |
| "nach X Waeschen" | Langzeit-Haltbarkeit | BP3 mit konkreter Waeschezahl |

**Naht-Cluster (besonders bei Socken!):**
| Suchbegriff | Was es bedeutet | Einfluss auf |
|---|---|---|
| "Naht drueckt" | Maschinennaht an Zehen stoert | USP "handgekettelt/nahtfrei" |
| "nahtlos", "Flachnaht" | Kaeufer sucht explizit nahtfrei | Titel-Keyword, Slot 3 Callout |
| "spuerbar", "spuere die Naht" | Naht ist stoerend | BP4 (Einwand adressieren) |

### Sprach-Extraktion: Socken-Vokabular

**Minimum 15 Phrasen extrahieren, aufgeteilt in:**

| Kategorie | Beispiel-Phrasen | Wo verwenden |
|---|---|---|
| **Positiv-Passform** (min. 3) | "sitzen wie angegossen", "kein Verrutschen den ganzen Tag", "perfekter Halt" | BP2, Slot 2 Beschreibung |
| **Positiv-Material** (min. 3) | "mega weich", "fuehlen sich hochwertig an", "angenehm auf der Haut" | BP1, Slot 5 Beschreibung |
| **Positiv-Haltbarkeit** (min. 3) | "nach 20 Waeschen wie neu", "halten ewig", "kein Pilling" | BP3, Slot 7 Vergleich |
| **Negativ-Einwaende** (min. 3) | "haette gerne eine 47-50 Groesse", "Bund koennte breiter sein" | BP4, Groessentabelle |
| **Kauf-Trigger** (min. 3) | "direkt nachbestellt", "fuer die ganze Familie geholt", "als Geschenk perfekt" | Titel, A+ Content |

---

## Fuer den Quality-Reviewer

### Socken-spezifische Pruefpunkte (zusaetzlich zu den 7 Dimensionen)

| Check | PASS | FAIL |
|---|---|---|
| **Groessentabelle vorhanden** | Slot 4 enthaelt EU + UK + US Groessen | Fehlt oder nur EU |
| **Packungsgroesse im Hero** | Alle Socken im Pack sichtbar | Nur 1 Socke gezeigt bei Multipack |
| **Tragebild statt Flat-Lay** | Slot 2 zeigt Socke am Fuss | Flat-Lay (zeigt nicht Passform) |
| **Material-Composition** | Exakte % im Briefing + in Bullets | Nur "Baumwolle" ohne % |
| **PAN-EU Groessen** | Groessentabelle hat EU + UK + US | Nur eine Groessennorm |
| **Naht-Thema adressiert** | Wenn >5% Reviews Naht erwaehnen: muss in Briefing sein | Ignoriert obwohl Review-Daten es zeigen |
| **Stueckpreis-Transparenz** | Bei Multipacks: Preis pro Paar kommuniziert | Nur Gesamtpreis |
| **Hoehe erkennbar** | Im Hero und/oder Slot 2 ist die Sockenhoehe klar | Unklar ob Quarter, Crew oder Knie |

---

## Fuer den A+ Content Designer

### A+ Module Socken — Was die Galerie NICHT abdeckt

| A+ Modul | Inhalt | Warum nicht in Galerie |
|---|---|---|
| **Pflegeanleitung** | Waschsymbole, Temperatur, Trockner-Hinweis | Zu detailliert fuer Slot-Infografik |
| **Technologie-Querschnitt** | Schichtaufbau der Socke (Polsterung, Mesh, Verstaerkung) | Braucht mehr Platz als 1 Slot |
| **Anlassbilder (erweitert)** | Sport, Buero, Freizeit, Reise — 4 Szenarien | Galerie zeigt nur 1 Lifestyle-Szene |
| **Material-Story** | Woher kommt die Wolle? Wie wird produziert? | Brand-Story-Element |
| **Groessen-Guide (erweitert)** | Messmethode + Empfehlung + FAQ | Galerie-Slot 4 ist nur die Tabelle |
| **Produktlinien-Vergleich** | Eigene Socken-Varianten nebeneinander (Sport vs. Business vs. Alltag) | Cross-Selling — Shoppable Comparison |

### Anti-Duplikations-Check Socken

| Galerie zeigt | A+ darf NICHT zeigen | A+ zeigt STATTDESSEN |
|---|---|---|
| Slot 2: Fuss im Laufschuh | Gleichen Fuss im gleichen Schuh | Andere Szene: Fuss auf Laufband, Strasse, Trail |
| Slot 3: 5 Callouts Features | Dieselben 5 Features | Tiefere Erklaerung eines Features (Querschnitt) |
| Slot 5: Material-Nahaufnahme | Gleiche Nahaufnahme | Anderes Detail: Naht, Bund, Sohle |
| Slot 7: Vergleich vs. generisch | Gleiche Vergleichstabelle | Eigene Varianten im Shoppable-Chart |
