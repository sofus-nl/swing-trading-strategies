# RSI Reversion (Connors 2-period)

Larry Connors's short-term mean-reversion setup. Use a 2-period RSI rather than the conventional 14-period — RSI(2) is responsive enough to catch temporary oversold dislocations in real uptrends without producing false signals in actual downtrends.

## Why It Works

Strong uptrends produce temporary oversold dislocations as profit-taking and short-term volatility push prices below short-term equilibrium. These dislocations resolve quickly because the underlying demand is still present. RSI(2) — drastically shorter than the conventional RSI(14) — fires only on genuine short-term dislocations, not on the slower drift toward oversold that a real downtrend produces.

The setup deliberately uses a long-term trend filter (price above SMA200) to ensure the broader regime is constructive. Without that filter, RSI(2) buying becomes a "catch a falling knife" strategy in bear markets.

## Entry Rules

1. Price above SMA200 (long-term uptrend confirmed — the load-bearing filter).
2. RSI(2) closes below 10.
3. Stock has not gapped down on news in the prior 2 sessions (no catalyst-driven dislocation).
4. The most recent close is at least 5% above the 52-week low (avoid distressed names).

## Exit Rules

- **Stop Loss:** 2.0x ATR below entry — wider than typical because RSI(2) entries are intra-volatility events.
- **Target / Exit:** Close the position when RSI(2) crosses back above 70, OR after 5 bars maximum hold (whichever fires first). No second target — this is a quick mean-reversion, not a trend trade.
- **Hard exit:** Close below SMA200 invalidates the setup; exit immediately.

## Ideal Market Conditions

Bull or constructive range. The setup is regime-agnostic above SMA200 — it works as long as the stock is in a genuine uptrend. In a confirmed downtrend (stock below SMA200), the same RSI(2) signal becomes a trap.

## Status

Tuned-provisional in the EasySwing autoresearch sweep. The strategy is profitable on the holdout window with PF ≈ 1.7, but the detector's intrinsic gates filter the universe exhaustively enough that the shuffle-returns permutation null degenerates — the params are published for inspection but not auto-adopted as live overrides.

## Source Attribution

**Primary book:** Larry Connors. *Short Term Trading Strategies That Work* (2009). The book formalizes the 2-period RSI mean-reversion approach across multiple market and asset classes.

## Cross-References

- Live screening: [EasySwing.trading/strategies](https://easyswing.trading/strategies)
- Deep dive: [RSI mean reversion oversold bounce](https://easyswing.trading/blog/rsi-mean-reversion-oversold-bounce)
- Related: [RSI Pullback to 40](04-rsi-pullback.md) (honorable mention, conventional RSI(14) variant)
