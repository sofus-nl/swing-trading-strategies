# RSI Pullback to 40 (Momentum Continuation)

> **Larry Connors' RSI Pullback strategy exploits the high-probability zone where RSI(14) cools to 40-50 within an established uptrend, producing a 70-78% win rate with an average hold time of just 3-5 days.**

## Overview
- **Author/Origin:** Larry Connors and Cesar Alvarez, *Short-Term Trading Strategies That Work* (2009)
- **Family:** Pullback / Mean-Reversion Hybrid
- **Direction:** Long
- **Best Market Regime:** Trending Up
- **Typical Hold Time:** 3-5 days

## Why It Works

In a strong uptrend, the Relative Strength Index rarely drops below 40. When RSI(14) falls from overbought territory (above 70) back to the 40-50 zone, it signals a temporary cooling of momentum rather than a trend reversal. This pullback zone represents a point where short-term traders have taken profits and momentum has paused, but the underlying institutional demand that drives the trend remains intact.

> "In an uptrend, RSI readings near 40-50 represent a cooling off period, not a trend change." -- Larry Connors

Connors' quantitative research, spanning 17 years of S&P 500 component data published in *Short-Term Trading Strategies That Work*, demonstrated that buying after RSI pullbacks to this zone in uptrending stocks produced significantly higher returns than buying at random or buying after RSI reached extreme lows. The key insight is counterintuitive: in strong trends, the best entries come not from oversold readings (RSI below 30) but from the moderate pullback zone (40-50), because stocks strong enough to hold RSI above 40 during corrections are the ones most likely to resume their advance.

The edge is rooted in behavioral finance. When a strong stock pulls back moderately, it shakes out impatient traders and attracts value-conscious institutions. The declining volume during the pullback confirms that selling is light and reactive, not heavy and institutional. The bounce candle -- a close in the upper 60% of the day's range -- provides the final confirmation that buyers have regained control. This setup is designed to be a short-duration, high-probability trade, not a long-term hold.

## Entry Rules

1. Price is above the 200-day Simple Moving Average, confirming the long-term uptrend
2. RSI(14) has pulled back to the 40-50 zone after being above 70 within the last 10 trading bars
3. Price is holding above a rising EMA(21), confirming the intermediate trend is intact
4. Volume is declining during the pullback phase (lower than the 20-day average)
5. A bounce candle forms: the daily close is in the upper 60% of the day's range
6. The bounce candle closes above the EMA(21) support level
7. The stock is not reporting earnings within the next 3 trading days
8. ADX(14) is above 20, confirming sufficient trend strength

## Exit Framework

### Stop Loss
Place the initial stop below the most recent swing low or 2.0x ATR(14) below entry, whichever provides tighter risk. This strategy trades strong stocks in clear uptrends -- a violation of the swing low signals the trend thesis is wrong.

### Target 1 (Scale Out)
Exit 100% of the position at 1.5x ATR above entry or when RSI(14) crosses back above 70, whichever comes first. This is a quick, high-probability trade designed to capture the RSI reversion back to the mean. Connors' data shows the bulk of the edge is captured within the first 3-5 days.

### Target 2 (Remainder)
Not applicable. This strategy exits the full position at Target 1. Holding for extended moves dilutes the strategy's high win rate with unnecessary exposure to reversal risk.

### Trailing Stop
If the position is not stopped out or target-filled within 5 days, trail a 5% stop from the highest close. The strategy's edge diminishes rapidly after the initial momentum burst. Quick exits preserve the statistical advantage.

## Performance Data

| Metric | Value |
|--------|-------|
| Win Rate (Best Regime) | 78% |
| Win Rate (Worst Regime) | 48% |
| Avg R-Multiple | 0.9R |
| Avg Hold Days | 4 |
| Sample Size | 85+ trades |
| Source | Connors / Quantified Strategies |

*Note: Backtested results do not guarantee future performance. See [methodology](https://easyswing.trading/methodology) for testing approach and limitations.*

## Common Mistakes

- **Entering before the bounce candle confirms.** The pullback to RSI 40-50 is the setup, not the trigger. Without the bounce candle closing in the upper 60% of range, there is no confirmation that buyers have returned. Premature entries catch falling knives.
- **Using in downtrending stocks.** An RSI pullback to 40 in a stock below its 200-day SMA is not a momentum continuation -- it is a stock getting weaker. The SMA(200) filter is non-negotiable.
- **Ignoring the SMA(200) filter.** Connors' backtests showed dramatically lower win rates when the long-term trend filter was removed. The 200-day SMA is the line that separates momentum pullbacks from deteriorating stocks.
- **Holding too long.** This is a 3-5 day trade by design. The statistical edge is concentrated in the initial snap-back. Traders who hold for 10+ days turn a high-win-rate strategy into an average one by exposing themselves to subsequent pullbacks.
- **Trading during earnings season without exclusion.** Earnings announcements create binary risk that overwhelms the technical setup. Always verify that the stock is not reporting within the next 3 days.

## Live Scanning

[EasySwing.trading](https://easyswing.trading/strategies) scans for RSI Pullback setups daily across 2,000+ US stocks with automated alerts. The scanner monitors RSI trajectories, bounce candle formation, volume patterns, and trend alignment to surface the highest-probability momentum continuation entries.

---
*[Back to Strategy Library](../README.md)*
