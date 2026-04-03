# kg-skills

A collection of Claude Code skills for personal investment research.

---

## Table of Contents

- [Installation](#installation)
- [Skills](#skills)
  - [kg-investment-analysis](#kg-investment-analysis)
  - [kg-recent-price-analysis](#kg-recent-price-analysis)

---

## Installation

Each skill is packaged as a `.skill` file (a zip archive). To install, extract each skill into your personal Claude Code skills directory.

**Prerequisites:** [Claude Code](https://claude.ai/code) installed.

**Steps:**

1. Clone or download this repository:
   ```bash
   git clone <repo-url>
   cd skills
   ```

2. Extract each `.skill` file into `~/.claude/skills/`:
   ```bash
   unzip kg-investment-analysis.skill -d ~/.claude/skills/
   unzip kg-recent-price-analysis.skill -d ~/.claude/skills/
   ```

3. Verify the skills are installed by checking the directories exist:
   ```bash
   ls ~/.claude/skills/
   # Should list: kg-investment-analysis  kg-recent-price-analysis
   ```

4. Open Claude Code — skills are auto-discovered and available immediately. Type `/` to see them listed, or invoke them directly (e.g., `/kg-investment-analysis`).

---

## Skills

### kg-investment-analysis

A bottoms-up single-equity investment analysis framework. Performs deep dives on individual stocks covering business fundamentals, financial metrics, moat analysis, valuation, and position strategy.

**Triggers on:** "analyze [ticker]", "is [stock] a buy", "deep dive on [company]", "bull/bear case for [ticker]", "summarize earnings call for [company]", "what's the BAIT on [stock]", or any request for financial analysis of a named company.

**Output modes:**
- **Mode A — Full Investment Thesis**: 15-section analysis including business overview, financial history, moat rating, BAIT framework, scenario pricing (with probabilities), and a downloadable styled HTML report
- **Mode B — Earnings Deep Dive**: Summary of the most recent earnings call and what it means for the thesis
- **Mode C — News & Price Action**: What happened to the stock recently and why

**Key principles:** Published data only (10-K, earnings releases, official guidance); multi-year trend view; live price verification before every analysis.

---

### kg-recent-price-analysis

A structured price history and event analysis framework. Analyzes a stock's price action across three horizons (5-year, 1-year, 30-day), identifies every 20%+ move, and classifies each event by type (fundamental, macro, sentiment, etc.).

**Triggers on:** "price history for [ticker]", "what happened to [stock]", "chart [ticker]", "how has [stock] performed", "what drove [stock] up/down", or any request about historical price movements, drawdowns, or rallies. Also called from `kg-investment-analysis` for price context.

**Output:** Conversational analysis plus a downloadable HTML report with an annotated Chart.js price chart.

**Key principles:** Accuracy above speed — all prices and percentage changes verified from live sources; intrinsic vs. extrinsic move classification; math shown for every calculation.
