# Anchored VWAP Bounce

> **Anchored VWAP bounces from significant events produce a 55-63% win rate with a 1.4R average return, exploiting the tendency of institutions to defend their average cost basis.**

## Overview
- **Author/Origin:** Institutional concept, popularized by Brian Shannon (*Technical Analysis Using Multiple Timeframes*, 2008) and Brett Steenbarger
- **Family:** Pullback / Institutional Flow
- **Direction:** Long
- **Best Market Regime:** Trending Up / Ranging
- **Typical Hold Time:** 3-10 days

## Why It Works

Unlike a regular VWAP that resets at the start of each trading session, an anchored VWAP (AVWAP) calculates the volume-weighted average price from any user-defined starting point. When anchored to a significant event -- an earnings gap, an IPO date, a 52-week high, or a major breakout -- the AVWAP represents the average cost basis of every participant who has traded the stock since that event.

"Anchored VWAP gives you the volume-weighted average price from any significant event. It's the closest thing to knowing where institutions are positioned." -- Brian Shannon, *Technical Analysis Using Multiple Timeframes* (2008)

This matters because institutional traders are acutely aware of their average cost. A mutual fund that accumulated a large position after a strong earnings report has an average entry price that closely approximates the AVWAP anchored to that earnings date. When the stock pulls back to this level, two forces converge: the fund may add to its position to improve its average (or at minimum will not sell at a loss), and other participants who missed the initial move see the AVWAP test as a second chance to enter at the same level institutions bought.

The result is a self-reinforcing support zone. AVWAP tests produce bounces more reliably than arbitrary moving averages because they are rooted in actual transactional data rather than arbitrary lookback periods. Brett Steenbarger's research at trading firms demonstrated that AVWAP levels from high-volume events acted as institutional "memory" -- price levels where large funds would re-engage. The strategy works best when the anchor point is both significant (high volume, clear catalyst) and recent enough that the AVWAP has not been tested multiple times, which gradually weakens the support.

## Entry Rules

1. Identify a significant anchor point: earnings gap, IPO date, 52-week high, or major volume spike
2. Price pulls back to the AVWAP level calculated from that anchor
3. Price shows support at the AVWAP level -- 2-3 consecutive candles holding at or slightly above it
4. Volume picks up on the bounce candle, confirming buying interest
5. RSI(14) is above 40, indicating the pullback has not destroyed momentum
6. Stock is trading above its 50-day simple moving average (broad uptrend intact)
7. The AVWAP slope is rising or flat -- a declining AVWAP indicates the stock is in distribution

## Exit Framework

### Stop Loss
Place the stop below the AVWAP by 1.0x ATR. A close below the AVWAP means institutions are no longer defending the level and the average cost basis thesis is broken.

### Target 1 (Scale Out)
1.5x ATR above entry. Scale out 50% of the position to capture the initial bounce. AVWAP bounces often produce a quick 1-3 day snap-back before consolidating.

### Target 2 (Remainder)
Prior swing high. The remaining 50% targets the most recent significant high, which is where supply from the prior rally may emerge.

### Trailing Stop
Once Target 1 is reached, trail the stop below the most recent swing low or 1.5x ATR below the current price, whichever provides more room. AVWAP bounces can develop into multi-day trends if institutional accumulation resumes.

## Performance Data

| Metric | Value |
|--------|-------|
| Win Rate (Best Regime) | 63% |
| Win Rate (Worst Regime) | 40% |
| Avg R-Multiple | 1.4R |
| Avg Hold Days | 6 |
| Sample Size | 100+ trades |
| Source | Shannon, *Technical Analysis Using Multiple Timeframes*; institutional flow research |

*Note: Backtested results do not guarantee future performance. See [methodology](https://easyswing.trading/methodology) for testing approach and limitations.*

## Common Mistakes

- **Using AVWAP without a meaningful anchor point.** Anchoring to an arbitrary date produces a meaningless level. The anchor must be a high-volume, high-significance event that institutional traders would remember and act on.
- **Ignoring the broader trend.** An AVWAP bounce in a Stage 4 decline is a counter-trend trade with much lower odds. The strategy works best when the broader trend supports the long direction.
- **Not waiting for bounce confirmation.** Buying the first touch of the AVWAP is premature. Wait for 2-3 candles to hold and a bounce candle with above-average volume to confirm that buyers are present.
- **Anchoring to too many events.** Drawing 5-10 AVWAP lines creates confusion and dilutes the signal. Limit to the 2-3 most significant anchor points for any given stock.
- **Trading against a declining AVWAP slope.** A falling AVWAP from a recent high means the average participant since that high is underwater. These levels act as resistance, not support.

## Live Scanning

[EasySwing.trading](https://easyswing.trading/strategies) scans for Anchored VWAP setups daily across 2,000+ US stocks, identifying pullbacks to institutional cost levels with volume-confirmed bounces and automated alerts.

---
*[Back to Strategy Library](../README.md)*
