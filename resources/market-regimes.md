# Market Regimes: When to Use Which Strategy

> **Strategy selection matters less than regime selection. The best strategy in the wrong market regime will lose money.**

Markets cycle through distinct behavioral phases. A VCP Breakout that produces a 72% win rate in a trending bull market drops to 45% in a ranging market. The strategy did not change -- the regime did. Identifying the current regime before selecting a strategy is the single highest-leverage decision a swing trader makes.

---

## The 5 Market Regimes

### 1. Trending Up

Rising SMA50 and SMA200 slopes. Market breadth expanding (>60% of stocks above their 200 SMA). ADX above 25 with positive slope. VIX declining or stable below 18. This is the most forgiving regime -- most long strategies work. Momentum stocks with high relative strength lead the advance. Focus on breakout and trend-following strategies with wider targets.

**Best strategies:** VCP Breakout, Cup & Handle, EMA Crossover, Stage 2 Breakout, Bull Flag, RSI Pullback to 40

### 2. Trending Down

Falling SMA50 and SMA200 slopes. Market breadth contracting (<40% of stocks above their 200 SMA). ADX above 25 with positive slope (trend is strong, just bearish). VIX rising or elevated. Long strategies fail systematically in this regime. The primary options are shorting weak stocks or sitting in cash. Mean-reversion longs are traps -- "cheap" keeps getting cheaper.

**Best strategies:** Bear Flag, RSI Overbought

### 3. Ranging

Flat SMA50 and SMA200 slopes. Price oscillating between defined support and resistance levels. ADX below 20 (no directional trend). Breadth between 35-65%. Mean-reversion and range-bound strategies thrive because price reverts to the mean instead of trending. Breakout strategies generate frequent false signals in this regime.

**Best strategies:** RSI Pullback to 40, Anchored VWAP Bounce, Triple RSI Divergence

### 4. High Volatility

VIX above 25 (or above 30 for extreme volatility). Large intraday ranges (ATR expanding). ADX may read high due to sharp directional moves, but follow-through is unreliable. Position sizes must be reduced (wider stops in ATR terms consume more risk budget). Only strategies with quick holding periods and tight risk definitions are appropriate.

**Best strategies:** VWAP Reclaim (quick in/out), Triple RSI Divergence (reversal setups)

### 5. Transitioning

The regime is changing but the new regime is not yet confirmed. SMA slopes are flattening or beginning to turn. Breadth is shifting. ADX is declining or directionless. This is the highest-uncertainty regime. Reduce exposure to 50% of normal position count. Favor quick mean-reversion strategies over multi-week holds. Be prepared to exit all positions if the new regime becomes clear and contradicts your book.

**Best strategies:** RSI Pullback to 40 (quick in/out), VWAP Reclaim (momentum shift)

---

## Strategy-Regime Matrix

The following table rates each strategy's effectiveness across the five market regimes.

| Strategy              | Trending Up | Trending Down | Ranging | High Volatility | Transitioning |
|-----------------------|:-----------:|:-------------:|:-------:|:---------------:|:-------------:|
| VCP Breakout          | Best        | Avoid         | Avoid   | Avoid           | Avoid         |
| Cup & Handle          | Best        | Avoid         | Avoid   | Avoid           | Avoid         |
| EMA Crossover (9/21)  | Best        | Avoid         | Avoid   | Avoid           | Avoid         |
| RSI Pullback to 40    | Best        | Avoid         | Works   | Avoid           | Works         |
| VWAP Reclaim          | Works       | Works         | Works   | Best            | Works         |
| Power Earnings Gap    | Best        | Avoid         | Works   | Avoid           | Avoid         |
| Stage 2 Breakout      | Best        | Avoid         | Avoid   | Avoid           | Avoid         |
| Bull Flag / Pennant   | Best        | Avoid         | Avoid   | Avoid           | Avoid         |
| Anchored VWAP Bounce  | Works       | Avoid         | Best    | Avoid           | Works         |
| Triple RSI Divergence | Avoid       | Works         | Best    | Works           | Works         |

**Best** = The strategy is designed for this regime. Historically highest win rate and R-multiple.

**Works** = The strategy can be profitable but with reduced edge. Consider tighter stops or smaller position sizes.

**Avoid** = The strategy's statistical edge disappears or inverts in this regime. Do not force it.

---

## How to Identify the Current Regime

Use this checklist to classify the current market regime. Evaluate weekly.

### Price Structure
- [ ] Is SPY above its SMA200? (Above = bullish bias, below = bearish bias)
- [ ] Is the SMA50 sloping up, down, or flat?
- [ ] Is the SMA200 sloping up, down, or flat?

### Trend Strength
- [ ] Is ADX(14) above 25? (Above = trending, below = ranging)
- [ ] Is ADX slope positive? (Rising = trend strengthening)

### Breadth
- [ ] What percentage of stocks in your universe are above their 200 SMA?
  - Above 60%: Broad participation (bullish)
  - 35-65%: Mixed (ranging)
  - Below 40%: Narrow or deteriorating (bearish)

### Volatility
- [ ] What is the current VIX level?
  - Below 15: Low volatility, complacency
  - 15-20: Normal volatility
  - 20-25: Elevated volatility
  - Above 25: High volatility regime
  - Above 30: Extreme volatility

### Decision Tree

1. VIX above 30? --> **High Volatility**
2. ADX above 25 AND breadth above 60% AND SPY above SMA200? --> **Trending Up**
3. ADX above 25 AND breadth below 40% AND SPY below SMA200? --> **Trending Down**
4. ADX below 20 AND breadth between 35-65%? --> **Ranging**
5. None of the above? --> **Transitioning**

When in doubt, default to **Transitioning** and reduce exposure. It is better to miss a few trades than to take the wrong trades in the wrong regime.

---

[EasySwing.trading](https://easyswing.trading) automatically detects the current market regime and filters strategies accordingly.
