# Resources

A curated reading list for the strategies in this repository, plus live tools and references for further study.

## Books — primary sources

The strategies in this repo are sourced from these books. Where a strategy carries an author attribution, this is where that attribution comes from.

- **Mark Minervini.** *Trade Like a Stock Market Wizard* (2013) and *Think and Trade Like a Champion* (2016). VCP, Trend Template, Power Earnings Gap. McGraw-Hill.
- **William J. O'Neil.** *How to Make Money in Stocks*, 4th edition (2009). Cup & Handle, CAN SLIM framework, IBD relative strength methodology. McGraw-Hill.
- **Stan Weinstein.** *Secrets for Profiting in Bull and Bear Markets* (1988). Four-stage analysis. McGraw-Hill.
- **Larry Connors.** *Short Term Trading Strategies That Work* (2009). RSI(2) mean reversion. TradingMarkets.
- **Thomas Bulkowski.** *Encyclopedia of Chart Patterns*, 3rd edition (2021). Bull Flag, Pennant, and most of the classical pattern library. Wiley.
- **Curtis Faith.** *Way of the Turtle* (2007). Donchian breakout / Turtle system, originally designed by Richard Dennis and William Eckhardt. McGraw-Hill.
- **Brian Shannon.** *Technical Analysis Using Multiple Timeframes* (2008). Anchored VWAP method.
- **Andrew Cardwell.** RSI methodology (no single primary book — see his RSI Premier course material and Constance Brown's *Technical Analysis for the Trading Professional* for derived treatment).

## Academic papers

- **Jegadeesh, N., & Titman, S. (1993).** *Returns to Buying Winners and Selling Losers: Implications for Stock Market Efficiency.* Journal of Finance, 48(1), 65–91. Foundational momentum paper. Multi-Period Strength and ROC Breakout sit in this lineage.
- **Da, Z., Gurun, U., & Warachka, M. (2014).** *Frog in the Pan: Continuous Information and Momentum.* Review of Financial Studies, 27(7), 2171–2218. Source of the Frog-in-the-Pan setup. [Public preprint via SSRN](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=1572409).
- **Blitz, D., Huij, J., & Martens, M. (2011).** *Residual Momentum.* Journal of Empirical Finance, 18(3), 506–521. Source of Residual Momentum. [SSRN preprint](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=1132921).
- **Wilder, J. W. (1978).** *New Concepts in Technical Trading Systems.* Trend Research. Original ADX and RSI definitions.

## EasySwing — live application

These pages put the strategies in this repo into a daily-screener workflow against ~2,000 US equities.

- [EasySwing.trading homepage](https://easyswing.trading) — overview and onboarding.
- [Strategies hub](https://easyswing.trading/strategies) — every live detector, with the current credentialed verdict, regime gates, and grade thresholds.
- [Strategy Cheat Sheet (PDF)](https://easyswing.trading/swing-trading-strategy-cheat-sheet.pdf) — two-page reference card: regime gate, 5-MA stack, grade scale, ATR-anchored entry/stop/target conventions, and the full 13-strategy table with holdout PF and trade counts. Generated from the live registry.
- [Performance page](https://easyswing.trading/performance) — empirical record per strategy: holdout PF, win rate, expectancy, sample size, and the most recent autoresearch verdict. This is the canonical citation when this repo refers to "live performance."
- [Blog index](https://easyswing.trading/blog) — long-form strategy walkthroughs and methodology posts.
- [Methodology and rebuild log](https://easyswing.trading/blog/swing-trading-strategies-complete-guide) — the complete guide that ties the strategy set together.

## Topical deep-dives — EasySwing blog

Curated by topic.

### Strategy walkthroughs

- [VCP setup: Volatility Contraction Pattern](https://easyswing.trading/blog/vcp-setup-volatility-contraction-pattern)
- [Cup and Handle pattern](https://easyswing.trading/blog/cup-handle-pattern-swing-trading)
- [Qullamaggie Breakout continuation setup](https://easyswing.trading/blog/qullamaggie-breakout-continuation-setup)
- [Pullback to rising MA — trend entry](https://easyswing.trading/blog/pullback-to-rising-ma-trend-entry)
- [RSI mean reversion oversold bounce](https://easyswing.trading/blog/rsi-mean-reversion-oversold-bounce)
- [RSI overbought mean reversion (short)](https://easyswing.trading/blog/rsi-overbought-mean-reversion)
- [Bear flag short setup in a downtrend](https://easyswing.trading/blog/bear-flag-short-setup-downtrend)
- [Stage 2 stock analysis — Minervini uptrend](https://easyswing.trading/blog/stage-2-stock-analysis-minervini-uptrend)

### Technical analysis pillars

- [Moving averages for swing trading](https://easyswing.trading/blog/moving-averages-for-swing-trading)
- [MACD for swing trading](https://easyswing.trading/blog/macd-swing-trading)
- [Bollinger Bands for swing trading](https://easyswing.trading/blog/bollinger-bands-swing-trading)
- [Fibonacci retracement for swing trading](https://easyswing.trading/blog/fibonacci-retracement-swing-trading)
- [Top 10 candlestick patterns for swing trading](https://easyswing.trading/blog/top-10-candlestick-patterns-swing-trading)
- [Support and resistance](https://easyswing.trading/blog/support-and-resistance-swing-trading)
- [Volume analysis](https://easyswing.trading/blog/volume-analysis-swing-trading)

### Context and execution

- [Market regime: bull / bear / choppy](https://easyswing.trading/blog/market-regime-bull-bear-choppy)
- [RS rank — relative strength for swing trading](https://easyswing.trading/blog/rs-rank-relative-strength-swing-trading)
- [Swing trading stop-loss methods](https://easyswing.trading/blog/swing-trading-stop-loss)
- [Swing trading strategies: complete guide](https://easyswing.trading/blog/swing-trading-strategies-complete-guide)

### Tool comparisons

- [EasySwing vs DeepVue](https://easyswing.trading/blog/easyswing-vs-deepvue)
- [EasySwing vs Finviz](https://easyswing.trading/blog/easyswing-vs-finviz)
- [EasySwing vs TradingView](https://easyswing.trading/blog/easyswing-vs-tradingview)
- [EasySwing vs IBD MarketSmith](https://easyswing.trading/blog/easyswing-vs-ibd-marketsmith)

## Data and tools (third-party)

- [Quantified Strategies](https://www.quantifiedstrategies.com) — independent backtest reports for many of the patterns in this repo.
- [StockCharts SharpCharts](https://stockcharts.com) — charting with most of the indicators this repo references.
- [Finviz](https://finviz.com) — fast pre-built screens for breakouts and high-RS stocks.
- [TradingView](https://tradingview.com) — charting and community scripts (most setups in this repo have community Pine Script implementations).

---

If a link here breaks or a source attribution looks wrong, please open an issue or PR. Attribution accuracy is the load-bearing constraint of this repo.
