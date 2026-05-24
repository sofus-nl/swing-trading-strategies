# Residual Momentum

A momentum setup that ranks stocks on the portion of their 6–12 month return that is NOT explained by the broader market or sector. Originally proposed by Blitz, Huij & Martens (2011) as a refinement of classical momentum.

## Why It Works

Classical 12-month momentum (Jegadeesh-Titman) has well-documented "momentum crashes" — periods when high-momentum stocks underperform sharply as leadership rotates. Blitz, Huij & Martens showed that the residual portion of momentum — what remains after subtracting factor exposures (market, size, value, sector) — carries the bulk of the signal and is far less prone to crashes.

For practical purposes: a stock with high raw momentum may be high simply because its sector is hot. A stock with high residual momentum is genuinely outperforming its sector and the market — its strength is idiosyncratic, not borrowed from the rotation.

## Entry Rules — "Poor Man's" Residual Momentum

(Full residual computation requires factor regression; this is the daily-timeframe operational approximation.)

1. Stock's 6-month total return is in the top quartile of its universe.
2. After subtracting the sector ETF's 6-month return (sector beta ≈ 1), the residual is still positive and large.
3. After subtracting SPY's 6-month return (market beta ≈ 1), the residual is still positive.
4. Price above SMA50 and SMA200.
5. Entry on a pullback to EMA21 or on a fresh 20-day high after consolidation.

## Exit Rules

- **Stop Loss:** 2.0x ATR below entry.
- **Target 1:** 2.5x ATR above entry — scale 50%.
- **Target 2:** Trail with a swing-low stop.
- **Re-evaluate:** Recompute residual monthly. If the stock falls out of the top quartile, take profits aggressively.

## Ideal Market Conditions

Bull market. Residual momentum dampens the rotation risk but does not eliminate the need for a constructive broad-market backdrop. In a bear market, even the top residual-momentum stocks decline — they just decline less than the market.

## Source Attribution

**Primary paper:** Blitz, D., Huij, J. & Martens, M. (2011). *Residual Momentum.* Journal of Empirical Finance, 18(3), 506–521. The paper formalizes the residual computation and demonstrates reduced momentum-crash exposure on US and international equities. [SSRN preprint](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=1132921).

**Related lineage:** Jegadeesh & Titman (1993), Fama & French (1996), Carhart (1997).

## Cross-References

- Live screening: [EasySwing.trading/strategies](https://easyswing.trading/strategies)
- Related: [Multi-Period Strength](12-multi-period-strength.md), [Trend Template Fresh Pass](16-trend-template-fresh-pass.md)
