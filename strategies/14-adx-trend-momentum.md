# ADX Trend Momentum

A trend-confirmation setup built around Welles Wilder's Average Directional Index (ADX). The setup enters long when ADX confirms a genuine trend is underway AND +DI dominates -DI, with price above its 50-day SMA.

## Why It Works

Many "trend-following" entries fail because they enter during a non-trending or choppy regime that happens to look directional on a single bar. ADX is the diagnostic for whether the move is structurally trending or oscillating.

- ADX above 25 indicates a genuine trend (independent of direction).
- ADX rising indicates the trend is strengthening.
- +DI above -DI indicates the trend direction is up.

The combination — ADX rising through 25 with +DI dominant — is the highest-conviction "trend underway" signal in the indicator's design.

## Entry Rules

1. ADX(14) above 25 AND sloped upward over the last 3 bars.
2. +DI(14) above -DI(14) AND the gap widening (not narrowing).
3. Price above the SMA50.
4. The most recent bar closes in the upper half of its range.
5. Volume above the 20-day average.

## Exit Rules

- **Stop Loss:** 1.5x ATR below entry, or below the recent swing low.
- **Target 1:** 2.0x ATR above entry — scale 50%.
- **Target 2:** Trail with a 1.5x ATR stop or exit on ADX dropping back below 20.
- **Hard exit:** -DI crosses above +DI before Target 1 is hit.

## Ideal Market Conditions

Bull market. The setup is functionally "is this stock trending right now?" — it works in any regime where genuine trends exist, but the long-bias entry rule (+DI dominant) restricts it to up-trending environments.

In a high-volatility regime, ADX can read high from sharp directional moves that lack follow-through. Combine with the regime check from [`resources/market-regimes.md`](../resources/market-regimes.md) before sizing.

## Source Attribution

J. Welles Wilder, Jr. *New Concepts in Technical Trading Systems* (1978). Wilder introduced ADX, ATR, RSI, and the Parabolic SAR in the same book. The ADX 25 threshold and +DI / -DI crossover rules are from Wilder's original specification.

## Cross-References

- Live screening: [EasySwing.trading/strategies](https://easyswing.trading/strategies)
- Related: [MA Stack Confluence](13-ma-stack-confluence.md), [Volume-Weighted Trend](17-volume-weighted-trend.md)
