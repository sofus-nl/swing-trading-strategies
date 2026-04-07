# Triple RSI Divergence

> **Triple RSI divergence -- where price makes three consecutive extremes while RSI diverges three times -- produces a 50-58% win rate but a 1.8R average return, as reversal trades offer larger moves when they work.**

## Overview
- **Author/Origin:** Classic technical analysis concept, refined by Andrew Cardwell (RSI expert)
- **Family:** Mean Reversion / Reversal
- **Direction:** Long and Short
- **Best Market Regime:** Ranging / Transitioning
- **Typical Hold Time:** 5-12 days

## Why It Works

A single RSI divergence is one of the most commonly cited signals in technical analysis -- and one of the most commonly failed. Price makes a new low while RSI makes a higher low, suggesting momentum is waning. The problem is that a single divergence in a strong trend is often just a pause, not a reversal. Double divergence is more reliable, but still produces false signals in trending conditions.

Triple divergence changes the equation. When price makes three consecutive lower lows while RSI(14) makes three consecutive higher lows (bullish case), it represents a sustained and deepening exhaustion of selling pressure. Each successive price low is produced with less momentum than the last, and by the third divergence, the sellers are genuinely spent. The same logic applies in reverse for bearish triple divergence.

"Divergence tells you momentum is waning, but it takes a triple divergence to give you a high-probability reversal signal." -- Andrew Cardwell

Cardwell, who spent decades refining Welles Wilder's original RSI framework, demonstrated that triple divergences have materially higher reversal rates than single or double divergences. His research showed that the probability of reversal increases non-linearly with each successive divergence: a third divergence at a support or resistance level is particularly potent because it combines momentum exhaustion with structural price levels. The trade-off is patience -- triple divergences take longer to form and occur less frequently, but when they do complete, the resulting moves tend to be larger precisely because so much energy has been absorbed during the divergence pattern.

## Entry Rules

### Bullish (Long)
1. Price makes 3 consecutive lower lows over the pattern formation
2. RSI(14) makes 3 consecutive higher lows corresponding to each price low
3. The third divergence occurs near a recognizable support level (horizontal, trendline, or moving average)
4. Volume is declining into the pattern, confirming exhaustion rather than panic
5. A confirmation candle appears: bullish engulfing, hammer, or morning star
6. RSI(14) is above 30 at the time of the confirmation candle (not deeply oversold and still falling)

### Bearish (Short)
1. Price makes 3 consecutive higher highs over the pattern formation
2. RSI(14) makes 3 consecutive lower highs corresponding to each price high
3. The third divergence occurs near a recognizable resistance level
4. A confirmation candle appears: bearish engulfing, shooting star, or evening star
5. RSI(14) is below 70 at the time of the confirmation candle

## Exit Framework

### Stop Loss
**Bullish:** Below the lowest low of the entire divergence pattern. This is the maximum pain point -- if price breaks below the third low, the divergence has failed and further downside is likely.
**Bearish:** Above the highest high of the divergence pattern.

### Target 1 (Scale Out)
First significant resistance level (bullish) or support level (bearish). Scale out 50% of the position. Reversal trades often stall at the first structural level as overhead supply or demand from the prior trend engages.

### Target 2 (Remainder)
2.0x ATR from entry. The remaining 50% targets a full mean reversion move. Successful triple divergence reversals frequently produce moves of 2-3x ATR as the trend shifts.

### Trailing Stop
Trail 5% from the extreme (highest high for longs, lowest low for shorts) or below/above the most recent swing point. Reversal trades need wider stops than trend-following trades because the initial move is often volatile and choppy.

## Performance Data

| Metric | Value |
|--------|-------|
| Win Rate (Best Regime) | 58% |
| Win Rate (Worst Regime) | 35% |
| Avg R-Multiple | 1.8R |
| Avg Hold Days | 8 |
| Sample Size | 100+ trades |
| Source | Cardwell RSI methodology; Quantified Strategies |

*Note: Backtested results do not guarantee future performance. See [methodology](https://easyswing.trading/methodology) for testing approach and limitations.*

## Common Mistakes

- **Trading single or double divergence as if it were triple.** The probability profile is significantly different. Single divergences fail more often than they succeed in trending markets. Require all three divergence points before acting.
- **Ignoring the trend.** Divergence in a powerful trend can persist through 4, 5, or more occurrences before any reversal. Triple divergence works best in ranging or transitioning regimes, not against strong trends.
- **Not waiting for the confirmation candle.** The divergence pattern identifies *potential* exhaustion. Without a reversal candle (engulfing, hammer, shooting star), the pattern is incomplete. Many failed divergences never produce a confirmation candle -- the trend simply continues.
- **Setting stops too tight on reversal trades.** Reversals are inherently more volatile than continuation trades. The stop must be below the pattern's extreme to give the trade room to develop.
- **Trading divergence without nearby support or resistance.** Divergence in open space (no structural level nearby) has a much lower success rate. The combination of momentum exhaustion and a price level where buyers or sellers have previously acted is what makes the setup high-probability.

## Live Scanning

[EasySwing.trading](https://easyswing.trading/strategies) scans for Triple RSI Divergence setups daily across 2,000+ US stocks, detecting multi-point divergence patterns on both the bullish and bearish side with automated alerts.

---
*[Back to Strategy Library](../README.md)*
