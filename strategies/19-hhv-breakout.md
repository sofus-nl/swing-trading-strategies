# HHV Breakout (Donchian / Turtle)

The classic Donchian-channel breakout: enter long when price closes above the highest high of the last N bars (typically 20 or 55). This setup is the foundation of the Turtle Trading system designed by Richard Dennis and William Eckhardt in the early 1980s.

## Why It Works

A new N-day high indicates that demand has overwhelmed every level of supply that existed in the prior N bars. Empirically — and as Dennis demonstrated in the original Turtle experiment — N-day-high breakouts on US equities and commodities are persistent often enough to be profitable with appropriate risk management.

The N parameter matters:
- **N = 20.** Short-term entry, more signals, more whipsaws. Typical for swing-timeframe US equities.
- **N = 55.** Long-term entry, fewer signals, more durable trends. Original Turtle "System 2."

## Entry Rules (N = 20)

1. Price closes above the highest high of the prior 20 bars.
2. Volume on the breakout bar above 1.3x the 50-day average.
3. Price above the SMA50.
4. SMA50 sloped upward.
5. RS rank above 60.

## Exit Rules

- **Stop Loss:** Below the breakout bar's low, or 2.0x ATR below entry (the Turtles used 2N where N = ATR).
- **Target 1:** No fixed target — Turtles ran with trailing stops only.
- **Trailing Stop:** Original Turtle exit: a close below the lowest low of the prior 10 bars exits the long. For swing application: trail at 1.5–2.0x ATR from the highest close since entry.

## Ideal Market Conditions

Bull or constructive range with broad participation. The setup fails systematically in choppy markets where breakouts are followed immediately by reversals. The Turtles famously had losing years when the markets they traded entered prolonged ranges.

## Source Attribution

The Turtle Trading experiment was conducted by Richard Dennis and William Eckhardt in 1983–1984. The full rules — including the 20-day and 55-day entry signals, the 2N ATR-based position sizing, and the 10-day exit — were eventually published. The most accessible practitioner reference is **Curtis Faith, *Way of the Turtle* (2007)**, written by one of the original Turtles. Michael Covel's *The Complete TurtleTrader* (2007) is the journalistic history.

## Cross-References

- Live screening: [EasySwing.trading/strategies](https://easyswing.trading/strategies)
- Related: [ROC Breakout](18-roc-breakout.md), [VCP](01-vcp.md), [Cup and Handle](02-cup-and-handle.md)
