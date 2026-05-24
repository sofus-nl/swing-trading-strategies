# Trend Pullback (EMA20 / SMA50)

A textbook pullback continuation setup in an established uptrend, with one strict refinement: only stocks in the top 4% of relative strength (RS rank ≥ 96) qualify. The strict RS gate is what distinguishes the tuned version from the generic "buy the pullback" trade.

## Why It Works

In an established uptrend, profit-taking and short-term volatility create temporary supply spikes that resolve at moving-average reference points. The EMA20 is the most-watched short-term reference; the SMA50 is the most-watched intermediate reference. Pullbacks that hold either level tend to produce a continuation move because the structural demand is still present.

The strict RS gate (top 4% of universe) is load-bearing. Without it, the setup pulls in too many stocks with weak underlying structure — the pullback looks the same on the chart but the base rate is materially different. Empirically, the top-4% cohort produces meaningfully better continuation outcomes than the top-30% cohort.

## Entry Rules

1. Price above SMA50.
2. EMA20 above SMA50 AND both sloped upward.
3. RS rank ≥ 96 (top 4% of universe — strict filter).
4. Pullback brings price to within 1 ATR of the EMA20 (preferred) or SMA50 (acceptable).
5. Bounce candle closes in the upper half of its range with volume above the 20-day average.
6. Grade A only — the EasySwing engine grades each setup A through D based on confluence; this strategy is tuned to A-only.

## Exit Rules

- **Stop Loss:** 1.5x ATR below entry, or below the EMA20, whichever is tighter.
- **Target 1:** 2.0x ATR above entry — scale 50%.
- **Target 2:** Trail with a swing-low stop or 1.5x ATR from highs.
- **Hard exit:** Two consecutive closes below the SMA50.

## Ideal Market Conditions

Bull market or constructive range. The setup tolerates a wider regime band than pure breakout setups because pullback-and-resume patterns can work in non-trending environments as long as the individual stock retains a tight uptrend structure. The RS≥96 gate effectively self-screens for environments where leadership exists.

## Status

Tuned. The combination of strict RS gate + grade-A confluence + EMA20/SMA50 entry trigger passed all four autoresearch gates (holdout PF, robustness, permutation null, Sharpe haircut) on the most recent sweep.

## Source Attribution

The pullback-to-rising-MA setup is foundational — variants appear across O'Neil's CAN SLIM, Minervini's framework, Weinstein's Stage 2 management, and most modern momentum schools. The specific combination of EMA20 / SMA50 + RS≥96 + grade-A confluence is the EasySwing-tuned formalization.

## Cross-References

- Live screening: [EasySwing.trading/strategies](https://easyswing.trading/strategies)
- Deep dive: [Pullback to rising MA — trend entry](https://easyswing.trading/blog/pullback-to-rising-ma-trend-entry)
- Background: [RS rank — relative strength for swing trading](https://easyswing.trading/blog/rs-rank-relative-strength-swing-trading)
- Related: [Proximity Pullback](21-proximity-pullback.md), [MA Stack Confluence](13-ma-stack-confluence.md)
