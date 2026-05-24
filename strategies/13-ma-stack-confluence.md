# MA Stack Confluence (10 / 21 / 50 / 200)

A momentum filter that requires four moving averages in perfect bullish alignment: EMA10 > EMA21 > SMA50 > SMA200, all sloped upward, with price riding the EMA10. This is the strictest version of the moving-average-stack filter family.

## Why It Works

Each moving average represents a different participant cohort's reference price. When all four are stacked in the correct order with positive slopes, short-term traders, intermediate-horizon active managers, and long-term institutional holders are all positioned the same way. There is no overhead supply from a higher reference average — every reference is below current price, supporting the structure.

When one of the four MAs breaks the stack (e.g., SMA50 crosses below SMA200, or EMA10 falls under EMA21), the confluence breaks and the structural support thesis weakens.

## Entry Rules

1. EMA10 > EMA21 > SMA50 > SMA200 (perfect alignment).
2. All four moving averages sloped upward over the last 5+ bars.
3. Price within 5% of EMA10 (riding the short-term reference, not extended).
4. Volume on the entry day or trigger day above the 20-day average.
5. RS rank above 70.

## Exit Rules

- **Stop Loss:** 1.5x ATR below entry, or below the EMA21, whichever is tighter.
- **Target 1:** 2.5x ATR above entry — scale 50%.
- **Target 2:** Hold the remainder until the EMA10 / EMA21 stack breaks.
- **Hard exit:** Close below SMA50 closes the position.

## Ideal Market Conditions

Bull market. In a range, the four MAs flatten and the slope condition fails. In a transitioning regime, the short-term MAs (EMA10/EMA21) cross frequently, producing whipsaws. The setup is most reliable in months 6–18 of a confirmed bull trend.

## Source Attribution

The "moving average stack" idea is common across multiple traditions: Minervini's Trend Template uses a 50/150/200 stack, IBD uses 21/50/200, and Weinstein's stage analysis uses the 30-week MA. The specific 10/21/50/200 confluence is a composite synthesis tuned for the daily timeframe.

## Cross-References

- Live screening: [EasySwing.trading/strategies](https://easyswing.trading/strategies)
- Background: [Moving averages for swing trading](https://easyswing.trading/blog/moving-averages-for-swing-trading)
- Related: [Trend Template Fresh Pass](16-trend-template-fresh-pass.md), [Trend Pullback](23-trend-pullback.md)
