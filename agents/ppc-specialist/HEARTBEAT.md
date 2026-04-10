# Heartbeat — PPC Specialist

Run this checklist every heartbeat.

## 1. Check for Work

```
GET /api/companies/{companyId}/issues?assigneeAgentId={myId}&status=todo,in_progress,blocked
```

Two types: new campaign setup, optimization review.

## 2. Checkout Task

```
POST /api/issues/{issueId}/checkout
```

## 3. Campaign Setup (New Product)

1. Read `produkt-analyse.md` — product, margins, competition
2. Read `keyword-strategie.md` — keyword tiers, search volumes
3. Calculate break-even ACoS: (margin / price) x 100
4. Create campaign structure:

```
├── SP — Exact (top keywords, aggressive bids)
├── SP — Phrase (mid-tier)
├── SP — Broad/Auto (discovery, lower bids)
├── SP — Branded (defensive)
├── SP — Competitor (offensive)
├── SB — Headline Search (brand awareness)
└── SD — Retargeting (product + audience targeting)
```

5. Set initial bids per category benchmarks
6. Budget allocation: 60% exact/phrase, 25% broad/auto, 15% SB/SD

## 4. Optimization Review (Running Campaigns)

1. Pull performance data (impressions, clicks, CTR, CPC, ACoS, ROAS)
2. Search term analysis: converting → exact, wasting → negative, high-impression/low-click → flag listing
3. Bid adjustments based on ACoS vs. target
4. Budget reallocation
5. Placement analysis

## 5. Self-Check

- [ ] Break-even ACoS calculated
- [ ] Campaign structure follows architecture
- [ ] All keyword tiers mapped
- [ ] Negative keywords defined
- [ ] Budget allocation justified
- [ ] Recommendations specific (not "increase bids" but "keyword X: 0.45 → 0.62 EUR")

## 6. Write Output

Write `ppc-strategie.md` or `ppc-optimierung.md` to `./workspace/{task-id}/`.

## 7. Complete Task

```
PATCH /api/issues/{issueId}
{
  "status": "done",
  "comment": "PPC-Strategie abgeschlossen. [X] Kampagnen, Break-even ACoS: [X]%, Budget: [X] EUR/Tag."
}
```
