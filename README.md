# Swing Trading Strategies — A Systematic Reference Library

An open-source reference library of swing trading setups with exact entry/exit rules, source attribution, and notes on when each strategy works (and when it doesn't). Maintained alongside [EasySwing.trading](https://easyswing.trading) — a swing trading screener that scans ~2,000 US equities for these setups daily and journals them with regime context.

Every strategy here is sourced from published research (Minervini, O'Neil, Weinstein, Connors, Bulkowski, Kullamägi, Wilder, Da/Gurun/Warachka, Blitz/Huij/Martens, Dennis/Eckhardt, Jegadeesh/Titman). Where we cite live performance, the source is the EasySwing autoresearch pipeline — a walk-forward backtest with holdout, robustness, and permutation-null gates. See the [methodology notes](#methodology-honesty-notes) at the bottom for what those gates do and don't prove.

---

## Table of Contents

- [Quick reference: credentialed strategies](#quick-reference-credentialed-strategies)
- [Strategy notes](#strategy-notes)
  - [Momentum / breakout family](#momentum--breakout-family)
  - [Trend continuation family](#trend-continuation-family)
  - [Mean reversion family](#mean-reversion-family)
  - [Catalyst family](#catalyst-family)
- [Honorable mentions](#honorable-mentions)
- [Market regime selection](#market-regime-selection)
- [Risk management principles](#risk-management-principles)
- [Resources and further reading](#resources-and-further-reading)
- [Methodology honesty notes](#methodology-honesty-notes)
- [FAQ](#faq)
- [Disclaimer](#disclaimer)

---

## Quick reference: credentialed strategies

The table below lists strategies that have passed walk-forward validation on a holdout window with a robustness neighborhood and a permutation null. **Tuned** means parameters are live-adopted; **tuned-provisional** means the strategy passes the profitability gates but the permutation p-value is degenerate (the detector's intrinsic gates already filter the universe exhaustively, so shuffling returns can't break the signal). Tuned-provisional setups are published for inspection but live params stay at registry defaults until the next sweep promotes them.

| Strategy | Direction | Family | Source author | Status | Best regime |
|---|---|---|---|---|---|
| VCP Breakout | Long | Momentum | Mark Minervini | tuned-provisional | Bull |
| Cup & Handle | Long | Momentum | William O'Neil | tuned | Bull |
| Qullamaggie Breakout | Long | Continuation | Kristjan Kullamägi | tuned | Bull |
| Trend Pullback (EMA20/SMA50) | Long | Pullback | Composite (Minervini-school) | tuned | Bull / Range |
| Proximity Pullback (52w high) | Long | Pullback | Composite | tuned | Bull |
| Power Earnings Gap | Long | Catalyst | Minervini / Zanger | tuned | Bull |
| Frog-in-the-Pan | Long | Momentum | Da, Gurun, Warachka (2014) | tuned | Bull / Range |
| MA Stack Confluence (10/21/50/200) | Long | Momentum | Composite | tuned | Bull |
| ADX Trend Momentum | Long | Momentum | Wilder | tuned | Bull |
| Residual Momentum | Long | Momentum | Blitz, Huij, Martens (2011) | tuned | Bull |
| Multi-Period Strength | Long | Momentum | Jegadeesh-Titman lineage | tuned | Bull |
| Volume-Weighted Trend | Long | Momentum | Composite | tuned | Bull |
| ROC Breakout | Long | Momentum | Composite (Bulkowski) | tuned | Bull |
| HHV Breakout (Donchian / Turtle) | Long | Momentum | Dennis, Eckhardt | tuned | Bull |
| Trend Template Fresh Pass | Long | Momentum | Mark Minervini | tuned | Bull |
| RSI Reversion (Connors 2-period) | Long | Mean reversion | Larry Connors | tuned-provisional | Bull / Range |

Net profit factor on the holdout window varies from ~1.7 (RSI Reversion) to ~4.5 (VCP Breakout, provisional). For the live numbers and current verdicts see the [methodology and performance page](https://easyswing.trading/performance). The full table with per-strategy holdout PF, trade counts, family, regime, and grade floor is also published as a [two-page PDF cheat sheet](https://easyswing.trading/swing-trading-strategy-cheat-sheet.pdf).

---

## Strategy notes

### Momentum / breakout family

#### VCP Breakout (Volatility Contraction Pattern)

Mark Minervini's signature pattern. A stock makes a series of progressively tighter pullbacks on declining volume while institutions accumulate. The breakout above the final contraction on volume expansion is the trigger.

- **Why it works.** Each contraction represents another wave of weak holders being absorbed. When supply dries up, even modest demand resolves the base upward.
- **Hard gates.** Price above SMA50 / SMA150 / SMA200, RS rank above 70, within 25% of 52-week high, 3+ visible contractions.
- **Trigger.** Breakout on volume 40%+ above the 50-day average.
- **Regime.** Bull market only. Win rate collapses in ranging or transitioning environments.
- **Status.** Tuned-provisional. The detector's intrinsic gates produce a small enough filtered pool that the permutation null degenerates; live params kept at registry defaults pending the next sweep iteration.
- **Deep dive.** [VCP setup walkthrough](https://easyswing.trading/blog/vcp-setup-volatility-contraction-pattern). Detailed entry rules in [`strategies/01-vcp.md`](strategies/01-vcp.md).

#### Cup & Handle

William O'Neil's continuation pattern. A rounded U-shaped consolidation (the cup) followed by a tight pullback (the handle), then a breakout above the handle high.

- **Why it works.** The cup is weak holders selling and stronger hands accumulating. The handle shakes out the last nervous holders before institutions push through resistance.
- **Hard gates.** Prior uptrend of 30%+, cup depth 12–35%, cup duration 3–6+ weeks, handle in upper 15% of cup with depth < 12%.
- **Trigger.** Breakout above handle high on volume 40%+ above average, RS rank above 80.
- **Regime.** Strong bull market. Win rate drops sharply in ranging conditions.
- **Status.** Tuned.
- **Deep dive.** [Cup and Handle pattern guide](https://easyswing.trading/blog/cup-handle-pattern-swing-trading). Detailed rules in [`strategies/02-cup-and-handle.md`](strategies/02-cup-and-handle.md).

#### Qullamaggie Breakout

Kristjan Kullamägi's continuation setup. After a sharp directional leg (often +30% in 30–90 days), the stock consolidates in a tight range and then breaks out for a second leg.

- **Why it works.** The initial leg attracts institutional attention; the tight consolidation is profit-taking absorbed by new buyers. The second leg is the genuine extension.
- **Hard gates.** Prior leg of 30%+, tight base 5–15 bars, narrow range bars during the base, RS rank high.
- **Trigger.** Breakout above the base high on a volume surge.
- **Regime.** Bull market. Pattern is essentially noise in choppy conditions.
- **Status.** Tuned.
- **Deep dive.** [Qullamaggie Breakout setup](https://easyswing.trading/blog/qullamaggie-breakout-continuation-setup). See [`strategies/11-qullamaggie-breakout.md`](strategies/11-qullamaggie-breakout.md).

#### Trend Template Fresh Pass

Mark Minervini's Trend Template is the checklist a stock must clear to be considered for a momentum long: price above SMA150 and SMA200, SMA150 above SMA200, both rising for at least a month, price within 25% of 52w high and at least 30% off 52w low, RS rank top quartile. The "fresh pass" variant fires when a stock passes the template for the first time in N days — the moment it joins the leadership cohort.

- **Why the fresh-pass variant.** Late entries on stocks already deep into the template lose the early advance. The fresh pass captures the regime transition for the individual name.
- **Status.** Tuned. See [`strategies/16-trend-template-fresh-pass.md`](strategies/16-trend-template-fresh-pass.md).
- **Background.** [Stage 2 analysis explained](https://easyswing.trading/blog/stage-2-stock-analysis-minervini-uptrend) — the Trend Template is the operational implementation of "stock is in Stage 2."

#### MA Stack Confluence (10/21/50/200)

A composite setup that requires all four moving averages to be in perfect bullish alignment: EMA10 > EMA21 > SMA50 > SMA200, all sloped upward, with price riding the EMA10. The "stack confluence" gate is the strictest version of the moving-average filter family.

- **Why it works.** Perfect alignment with rising slopes confirms multi-timeframe agreement: short-term, intermediate, and long-term participants are all positioned the same way.
- **Status.** Tuned. See [`strategies/13-ma-stack-confluence.md`](strategies/13-ma-stack-confluence.md).
- **Background.** [Moving averages for swing trading](https://easyswing.trading/blog/moving-averages-for-swing-trading).

#### ADX Trend Momentum

Wilder's Average Directional Index (ADX) measures trend strength independent of direction. The setup combines a rising ADX above 25 (genuine trend present) with +DI above -DI (direction is up) and price above the 50-day SMA.

- **Why it works.** ADX confirms that the move is trending rather than oscillating. Many momentum failures happen when entries occur in choppy conditions that look directional on a single bar.
- **Status.** Tuned. See [`strategies/14-adx-trend-momentum.md`](strategies/14-adx-trend-momentum.md).

#### Residual Momentum

Blitz, Huij & Martens (2011) showed that momentum signals stripped of their factor exposures (market beta, size, value) carry more information than raw price momentum. A "poor man's" residual momentum filters stocks whose 6–12 month return is high after subtracting sector or index beta.

- **Why it works.** Standard momentum has periodic crashes when leadership rotates. Residual momentum reduces the rotation risk by isolating stock-specific strength.
- **Status.** Tuned. See [`strategies/15-residual-momentum.md`](strategies/15-residual-momentum.md).
- **Source.** Blitz, Huij, Martens, *Residual Momentum*, Journal of Empirical Finance, 2011.

#### Multi-Period Strength

The Jegadeesh-Titman momentum effect is most robust when measured across multiple lookback windows (3-month, 6-month, 12-month) that confirm each other. Multi-period strength requires positive momentum across all three horizons simultaneously.

- **Why it works.** Single-window momentum can be a recent-news artifact. Multi-window confirmation indicates the strength is structural, not a one-week pop.
- **Status.** Tuned. See [`strategies/12-multi-period-strength.md`](strategies/12-multi-period-strength.md).
- **Source.** Jegadeesh & Titman, *Returns to Buying Winners and Selling Losers*, Journal of Finance, 1993.

#### Volume-Weighted Trend

A trend confirmation where price is above the rising 21-day VWAP and recent up-volume materially exceeds recent down-volume. The setup is the long-form (multi-day) cousin of intraday VWAP-reclaim setups.

- **Why it works.** VWAP is the institutional benchmark. Price persistently above VWAP with up-volume dominance means the average institutional position taken in this period is profitable — typically a self-reinforcing dynamic.
- **Status.** Tuned. See [`strategies/17-volume-weighted-trend.md`](strategies/17-volume-weighted-trend.md).
- **Background.** [Volume analysis for swing trading](https://easyswing.trading/blog/volume-analysis-swing-trading).

#### ROC Breakout

Rate-of-Change measures the percent return over a fixed lookback. A ROC Breakout fires when the 21-day ROC is accelerating into a price breakout — momentum confirms breakout legitimacy.

- **Why it works.** Many breakouts on absolute price terms are weak when momentum is flat or decelerating. Accelerating ROC at the breakout point is the difference between a real leg and a fakeout.
- **Status.** Tuned. See [`strategies/18-roc-breakout.md`](strategies/18-roc-breakout.md).

#### HHV Breakout (Donchian / Turtle)

The classic Donchian channel breakout: enter when price closes above the highest high of the last N bars (typically 20 or 55). This is the foundation of the Turtle trading system designed by Richard Dennis and William Eckhardt.

- **Why it works.** New N-day highs are persistent. The original Turtle program demonstrated this on commodities; subsequent equity research confirms the effect on US stocks with appropriate filters.
- **Status.** Tuned. See [`strategies/19-hhv-breakout.md`](strategies/19-hhv-breakout.md).
- **Source.** Curtis Faith, *Way of the Turtle*, 2007. Original Dennis/Eckhardt system from the early 1980s.

#### Frog-in-the-Pan

Da, Gurun & Warachka (2014) named this effect: information arrives in small, gradual increments rather than as a single news event, so a stock with consistent small daily gains is being repriced quietly by informed participants. The detector measures "information discreteness" — small signed daily returns that compound into a large cumulative move.

- **Why it works.** Markets under-react to a slow drumbeat of small news because no single bar grabs attention. The full repricing arrives over months. Catching it early captures the gap between current price and informed value.
- **Status.** Tuned. See [`strategies/20-frog-in-the-pan.md`](strategies/20-frog-in-the-pan.md).
- **Source.** Da, Gurun, Warachka, *Frog in the Pan: Continuous Information and Momentum*, Review of Financial Studies, 2014.

### Trend continuation family

#### Trend Pullback (EMA20 / SMA50)

A textbook pullback continuation in an established uptrend. Stock is above its SMA50, pulls back to (or briefly through) the rising EMA20, then resumes.

- **Why it works.** In a trend, profit-taking creates a temporary supply spike that resolves at a moving-average reference. Institutional buyers add at the pullback. The trend resumes.
- **Hard gates.** Price above SMA50, EMA20 above SMA50 and rising, RS rank at least 96 (top 4% of universe) — the strict RS gate is what differentiates the tuned version from the textbook setup.
- **Trigger.** Bounce from EMA20 with a confirmation candle, grade A only.
- **Regime.** Bull or range.
- **Status.** Tuned with the strict RS gate. Without the RS≥96 filter the win rate drops materially.
- **Deep dive.** [Pullback to rising MA — trend entry](https://easyswing.trading/blog/pullback-to-rising-ma-trend-entry).

#### Proximity Pullback (52-Week High)

A variant of trend pullback that requires the stock to be near (within ~5%) of its 52-week high before the pullback. The 52w-high proximity is itself a strong screen — stocks that pull back from new highs and re-base tend to continue.

- **Why it works.** Stocks within 5% of a 52w high are the leadership cohort. A pullback that holds in this group is qualitatively different from a pullback in a mid-pack stock.
- **Status.** Tuned. See [`strategies/21-proximity-pullback.md`](strategies/21-proximity-pullback.md).

### Mean reversion family

#### RSI Reversion (Connors 2-period)

Larry Connors's short-term mean-reversion setup. RSI(2) below 10 in an established uptrend triggers a bounce trade.

- **Why it works.** Strong uptrends have temporary oversold dislocations that resolve quickly. RSI(2) — much shorter than the conventional RSI(14) — is sensitive enough to catch them without producing false signals in a real downtrend.
- **Hard gates.** Price above SMA200 (long-term uptrend confirmed), no immediate news catalyst.
- **Trigger.** RSI(2) below 10, exit on RSI(2) above 70 or after 5 bars.
- **Status.** Tuned-provisional. Setup is profitable on the holdout but the permutation null degenerates (filtered pool too small). Live params held at registry defaults.
- **Deep dive.** [RSI mean reversion oversold bounce](https://easyswing.trading/blog/rsi-mean-reversion-oversold-bounce).
- **Source.** Larry Connors, *Short Term Trading Strategies That Work*, 2009.

### Catalyst family

#### Power Earnings Gap (PEG)

Mark Minervini's catalyst setup. A stock gaps up 5%+ on an earnings beat with volume at least 2x the 50-day average. The gap creates a new support shelf.

- **Why it works.** A gap of this magnitude on this volume is institutional re-positioning, not retail flow. The gap level becomes a structural support because the institutions building positions defend their cost basis.
- **Hard gates.** Earnings catalyst, gap 5%+, volume 2x+, gap holds (doesn't fill) for 3+ bars.
- **Trigger.** Entry on day 3+ if gap holds. RS rank above 60.
- **Regime.** Bull market preferred; can work in ranging markets if the individual catalyst is strong.
- **Status.** Tuned.
- **Detailed rules.** [`strategies/06-power-earnings-gap.md`](strategies/06-power-earnings-gap.md).

---

## Honorable mentions

The setups below are community-known and well-documented in trading literature but did not pass our current credentialing process — either because we don't yet have a robust detector implementation, because the holdout permutation null was inconclusive, or because the setup's edge is regime-dependent in ways our walk-forward sweep can't yet capture. They remain in this repository as standalone reference notes.

- [EMA Crossover (9/21)](strategies/03-ema-crossover.md) — classic trend-following crossover. Highly regime-dependent (great in trends, terrible in ranges).
- [VWAP Reclaim](strategies/05-vwap-reclaim.md) — intraday institutional-flow setup. Mostly useful for day traders; swing application is limited.
- [Anchored VWAP Bounce](strategies/09-anchored-vwap.md) — Brian Shannon's method. Strong concept but anchor selection introduces too much discretion to backtest cleanly.
- [Triple RSI Divergence](strategies/10-triple-rsi-divergence.md) — Cardwell methodology. Real effect, but signals are sparse and the formation rules are subjective enough that systematic detection produces high false-positive rates.
- [Stage 2 Breakout (Weinstein)](strategies/07-stage-2-breakout.md) — Stan Weinstein's framework. Largely subsumed by the Trend Template family (Minervini's operational implementation of Stage 2). Kept here for the original framing.
- [Bull Flag / Pennant](strategies/08-bull-flag.md) — Bulkowski's flag pattern. Real but difficult to gate systematically without manual chart reading.

---

## Market regime selection

A strategy's edge is regime-dependent. The same VCP Breakout that returns a strong win rate in a trending bull market drops to near-coin-flip in a ranging market. Identifying the current regime is the highest-leverage decision a swing trader makes before strategy selection.

The five regimes:

1. **Trending Up** — rising SMA50/200, breadth expanding, VIX low. Momentum, breakout, and trend-following strategies all work.
2. **Trending Down** — falling SMA50/200, breadth contracting, VIX rising. Long setups fail systematically. Cash or short-only.
3. **Ranging** — flat SMA50/200, ADX below 20. Mean-reversion thrives, breakouts fail.
4. **High Volatility** — VIX above 25, large ATR, unreliable follow-through. Reduce position sizes, prefer quick setups.
5. **Transitioning** — slopes flattening, regime ambiguous. Reduce exposure by half.

A detailed regime classification checklist and per-strategy effectiveness matrix lives in [`resources/market-regimes.md`](resources/market-regimes.md).

EasySwing detects the current market regime automatically and gates the strategy universe accordingly — see the [bull/bear/choppy regime explainer](https://easyswing.trading/blog/market-regime-bull-bear-choppy).

---

## Risk management principles

Every strategy in this repository assumes disciplined risk management. The fundamentals:

- **1–2% rule.** Risk no more than 1–2% of account equity per trade.
- **Position sizing.** Position size in shares = risk amount / (entry price − stop price). Always derive size from risk, never the other way around.
- **R-multiple tracking.** Express every trade outcome in multiples of initial risk. After 30+ trades, your average R tells you whether the strategy is working.
- **Max open positions.** 5–8 concurrent positions depending on account size. More than 8 is a correlation trap.
- **Drawdown rules.** After 3 consecutive losses, reduce size by 50%. After 5% portfolio drawdown, stop opening new positions for the week. After 10%, move to cash and review.

Full treatment in [`resources/risk-management.md`](resources/risk-management.md). A practical stop-loss guide for each strategy family is at [swing trading stop-loss methods](https://easyswing.trading/blog/swing-trading-stop-loss).

---

## Resources and further reading

A curated set of further-reading links — books, papers, and live tools — lives in [`RESOURCES.md`](RESOURCES.md).

### Strategy deep-dives in this repo

- [VCP Volatility Contraction Pattern](strategies/01-vcp.md)
- [Cup and Handle](strategies/02-cup-and-handle.md)
- [Power Earnings Gap](strategies/06-power-earnings-gap.md)
- [Qullamaggie Breakout](strategies/11-qullamaggie-breakout.md)
- [Multi-Period Strength](strategies/12-multi-period-strength.md)
- [MA Stack Confluence](strategies/13-ma-stack-confluence.md)
- [ADX Trend Momentum](strategies/14-adx-trend-momentum.md)
- [Residual Momentum](strategies/15-residual-momentum.md)
- [Trend Template Fresh Pass](strategies/16-trend-template-fresh-pass.md)
- [Volume-Weighted Trend](strategies/17-volume-weighted-trend.md)
- [ROC Breakout](strategies/18-roc-breakout.md)
- [HHV Breakout (Donchian)](strategies/19-hhv-breakout.md)
- [Frog-in-the-Pan](strategies/20-frog-in-the-pan.md)
- [Proximity Pullback (52-week high)](strategies/21-proximity-pullback.md)
- [RSI Reversion (Connors)](strategies/22-rsi-reversion.md)
- [Trend Pullback (EMA20/SMA50)](strategies/23-trend-pullback.md)

### Honorable mentions

- [EMA Crossover (9/21)](strategies/03-ema-crossover.md)
- [RSI Pullback to 40](strategies/04-rsi-pullback.md)
- [VWAP Reclaim](strategies/05-vwap-reclaim.md)
- [Stage 2 Breakout (Weinstein)](strategies/07-stage-2-breakout.md)
- [Bull Flag / Pennant](strategies/08-bull-flag.md)
- [Anchored VWAP Bounce](strategies/09-anchored-vwap.md)
- [Triple RSI Divergence](strategies/10-triple-rsi-divergence.md)

### Resource notes

- [Glossary of swing trading terms](resources/glossary.md)
- [Market regime guide](resources/market-regimes.md)
- [Risk management for swing traders](resources/risk-management.md)

---

## Methodology honesty notes

Anywhere this repo refers to "tuned" or "tuned-provisional" status, here's what that means and doesn't mean:

- **Walk-forward backtest.** Strategies are tuned on a training window and evaluated on a never-touched holdout window. The training window doesn't see any holdout data.
- **Parameter robustness.** Each tuned configuration is required to retain a profit factor ≥ 1.0 across a ±10–20% parameter neighborhood. Single-cell point estimates are rejected.
- **Permutation null.** Holdout p-values are computed against shuffled-return permutations. When the detector's intrinsic gates already filter the universe exhaustively, the permutation null degenerates to ~1.0; in that case we accept strong holdout PF plus robust neighborhood plus positive Sharpe as evidence and tag the verdict "provisional" rather than "tuned." Tuned-provisional setups are surfaced for inspection; their tuned parameters are NOT live-adopted.
- **Sharpe haircut.** A scalar haircut is applied to raw Sharpe to account for multiple testing. This is an informal approximation, not the full Bailey/López de Prado Deflated Sharpe Ratio. We don't claim it is.
- **Holdout is roughly the last 12 months.** As of the most recent sweep, that's roughly mid-2025 through April 2026.
- **What this proves.** That on a specific holdout window with specific gates and a specific universe, the strategy did not behave like noise. It is evidence, not a guarantee.
- **What this doesn't prove.** That the next 12 months look like the last 12. Regime change breaks strategies. Always size positions as if any single strategy could stop working tomorrow.

For the canonical write-up and current verdict status see [EasySwing.trading/performance](https://easyswing.trading/performance).

---

## FAQ

### What is the best swing trading strategy for beginners?

For new swing traders, the **Trend Pullback** is the most forgiving structure: enter strong uptrends on pullbacks to a rising moving average. The hard gates do most of the work, and the entry trigger is mechanical. Avoid catalyst-driven setups (Power Earnings Gap) and short-horizon mean-reversion (RSI Reversion) until you can hold position-management discipline for 3+ weeks.

### How long should you hold a swing trade?

Most swing trades last 3–15 trading days. RSI Reversion bounces resolve in 1–5 bars. Momentum continuation (VCP, Qullamaggie, Cup & Handle) typically holds 8–20 bars. Position-style entries (Trend Template Fresh Pass, Residual Momentum) can extend beyond 30. Let the trailing stop dictate exit, not an arbitrary calendar.

### Do you need a high win rate to be profitable?

No. A 40% win rate strategy with 3:1 R:R has higher expected value than a 75% win rate strategy with 0.5:1. Win rate alone is a useless number without the R-multiple context. Track expected R per trade, not hit rate.

### What indicators are actually load-bearing for these setups?

Across the credentialed strategy set: RSI (used as a filter and an entry trigger), EMA / SMA (trend filter and pullback reference), ADX (regime/trend strength confirmation), ATR (stops and targets), volume (breakout validation), and RS rank (cross-sectional strength). Most setups use 2–4 of these together. More indicators = more conflicting signals.

### How is the credentialing process different from a regular backtest?

A regular backtest fits parameters to historical data and reports the result. Our process splits data into train and holdout, requires robustness across parameter neighborhoods, runs a permutation null, and applies a Sharpe haircut for multiple testing. Strategies that pass the gates on the holdout — not on the training data — get the tuned tag. See the methodology notes above.

### Should you swing trade in a bear market?

Most strategies in this repo are long-biased and lose money systematically in bear markets. The historically correct response to a confirmed downtrend is cash or short-only exposure. We have one bearish setup ([Bear Flag](https://easyswing.trading/blog/bear-flag-short-setup-downtrend)) but it's not in the long-side credentialed table because the universe and risk profile are different. Bear-market discipline = smaller positions or no positions.

### Where can I see this applied live?

The screener at [EasySwing.trading/strategies](https://easyswing.trading/strategies) runs these detectors against ~2,000 US equities every trading day, applies the current market regime gate, and surfaces only the credentialed setups graded A or B. The [strategies hub](https://easyswing.trading/strategies) lists every detector that's currently live; the [performance page](https://easyswing.trading/performance) shows the empirical record for each.

---

## Disclaimer

This repository is for educational and informational purposes only. Nothing here is investment advice, a recommendation, or a solicitation. Past performance and backtested results do not guarantee future returns. All performance numbers cited are based on historical backtests with specific parameters and may not reflect live trading conditions, slippage, commissions, or your specific account. The author and contributors are not licensed financial advisors. Do your own research and consult a qualified financial advisor before making trading decisions. Trade at your own risk.

---

Maintained by **Wibo** in Amsterdam, alongside [EasySwing.trading](https://easyswing.trading) — a swing-trading screener that scans ~2,000 US equities for these setups daily.
