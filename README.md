# ipo-2025-2026-tracker
# 2025–2026 IPO Returns Tracker
A single-page dashboard tracking how the 2025–2026 IPO class has performed to date, from IPO price through 1st day close, 1 month, 6 months, 12 months, and current returns, with sector filters, sortable views, and a returns chart.

**▶ Live demo:** _add your GitHub Pages URL here once deployed_

![Dashboard screenshot](screenshot.png)
<!-- Replace with a real screenshot: open the live page, take a screenshot, and commit it as screenshot.png -->

---
## Why I built this
When a company IPOs, the headline is always the first-day pop. This creates a lot of FOMO in retail investors that they missed the pop and makes them want to buy the stock. I was curious to see how companies who IPOd performed  longer term, in a visual way. I started out by creating a spreadsheet, but then quickly switched to building a Claude Code live artifact.

The pattern that emerged is the reason the tool exists. A strong first-day pop was a poor predictor of durable returns. Several names that spiked 40–80% on day one bled out through the 6-month mark as lockups expired and momentum unwound.
## What it does
- **Full return waterfall** per company: issue price → first-day close → 1M → 6M → 12M → current
- **Sector filtering** to compare cohorts (AI infra, fintech, crypto, SaaS, aerospace, and more)
- **Sortable table + chart views** to rank the class by any return window
- **Per-company detail panel** with a plain-English assessment derived from that name's return profile
- **KPI summary** across the whole class at a glance
## Design decisions & tradeoffs
- **Static, single-file, no backend.** The entire app is one `index.html` with Chart.js loaded from a CDN. It makes the tool portable, instantly loadable, and free to host. The tradeoff is that return figures are a point-in-time snapshot rather than a live market feed  appropriate for a retrospective analysis, and I'd wire a live data source if this became a recurring product.
- **Insight generation is computed from the dataset**, not a live model call, so the analysis is deterministic and works anywhere with zero dependencies or keys.
- **Optimized for scanning for trends, not for depth.** The goal is that someone gets the shape of the class in ten seconds. Anything requiring deeper diligence links back out to the source filing.
## Data & caveats
Returns are compiled from public IPO pricing and market data for the 2025–2026 class. Figures are a snapshot for analysis and illustration, not investment advice. Recently listed names (SpaceX, Cerebras, Quantinuum, and others) don't yet have full 6- or 12-month returns.
## Built with
Claude Code. Plain HTML, CSS, and JavaScript. [Chart.js](https://www.chartjs.org/) for the returns chart. No framework, no build step.
## Running locally
Clone the repo and open `index.html` in any browser — there's nothing to install or build.
---

_Built by Irina Issakova. This started as a way to see trends of returns of recently IPOd companies across all sectors.
