# Swing Trading Strategies: A Systematic Reference Library

This is an open-source reference library of 10 battle-tested swing trading strategies with exact entry/exit rules and backtested performance data. Maintained by [EasySwing.trading](https://easyswing.trading) -- a swing trading screener that scans 2,000+ US stocks for these setups daily. Each strategy includes specific entry conditions, risk management rules, and performance benchmarks sourced from published research and quantified backtests.

---

## Table of Contents

- [Strategy Comparison](#strategy-comparison)
- [1. VCP (Volatility Contraction Pattern)](#1-vcp-volatility-contraction-pattern)
- [2. Cup and Handle](#2-cup-and-handle)
- [3. EMA Crossover (9/21)](#3-ema-crossover-921)
- [4. RSI Pullback to 40](#4-rsi-pullback-to-40)
- [5. VWAP Reclaim](#5-vwap-reclaim)
- [6. Power Earnings Gap (PEG)](#6-power-earnings-gap-peg)
- [7. Stage 2 Breakout (Weinstein)](#7-stage-2-breakout-weinstein)
- [8. Bull Flag / Pennant](#8-bull-flag--pennant)
- [9. Anchored VWAP Bounce](#9-anchored-vwap-bounce)
- [10. Triple RSI Divergence](#10-triple-rsi-divergence)
- [Market Regime Guide](#market-regime-guide)
- [Risk Management Principles](#risk-management-principles)
- [Resources and Further Reading](#resources-and-further-reading)
- [FAQ](#faq)
- [Disclaimer](#disclaimer)

---

## Strategy Comparison

| Strategy | Direction | Family | Win Rate Range | Avg R:R | Typical Hold | Best Market Regime |
|---|---|---|---|---|---|---|
| VCP (Volatility Contraction) | Long | Momentum | 65-72% | 1.8:1 | 8-12 days | Trending Up |
| Cup & Handle | Long | Momentum | 62-69% | 2.1:1 | 12-20 days | Trending Up |
| EMA Crossover (9/21) | Long | Trend-Following | 55-62% | 1.5:1 | 5-15 days | Trending Up |
| RSI Pullback to 40 | Long | Mean-Reversion | 70-78% | 0.9:1 | 3-5 days | Trending Up / Ranging |
| VWAP Reclaim | Long | Intraday/Swing | 58-65% | 1.3:1 | 1-3 days | Any |
| Power Earnings Gap | Long | Catalyst | 60-68% | 2.0:1 | 5-15 days | Any |
| Stage 2 Breakout | Long | Position/Swing | 55-65% | 2.5:1 | 15-40 days | Trending Up |
| Bull Flag / Pennant | Long | Continuation | 60-67% | 1.6:1 | 3-8 days | Trending Up |
| Anchored VWAP Bounce | Long | Institutional | 55-63% | 1.4:1 | 3-10 days | Trending Up / Ranging |
| Triple RSI Divergence | Long/Short | Reversal | 50-58% | 1.8:1 | 5-12 days | Ranging / Transitioning |

---

## 1. VCP (Volatility Contraction Pattern)

The VCP is a momentum breakout setup that identifies stocks being accumulated by institutions through a series of contracting price ranges. Backtested across multiple market cycles, it produces a 65-72% win rate with an average reward-to-risk of 1.8:1 (Source: Mark Minervini, *Trade Like a Stock Market Wizard*, 2013; Quantified Strategies backtest, 48+ trades).

### Why It Works

Institutional buyers accumulate shares in stages, creating progressively tighter price contractions as selling pressure (supply) dries up. Each contraction represents fewer remaining sellers. When supply is fully absorbed, even modest buying pressure triggers a breakout.

> "The VCP is the most reliable base pattern I've found in my 30+ years of trading." -- Mark Minervini

### Entry Rules

1. Price is above the 50-day, 150-day, and 200-day SMA (moving average stack confirmed)
2. At least 3 contracting pullbacks are visible in the base, each shallower than the prior
3. Volume has dried up significantly during the base formation (below 50-day average)
4. Breakout occurs on volume 40% or more above the 50-day average
5. Relative Strength rank is above 70 (top 30% of the market)
6. The 200-day SMA is trending upward for at least 1 month
7. Price is within 25% of the 52-week high

### Exit Rules

- **Stop Loss:** 1.5x ATR below entry price
- **Target 1:** 2.0x ATR above entry -- scale out 50% of position
- **Target 2:** 4.0x ATR above entry -- exit remaining 50%
- **Trailing Stop:** Below the most recent swing low after Target 1 is hit

### Ideal Market Conditions

The VCP performs best in trending-up markets where institutional money is rotating into growth and momentum names. Avoid this setup in ranging or high-volatility regimes -- the contracting base is more likely to break down when broad market direction is uncertain.

### Performance Summary

| Metric | Value |
|---|---|
| Win Rate (Trending Up) | 72% |
| Win Rate (Ranging) | 45% |
| Avg R-Multiple | 1.8 |
| Avg Hold Days | 11 |
| Sample Size | 48+ trades |
| Source | Quantified Strategies backtest |

### Pattern Illustration

```
Price
  |    /\
  |   /  \  /\
  |  /    \/  \ /\
  | /          \/  \___/--- Breakout ->
  |________________________
                    Volume ^
```

[EasySwing.trading](https://easyswing.trading/strategies) scans for VCP setups daily across 2,000+ US stocks.

---

## 2. Cup and Handle

The Cup and Handle is a momentum continuation pattern that signals the resumption of a prior uptrend after a rounded consolidation. Backtested across bull market cycles, it produces a 62-69% win rate with an average reward-to-risk of 2.1:1 (Source: William O'Neil, *How to Make Money in Stocks*, 2009; 55+ trades).

### Why It Works

The rounded cup forms as weak holders sell during a correction and stronger hands accumulate at lower prices. The handle represents a final shakeout of remaining nervous holders before institutions push through resistance.

> "The cup with handle is one of the most important chart patterns in the stock market." -- William O'Neil

### Entry Rules

1. Prior uptrend of at least 30% before the cup begins
2. Cup depth between 12% and 35% from the prior high
3. Cup duration is at least 3-6 weeks (rounded bottom, not V-shaped)
4. Handle forms in the upper 15% of the cup with depth less than 12%
5. Volume dries up during handle formation (below 50-day average)
6. Breakout above the handle high on volume 40%+ above average
7. Relative Strength rank at or above 80

### Exit Rules

- **Stop Loss:** 1.5x ATR below entry, or below the handle low (whichever is tighter)
- **Target 1:** 2.5x ATR above entry -- scale out 40%
- **Target 2:** 5.0x ATR above entry -- exit remaining 60%
- **Trailing Stop:** Below the most recent swing low. Sell immediately if price closes back inside the cup.

### Ideal Market Conditions

Cup and Handle patterns perform best in strong bull markets when institutional money is actively flowing into equities. This pattern has a poor track record in ranging markets (32% win rate) and should be avoided entirely in bear markets.

### Performance Summary

| Metric | Value |
|---|---|
| Win Rate (Trending Up) | 69% |
| Win Rate (Ranging) | 32% |
| Avg R-Multiple | 2.1 |
| Avg Hold Days | 16 |
| Sample Size | 55+ trades |
| Source | Quantified Strategies backtest |

### Pattern Illustration

```
Price
  |  \                   /-- Handle --/--- Breakout ->
  |   \                 / \         /
  |    \               /   \___ __/
  |     \             /
  |      \___________/
  |         Cup (3-6 weeks)
  |________________________________
```

[EasySwing.trading](https://easyswing.trading/strategies) scans for Cup and Handle setups daily across 2,000+ US stocks.

---

## 3. EMA Crossover (9/21)

The EMA Crossover is a trend-following setup that identifies momentum shifts when the short-term exponential moving average crosses above the longer-term EMA. Across various market conditions, it produces a 55-62% win rate with an average reward-to-risk of 1.5:1 (Source: multiple quantified backtests).

### Why It Works

Moving average crossovers capture the transition from consolidation to trending behavior. The 9/21 EMA pair is fast enough to catch early moves while filtering out most noise. ADX confirmation ensures the crossover occurs in a genuinely trending environment rather than a choppy range.

### Entry Rules

1. EMA(9) crosses above EMA(21)
2. Price is above the SMA(50)
3. Volume is above the 20-day average on the crossover day
4. ADX(14) is above 20 (confirming a trending market)
5. RSI(14) is between 50 and 70 (momentum present but not overextended)

### Exit Rules

- **Stop Loss:** Below the EMA(21) or 1.5x ATR below entry, whichever is closer
- **Target 1:** 1.5x ATR above entry
- **Target 2:** 3.0x ATR above entry
- **Trailing Stop:** ATR-based at 1.5x ATR from recent highs

### Ideal Market Conditions

EMA Crossovers work best in trending markets with sustained directional moves. This setup generates many false signals in choppy or ranging environments, so always confirm with ADX above 20 before entering.

### Performance Summary

| Metric | Value |
|---|---|
| Win Rate (Trending) | 62% |
| Win Rate (Ranging) | 38% |
| Avg R-Multiple | 1.5 |
| Avg Hold Days | 10 |
| Sample Size | 120+ trades |
| Source | Quantified Strategies backtest |

### Pattern Illustration

```
Price
  |                      /-- Price continues ->
  |                    /
  |        ----EMA9--x---------->
  |       /      --x--EMA21---->
  |  ____/      /
  | /          /
  |________________________________
              ^ Crossover (buy)
```

[EasySwing.trading](https://easyswing.trading/strategies) scans for EMA Crossover setups daily across 2,000+ US stocks.

---

## 4. RSI Pullback to 40

The RSI Pullback is a mean-reversion continuation setup that enters strong uptrends when momentum temporarily cools to the 40-50 RSI zone. Backtested on US equities, it produces a 70-78% win rate with an average reward-to-risk of 0.9:1 (Source: Larry Connors, *Short Term Trading Strategies That Work*, 2009; Quantified Strategies).

### Why It Works

In a strong uptrend, RSI pulling back from overbought territory to the 40-50 zone represents a healthy pause -- not a reversal. Institutional buyers use these pauses to add to positions, creating reliable bounce points. The high win rate compensates for the modest R-multiple.

### Entry Rules

1. Price is above the SMA(200) (long-term uptrend confirmed)
2. RSI(14) pulls back to the 40-50 zone from above 70 within the last 10 bars
3. Price holds above a rising EMA(21)
4. Volume is declining during the pullback (no distribution)
5. Bounce candle closes in the upper 60% of its range (buying pressure visible)

### Exit Rules

- **Stop Loss:** Below the swing low of the pullback or 2.0x ATR below entry
- **Target 1:** 1.5x ATR above entry, or when RSI(14) returns above 70 -- exit 100%
- **Trailing Stop:** 5% trailing from highest close

### Ideal Market Conditions

RSI Pullbacks work in both trending-up and ranging markets -- any environment where the broader trend is intact. Avoid in downtrending markets where what looks like a pullback may be the start of a deeper decline.

### Performance Summary

| Metric | Value |
|---|---|
| Win Rate (Trending Up) | 78% |
| Win Rate (Downtrending) | 35% |
| Avg R-Multiple | 0.9 |
| Avg Hold Days | 4 |
| Sample Size | 200+ trades |
| Source | Larry Connors / Quantified Strategies |

### Pattern Illustration

```
RSI
70 |----x               x----
   |     \             /
50 |      \           /
40 |-------x---------x--------  <- Buy zone
30 |
   |________________________________

Price
   |        \       /--- Continuation ->
   |         \_____/
   |     Pullback (3-5 days)
   |________________________________
```

[EasySwing.trading](https://easyswing.trading/strategies) scans for RSI Pullback setups daily across 2,000+ US stocks.

---

## 5. VWAP Reclaim

The VWAP Reclaim is an intraday/swing setup that identifies institutional buying when price recovers the Volume-Weighted Average Price after a morning selloff. Across active trading sessions, it produces a 58-65% win rate with an average reward-to-risk of 1.3:1 (Source: quantified intraday backtests).

### Why It Works

VWAP represents the average price weighted by volume -- essentially the "fair value" for the session. When price reclaims VWAP after selling below it, this signals that institutional buyers view current prices as attractive. The volume surge on reclaim confirms real demand rather than a low-volume drift.

### Entry Rules

1. Stock gaps down or sells off below VWAP in the first 30-60 minutes of the session
2. Price reclaims VWAP with a volume surge (greater than 1.5x the average)
3. RSI(14) is above 40 at the time of reclaim
4. Price holds above VWAP for 5 or more consecutive 1-minute candles
5. Prior day closed above the SMA(20)

### Exit Rules

- **Stop Loss:** Below the session low, or 1.0x ATR below VWAP
- **Target 1:** Prior day high
- **Target 2:** Pre-market high or 2.0x ATR above VWAP
- **Trailing Stop:** Below VWAP for intraday holds, or 1.0x ATR for multi-day

### Ideal Market Conditions

VWAP Reclaims work in any regime that produces high relative volume. The key requirement is activity, not direction. Avoid on low-volume drift days where price floats around VWAP without conviction.

### Performance Summary

| Metric | Value |
|---|---|
| Win Rate (High Volume) | 65% |
| Win Rate (Low Volume) | 42% |
| Avg R-Multiple | 1.3 |
| Avg Hold Days | 2 |
| Sample Size | 80+ trades |
| Source | Quantified intraday backtest |

### Pattern Illustration

```
Price
  |  Open
  |  |
  |  v---\
  |       \   VWAP - - - - - - x - - - ->
  |        \_____/            / ^
  |         Low              /  Holds above
  |                         /
  |________________________/___________
   09:30    10:00    10:30    11:00
```

[EasySwing.trading](https://easyswing.trading/strategies) scans for VWAP Reclaim setups daily across 2,000+ US stocks.

---

## 6. Power Earnings Gap (PEG)

The Power Earnings Gap is a catalyst-driven setup that captures institutional repositioning after a significant earnings beat. Backtested across earnings seasons, it produces a 60-68% win rate with an average reward-to-risk of 2.0:1 (Source: Dan Zanger; Mark Minervini methodology; 45+ trades).

### Why It Works

When a company reports earnings significantly above expectations and the stock gaps up on massive volume, this represents institutional funds rapidly building positions. The gap creates a new support level as these large buyers defend their average cost. Gaps that hold for 3+ days almost never fully fill.

### Entry Rules

1. Stock gaps up 5% or more on the earnings report
2. Volume on the gap day is at least 2x the 50-day average
3. The gap holds above prior resistance levels
4. Price does not fill the gap for 3 or more trading days
5. Relative Strength rank is above 60

### Exit Rules

- **Stop Loss:** Below the low of the gap day
- **Target 1:** 1.5x the gap range above the gap day high
- **Target 2:** 3x the gap range above the gap day high
- **Trailing Stop:** Below the most recent swing low

### Ideal Market Conditions

Power Earnings Gaps perform best in bull markets during strong earnings seasons. The setup works in any regime when the individual stock's catalyst is strong enough, but avoid in bear markets where even strong gaps tend to fade.

### Performance Summary

| Metric | Value |
|---|---|
| Win Rate (Bull Market) | 68% |
| Win Rate (Bear Market) | 40% |
| Avg R-Multiple | 2.0 |
| Avg Hold Days | 10 |
| Sample Size | 45+ trades |
| Source | Zanger / Minervini methodology |

### Pattern Illustration

```
Price
  |                    /--- Continuation ->
  |                   /
  |           -------/  <- Hold above gap
  |           |  Gap (5%+)
  |  --------/
  | /  Prior trend
  |________________________________
         ^ Earnings     ^ Entry (day 3+)
           (2x volume)
```

[EasySwing.trading](https://easyswing.trading/strategies) scans for Power Earnings Gap setups daily across 2,000+ US stocks.

---

## 7. Stage 2 Breakout (Weinstein)

The Stage 2 Breakout is a position/swing setup based on Stan Weinstein's stage analysis that identifies stocks transitioning from basing (Stage 1) into a new uptrend (Stage 2). Backtested across full market cycles, it produces a 55-65% win rate with an average reward-to-risk of 2.5:1 (Source: Stan Weinstein, *Secrets for Profiting in Bull and Bear Markets*, 1988).

### Why It Works

Weinstein's stage analysis divides a stock's lifecycle into four stages: basing, advancing, topping, and declining. The transition from Stage 1 to Stage 2 is confirmed when the 30-week moving average turns up and price breaks above the base resistance on volume. This marks the beginning of a sustained advance as institutional accumulation becomes visible.

> "Buy in Stage 2, sell in Stage 3 -- it's that simple." -- Stan Weinstein

### Entry Rules

1. The 30-week moving average (approximated as SMA(150) on a daily chart) is rising
2. Price breaks above Stage 1 base resistance on volume 2x or more above average
3. Relative Strength line is improving (rising RS rank)
4. Price has based (Stage 1) for at least 3 months
5. The breakout occurs on a weekly closing basis, not just intraday

### Exit Rules

- **Stop Loss:** Below the 30-week moving average or the base support level
- **Target 1:** 20% above entry -- scale out partial position
- **Target 2:** Hold remaining position until Stage 3 signs appear (flattening 30-week MA, volume climaxes)
- **Trailing Stop:** Below the rising 30-week moving average on a weekly closing basis

### Ideal Market Conditions

Stage 2 Breakouts work best in early-to-mid bull markets when the market is transitioning from pessimism to optimism. Avoid in late-stage bull markets where most stocks are already extended, and avoid entirely in bear markets.

### Performance Summary

| Metric | Value |
|---|---|
| Win Rate (Early Bull) | 65% |
| Win Rate (Late Bull) | 42% |
| Avg R-Multiple | 2.5 |
| Avg Hold Days | 28 |
| Sample Size | 60+ trades |
| Source | Weinstein methodology backtest |

### Pattern Illustration

```
Price
  |                              /--- Stage 2 ->
  |                             /
  |     Stage 1 Base           / Breakout (2x vol)
  |  ______/\____/\___________/
  | /                        |
  |/   30-week MA ---------> turns up
  |________________________________
       3+ months basing       ^
```

[EasySwing.trading](https://easyswing.trading/strategies) scans for Stage 2 Breakout setups daily across 2,000+ US stocks.

---

## 8. Bull Flag / Pennant

The Bull Flag is a continuation pattern that offers a low-risk entry after a strong directional move pauses in a tight consolidation. Backtested across momentum stocks, it produces a 60-67% win rate with an average reward-to-risk of 1.6:1 (Source: Thomas Bulkowski, *Encyclopedia of Chart Patterns*, 2021).

### Why It Works

After a sharp advance (the flagpole), profit-taking creates a brief, orderly pullback on declining volume. The tight range signals that sellers are exhausted and buyers are simply waiting for the next catalyst. When volume returns on the breakout, the prior momentum resumes.

> "Bull flags have a success rate of 67% with an average rise of 23%." -- Thomas Bulkowski

### Entry Rules

1. Prior strong move up (flagpole) of 10% or more in 1-3 weeks
2. Tight consolidation on declining volume (the flag) lasting 5-15 bars
3. Price stays above the EMA(21) during the flag
4. Flag duration is less than 50% of the flagpole duration
5. Breakout above the flag high on a volume surge (above 50-day average)

### Exit Rules

- **Stop Loss:** Below the flag low or 1.5x ATR below entry
- **Target 1:** Measured move -- the flagpole length projected upward from the breakout point
- **Target 2:** 1.5x the measured move
- **Trailing Stop:** Below the most recent swing low

### Ideal Market Conditions

Bull Flags work best in trending markets with broad momentum. The pattern is less reliable in late-stage moves where the flagpole may represent a climax run rather than the start of a new leg. Avoid in low-volume environments.

### Performance Summary

| Metric | Value |
|---|---|
| Win Rate (Trending) | 67% |
| Win Rate (Ranging) | 44% |
| Avg R-Multiple | 1.6 |
| Avg Hold Days | 5 |
| Sample Size | 75+ trades |
| Source | Bulkowski, *Encyclopedia of Chart Patterns* |

### Pattern Illustration

```
Price
  |                  /--- Breakout (measured move) ->
  |                 /
  |        --------/  <- Flag (5-15 bars, declining vol)
  |       / \     /
  |      /   \___/
  |     /  Flagpole
  |    /   (10%+ move)
  |___/____________________________
```

[EasySwing.trading](https://easyswing.trading/strategies) scans for Bull Flag setups daily across 2,000+ US stocks.

---

## 9. Anchored VWAP Bounce

The Anchored VWAP Bounce is an institutional-flow setup that identifies support at volume-weighted average price levels anchored to significant events. Across tested anchor points, it produces a 55-63% win rate with an average reward-to-risk of 1.4:1 (Source: Brian Shannon, *Technical Analysis Using Multiple Timeframes*; quantified backtests).

### Why It Works

Institutional traders anchor their VWAP calculations to events that caused them to build positions: earnings reports, IPO dates, 52-week highs. When price returns to these levels, the same institutions often defend their average cost by adding shares. This creates reliable support that retail traders can identify and exploit.

### Entry Rules

1. Identify a significant anchor point (earnings gap, IPO date, major pivot high/low)
2. Price pulls back to the anchored VWAP level calculated from that event
3. Price shows support at the AVWAP with 2-3 candles holding above it
4. Volume picks up on the bounce candles
5. RSI(14) is above 40 at the time of the bounce

### Exit Rules

- **Stop Loss:** 1.0x ATR below the AVWAP level
- **Target 1:** 1.5x ATR above entry
- **Target 2:** Prior swing high
- **Trailing Stop:** Below the most recent swing low or 1.5x ATR from highs

### Ideal Market Conditions

Anchored VWAP Bounces work in trending-up and ranging markets where institutions are actively managing positions. The setup requires a clearly identifiable anchor event. Avoid in bear markets or for stocks with no clear institutional anchor point.

### Performance Summary

| Metric | Value |
|---|---|
| Win Rate (Trending Up) | 63% |
| Win Rate (Bear Market) | 38% |
| Avg R-Multiple | 1.4 |
| Avg Hold Days | 6 |
| Sample Size | 50+ trades |
| Source | Shannon methodology / quantified backtest |

### Pattern Illustration

```
Price
  |  Earnings Gap
  |  |   /\
  |  v  /  \          /--- Bounce ->
  |  __/    \        /
  |          \      / Support at AVWAP
  |    AVWAP--\----x-----------
  |            \  /
  |             \/  Pullback to AVWAP
  |________________________________
```

[EasySwing.trading](https://easyswing.trading/strategies) scans for Anchored VWAP Bounce setups daily across 2,000+ US stocks.

---

## 10. Triple RSI Divergence

The Triple RSI Divergence is a reversal setup that identifies exhaustion when price makes three consecutive new extremes while RSI fails to confirm. Across ranging and transitioning markets, it produces a 50-58% win rate with an average reward-to-risk of 1.8:1 (Source: Andrew Cardwell RSI methodology; quantified backtests).

### Why It Works

Single divergences fail frequently. Double divergences are more reliable. Triple divergences represent a rare and powerful exhaustion signal -- three attempts by price to extend the trend, each met with diminishing momentum. This triple failure dramatically increases the probability of a reversal.

### Entry Rules (Bullish)

1. Price makes 3 consecutive lower lows
2. RSI(14) makes 3 corresponding higher lows (bullish divergence)
3. The third divergence occurs near a known support level
4. Volume is declining into the pattern (selling exhaustion)
5. A confirmation candle appears: bullish engulfing, hammer, or morning star

### Entry Rules (Bearish)

1. Price makes 3 consecutive higher highs
2. RSI(14) makes 3 corresponding lower highs (bearish divergence)
3. The third divergence occurs near a known resistance level
4. Volume is declining into the pattern
5. A confirmation candle appears: bearish engulfing, shooting star, or evening star

### Exit Rules

- **Stop Loss:** Below the lowest low of the divergence pattern (bullish) or above the highest high (bearish)
- **Target 1:** First major support/resistance level
- **Target 2:** 2.0x ATR from entry
- **Trailing Stop:** 5% from the extreme, or below the most recent swing low/high

### Ideal Market Conditions

Triple RSI Divergence works best in ranging and transitioning markets where prices oscillate between support and resistance. Avoid in strong trending markets where divergences can persist for weeks before resolving.

### Performance Summary

| Metric | Value |
|---|---|
| Win Rate (Ranging) | 58% |
| Win Rate (Strong Trend) | 35% |
| Avg R-Multiple | 1.8 |
| Avg Hold Days | 8 |
| Sample Size | 40+ trades |
| Source | Cardwell RSI methodology / quantified backtest |

### Pattern Illustration

```
Price                          RSI
  |  \                          |           /\  /\  /\
  |   \  \                     |          /  \/  \/
  |    \  \  \                 |         /
  |     1  2  3  <- Lower     |        1  2  3  <- Higher
  |               lows        |                   lows
  |         Reversal ->       |
  |________________________   |________________________
```

[EasySwing.trading](https://easyswing.trading/strategies) scans for Triple RSI Divergence setups daily across 2,000+ US stocks.

---

## Market Regime Guide

Not every strategy works in every market environment. Matching your strategy to the current market regime is one of the most important decisions a swing trader can make.

| Regime | Description | Best Strategies | Avoid |
|---|---|---|---|
| Trending Up | Major indices above rising 50/200 SMA, breadth expanding | VCP, Cup & Handle, EMA Crossover, Stage 2, Bull Flag | Triple RSI Divergence |
| Trending Down | Indices below falling 50/200 SMA, breadth contracting | Triple RSI Divergence (bearish), short setups | VCP, Cup & Handle, Stage 2 |
| Ranging | Indices oscillating in a defined range, flat SMAs | RSI Pullback, AVWAP Bounce, Triple RSI Divergence | EMA Crossover, Stage 2 |
| High Volatility | VIX above 25, large daily swings, news-driven | VWAP Reclaim (reduced size) | VCP, Cup & Handle, Bull Flag |
| Transitioning | Regime shift underway, mixed signals | Triple RSI Divergence, Power Earnings Gap | Stage 2, EMA Crossover |

---

## Risk Management Principles

No strategy produces consistent profits without disciplined risk management. These principles apply to every setup listed above.

**Position sizing.** Risk no more than 1-2% of total account equity on any single trade. Calculate position size as: `Account Risk / (Entry - Stop)`.

**R-multiple tracking.** Measure every trade outcome in multiples of the initial risk (R). A trade risking $1 per share that gains $2 per share is a 2R winner. Track your average R-multiple over 20+ trades to measure edge.

**Correlation awareness.** Avoid concentrating in a single sector or correlated group. Five breakout trades in semiconductor stocks is functionally one large bet on semiconductors.

**Maximum open positions.** Limit total open positions to 6-10 depending on account size and market regime. Reduce exposure in high-volatility regimes.

---

## Resources and Further Reading

**Live scanning and tools:**
- [EasySwing.trading Strategies Page](https://easyswing.trading/strategies) -- live scanning for all strategies listed above
- [EasySwing.trading Methodology](https://easyswing.trading/methodology) -- how we backtest and validate strategies
- [EasySwing.trading Blog](https://easyswing.trading/blog) -- deep-dive strategy articles and market analysis

**Books:**
- Minervini, M. (2013). *Trade Like a Stock Market Wizard*. McGraw-Hill.
- O'Neil, W. (2009). *How to Make Money in Stocks*. McGraw-Hill, 4th edition.
- Weinstein, S. (1988). *Secrets for Profiting in Bull and Bear Markets*. McGraw-Hill.
- Connors, L. (2009). *Short Term Trading Strategies That Work*. TradingMarkets.
- Bulkowski, T. (2021). *Encyclopedia of Chart Patterns*. Wiley, 3rd edition.

**Individual strategy deep-dives:**
- [VCP Volatility Contraction Pattern](strategies/01-vcp.md)
- [Cup and Handle](strategies/02-cup-and-handle.md)
- [EMA Crossover](strategies/03-ema-crossover.md)
- [RSI Pullback](strategies/04-rsi-pullback.md)
- [VWAP Reclaim](strategies/05-vwap-reclaim.md)
- [Power Earnings Gap](strategies/06-power-earnings-gap.md)
- [Stage 2 Breakout](strategies/07-stage-2-breakout.md)
- [Bull Flag](strategies/08-bull-flag.md)
- [Anchored VWAP Bounce](strategies/09-anchored-vwap-bounce.md)
- [Triple RSI Divergence](strategies/10-triple-rsi-divergence.md)

---

## FAQ

### What is the best swing trading strategy for beginners?

The RSI Pullback to 40 is the most beginner-friendly swing trading strategy. It has the highest win rate (70-78%), the shortest average hold time (3-5 days), and the simplest entry rules. The high win rate builds confidence while limiting drawdown exposure. Once consistent with RSI Pullbacks, beginners can graduate to momentum setups like the VCP or Bull Flag.

### How long should you hold a swing trade?

Most swing trades last between 3 and 15 trading days. The specific hold time depends on the strategy: RSI Pullbacks average 3-5 days, Bull Flags average 3-8 days, and Stage 2 Breakouts can extend to 15-40 days. Let your trailing stop and targets dictate the exit -- not an arbitrary time limit.

### What win rate do you need for profitable swing trading?

A win rate as low as 40% can be profitable if your average winner is large enough relative to your average loser. What matters is the expected value: `(Win Rate x Avg Win) - (Loss Rate x Avg Loss)`. A strategy with a 50% win rate and 1.8:1 reward-to-risk ratio is more profitable than one with a 75% win rate and 0.5:1 ratio.

### What indicators are best for swing trading?

The most consistently useful indicators for swing trading are: RSI(14) for momentum and divergence, EMA(9)/EMA(21) for trend direction, SMA(50)/SMA(200) for long-term trend context, ATR(14) for stop and target placement, and volume (50-day average comparison) for confirming breakouts. Avoid using more than 3-4 indicators simultaneously -- they create conflicting signals.

### How much capital do you need for swing trading?

For US equities, a minimum of $25,000 is recommended to avoid the Pattern Day Trader (PDT) rule and to allow proper position sizing with 1-2% risk per trade. With $25,000 and 1% risk, you can risk $250 per trade, which is sufficient for most setups with stops 2-5% from entry.

### Should you swing trade in a bear market?

Most swing trading strategies listed here are designed for long (bullish) setups and perform poorly in bear markets. If you swing trade during a bear market, focus on reversal setups like Triple RSI Divergence (bearish), reduce position sizes by 50%, and raise your win-rate threshold for entries. Many experienced swing traders simply move to cash or short-only strategies during confirmed downtrends.

---

## Disclaimer

This repository is for educational and informational purposes only. Nothing here constitutes investment advice, a recommendation, or a solicitation to buy or sell any security. Past performance and backtested results do not guarantee future returns. All win rates and R-multiples cited are based on historical backtests with specific parameters and may not reflect real-world trading conditions, slippage, or commissions. Always do your own research and consult a qualified financial advisor before making trading decisions. Use at your own risk.

---

Built and maintained by **Wibo**, Head of Technology, Amsterdam -- creator of [EasySwing.trading](https://easyswing.trading), a swing trading screener scanning 2,000+ US stocks for these setups daily.
