# Heartbeat — PPC Specialist

## 1. Check for Tasks

- New campaign setup requests from CEO
- Optimization reviews for running campaigns
- Keyword strategies from Keyword Researcher
- Performance alerts or budget changes

## 2. Campaign Setup (New Product)

1. Read `produkt-analyse.md` — understand product, margins, competition
2. Read `keyword-strategie.md` — get keyword tiers and search volumes
3. Calculate break-even ACoS: (margin / price) × 100
4. Create campaign structure:

```
Campaign Structure:
├── SP — Exact (Top keywords, aggressive bids)
├── SP — Phrase (Mid-tier keywords)
├── SP — Broad/Auto (Discovery, lower bids)
├── SP — Branded (Defensive, own brand terms)
├── SP — Competitor (Offensive, competitor brand terms)
├── SB — Headline Search (Brand awareness, top-of-search)
└── SD — Retargeting (Product targeting, audience targeting)
```

5. Set initial bids based on category benchmarks
6. Define budget allocation (60% exact/phrase, 25% broad/auto, 15% SB/SD)

## 3. Optimization Review (Running Campaigns)

1. Pull performance data (impressions, clicks, CTR, CPC, ACoS, ROAS)
2. Search term analysis:
   - Converting terms → promote to exact match
   - Wasting terms → add as negative keywords
   - High-impression/low-click → listing problem (flag for Listing-Briefer)
3. Bid adjustments based on ACoS vs. target
4. Budget reallocation from underperformers to winners
5. Placement analysis (top-of-search vs. rest-of-search vs. product pages)

## 4. Write Output

Write `ppc-strategie.md` (setup) or `ppc-optimierung.md` (review) to task workspace.

## 5. Self-Check

- [ ] Break-even ACoS calculated
- [ ] Campaign structure follows standard architecture
- [ ] All keyword tiers mapped to campaigns
- [ ] Negative keywords defined
- [ ] Budget allocation justified by data
- [ ] Recommendations are specific (not "increase bids" but "increase bid on [keyword] from 0.45 to 0.62 EUR")
