# Multi-Period Strength

A momentum setup that requires positive returns across multiple lookback windows simultaneously — typically 3-month, 6-month, and 12-month. The setup belongs to the Jegadeesh-Titman momentum lineage and is closest in spirit to academic cross-sectional momentum, adapted for daily-timeframe swing trading.

## Why It Works

Single-window momentum measurements can be polluted by a single big day or a recent news catalyst. Multi-window confirmation indicates that the stock's strength is structural — it has outperformed across the medium and longer horizons that informed institutional buyers care about, not just over the last few weeks.

The classical academic result (Jegadeesh & Titman, 1993) showed that a portfolio of stocks with positive 6-month and 12-month returns outperformed a portfolio of negative-momentum stocks over the subsequent 3–12 months. This setup is the single-stock entry trigger derived from that effect.

## Entry Rules

1. 3-month total return positive AND above a sector / index baseline.
2. 6-month total return positive AND above baseline.
3. 12-month total return positive AND above baseline.
4. Price above SMA50 and SMA200, both sloped upward.
5. RS rank above 80.
6. Entry on a pullback to the EMA21 (preferred) or on the first new 20-day high after a 5+ bar consolidation.

## Exit Rules

- **Stop Loss:** 2.0x ATR below entry.
- **Target 1:** 2.5x ATR above entry — scale 50%.
- **Target 2:** Trail with a swing-low stop on the daily chart.
- **Re-evaluate:** If 3-month return turns negative while in the trade, take profits aggressively.

## Ideal Market Conditions

Bull market. The multi-period framework requires the broader market to have produced 12 months of constructive price action — which by definition does not happen during or immediately after major bear markets. In a healthy bull, this is one of the more durable filters available.

## Source Attribution

- **Foundational paper:** Jegadeesh, N. & Titman, S. (1993). *Returns to Buying Winners and Selling Losers: Implications for Stock Market Efficiency.* Journal of Finance, 48(1), 65–91.
- The single-stock trigger formalization is a composite — variants appear across CAN SLIM, Driehaus's momentum framework, and modern factor-based screeners.

## Cross-References

- Live screening: [EasySwing.trading/strategies](https://easyswing.trading/strategies)
- Background: [RS rank — relative strength for swing trading](https://easyswing.trading/blog/rs-rank-relative-strength-swing-trading)
- Related: [Residual Momentum](15-residual-momentum.md), [ROC Breakout](18-roc-breakout.md), [Trend Template Fresh Pass](16-trend-template-fresh-pass.md)
