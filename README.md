# Linus Invest — Two-Tier Stock Dashboard

**Linus's investment framework dashboard**: Tier 1 (top 15 recommended) + Tier 2 (40 watchlist).

## Architecture

- `index.html` — self-contained SPA with Tier 1 / Tier 2 / All / Methodology views
- `data.js` — embedded stock data (prices, scores, metrics)
- `data.json` — raw JSON for programmatic access
- Light/dark mode (CSS variables, prefers-color-scheme)

## Methodology

### 3-Lens Scoring (100 pts)

| Dimension | Points | What It Measures |
|---|---|---|
| **Munger Inversion** | 25 | Financial health — ROE, NetDebt/EBITDA, FCF yield |
| **Buffett Moat** | 25 | Quality — ROIC, EV/EBITDA, analyst buy%, market cap |
| **Bezos Flywheel** | 20 | Momentum — analyst upside, price vs 50-day MA |
| **Framework Fit** | 30 | AGI picks-and-shovels (30) / Non-AGI quality (15) → equalized to 25 in selection |

### Tier Structure

- **Tier 1 (15 stocks)**: 8 AGI picks-and-shovels + 7 Non-AGI quality compounders — highest 3-lens scores
- **Tier 2 (40 stocks)**: Framework-compatible watchlist — Cat 1 (picks-and-shovels) + Cat 3 (civilization trend)

## Update Workflow

```bash
cd ~/linus-invest
git pull
# Edit data.js or regenerate from anysearch data
git add -A
git commit -m "update: DD-MM-YYYY refresh"
git push
# GitHub Pages auto-deploys
```

## Data Sources

- anysearch finance.quote + finance.fundamental endpoints (financialmodelingprep.com)
- As of 2026-07-11

## Exclusions

Hard-excluded per Linus framework locks: TSMC, MU, Hynix, Samsung, NVDA, BTC miners, TSLA.
