# VWAP Reclaim (Intraday/Swing)

> **The VWAP Reclaim strategy captures institutional dip-buying after morning selloffs, producing a 58-65% win rate with a 1.3R average reward-to-risk ratio when the broader trend supports the trade.**

## Overview
- **Author/Origin:** Institutional trading concept, popularized by Brian Shannon in *Technical Analysis Using Multiple Timeframes* (2008)
- **Family:** Mean-Reversion / Momentum Hybrid
- **Direction:** Long
- **Best Market Regime:** Trending Up / Ranging
- **Typical Hold Time:** 1-3 days

## Why It Works

The Volume Weighted Average Price (VWAP) represents the true average price at which shares have traded during the session, weighted by volume. Unlike a simple average, VWAP reflects where the majority of capital has actually changed hands. Institutional traders -- mutual funds, pension funds, hedge funds -- routinely benchmark their execution quality against VWAP. A fund manager who buys below VWAP has achieved favorable execution; one who buys above VWAP has paid a premium.

> "VWAP is the truth serum of the market -- it shows you the real average price." -- Brian Shannon

This institutional behavior creates a self-reinforcing dynamic around the VWAP level. When a stock sells off below VWAP in the morning session, institutional algorithms begin accumulating shares at a discount to their benchmark. As buying volume increases, the price recovers back through VWAP. This reclaim moment is significant: it signals that institutional demand has absorbed all the morning's selling and shifted the intraday supply-demand balance. Short sellers who initiated positions during the selloff now face a losing trade and begin covering, adding additional buying fuel.

The setup works because it aligns three forces: institutional benchmark buying, short-covering, and the psychological shift that occurs when a stock moves from "losing" (below VWAP) to "winning" (above VWAP) territory. Shannon's multi-timeframe approach adds another layer -- by requiring the stock to be above the daily SMA(20), the VWAP reclaim is confirmed as a pullback within a larger uptrend rather than a dead-cat bounce in a declining stock. The combination of intraday mean-reversion and daily trend alignment produces a durable edge.

## Entry Rules

1. The stock gaps down or sells off below VWAP within the first 30-60 minutes of the trading session
2. Price reclaims VWAP (crosses above it) with a volume surge at least 1.5x the intraday average
3. RSI(14) on the intraday chart is above 40 at the time of reclaim, indicating the selloff was orderly rather than panicked
4. Price holds above VWAP for at least 5 consecutive minutes (5-min candle closes) after the initial reclaim
5. The prior trading day's close was above the 20-day Simple Moving Average on the daily chart
6. The stock has average daily volume of at least 500,000 shares (sufficient liquidity for VWAP reliability)
7. No major earnings announcement or binary event is scheduled for the current session
8. The morning selloff did not exceed 5% from the prior close (extreme selloffs indicate structural problems, not routine pullbacks)

## Exit Framework

### Stop Loss
Place the initial stop below the session low or 1.0x ATR(14) below VWAP, whichever is tighter. The session low represents the point of maximum selling pressure -- if price revisits that level after reclaiming VWAP, the reclaim has failed and the trade thesis is invalidated.

### Target 1 (Scale Out)
Exit 50% of the position at the prior day's high. This level often acts as the first area of resistance and provides a natural profit-taking zone. For stocks that gapped down, the prior close serves as an alternative Target 1.

### Target 2 (Remainder)
Exit the remaining 50% at the pre-market high or 2.0x ATR above VWAP. If the stock shows sustained momentum above the prior day's high, this second target captures the continuation move fueled by short-covering and momentum chasing.

### Trailing Stop
After Target 1 is hit, trail the stop below VWAP. If the stock closes a 5-minute candle below VWAP after having reclaimed it, exit the remainder. VWAP is the strategy's anchor level -- losing it means the institutional support thesis is no longer valid.

## Performance Data

| Metric | Value |
|--------|-------|
| Win Rate (Best Regime) | 65% |
| Win Rate (Worst Regime) | 42% |
| Avg R-Multiple | 1.3R |
| Avg Hold Days | 2 |
| Sample Size | 95+ trades |
| Source | EasySwing.trading walk-forward backtest |

*Note: Backtested results do not guarantee future performance. See [methodology](https://easyswing.trading/methodology) for testing approach and limitations.*

## Common Mistakes

- **Buying before the reclaim is confirmed.** Anticipating the VWAP reclaim by buying below VWAP is a different trade entirely -- one with significantly lower probability. Wait for price to close above VWAP on a 5-minute candle with volume confirmation before entering.
- **Trading low-float stocks.** VWAP is less reliable on stocks with low float (under 10 million shares) or low average volume (under 500,000 shares). Thin order books produce erratic VWAP behavior and unreliable reclaim signals.
- **Ignoring the broader daily trend.** A VWAP reclaim in a stock that is below its 20-day SMA on the daily chart is a counter-trend trade. These have lower win rates and smaller average gains. The daily trend context is the primary filter.
- **Chasing after VWAP is already far away.** If the stock has rallied 2-3% above VWAP by the time you notice the reclaim, the risk-reward has deteriorated. The best entries come within the first 1% above VWAP.
- **Holding overnight without the daily trend setup.** The VWAP reclaim is primarily an intraday signal. Holding overnight is only justified when the daily chart shows a clear uptrend (above SMA 20/50) and volume confirms institutional interest.

## Live Scanning

[EasySwing.trading](https://easyswing.trading/strategies) scans for VWAP Reclaim setups daily across 2,000+ US stocks with automated alerts. The scanner monitors intraday VWAP crossovers, volume surges, RSI conditions, and daily trend alignment to identify high-probability reclaim opportunities.

---
*[Back to Strategy Library](../README.md)*
