# ROC Breakout

A momentum-confirmed breakout setup that combines a classical price breakout with accelerating Rate-of-Change. The breakout trigger only fires when momentum is expanding, not flat or contracting.

## Why It Works

Many price breakouts fail because the underlying momentum is weak — the move is occurring on extended price terms but the rate at which gains are accumulating is decelerating. By overlaying a Rate-of-Change condition, the setup filters out tired breakouts that are statistically more likely to fade.

Rate-of-Change at the breakout point measures the percent return over a fixed lookback (typically 21 days). Accelerating ROC means the most recent slope is steeper than the prior slope — momentum is building into the breakout, not draining out of it.

## Entry Rules

1. Price closes above the highest high of the last 20 bars (20-day Donchian breakout).
2. ROC(21) is positive AND higher than its 5-bar-ago value (accelerating).
3. Volume on the breakout bar above 1.4x the 50-day average.
4. Price above the SMA50.
5. RS rank above 70.

## Exit Rules

- **Stop Loss:** Below the prior 20-day high (now support) or 1.5x ATR below entry.
- **Target 1:** 2.0x ATR above entry — scale 50%.
- **Target 2:** Trail with a swing-low stop.
- **Hard exit:** ROC turns negative while in the trade.

## Ideal Market Conditions

Bull market. Breakouts of any flavor fail systematically in ranging and bearish regimes. The ROC acceleration filter helps in transitioning regimes by rejecting tepid breakouts, but it doesn't rescue the setup in a confirmed downtrend.

## Source Attribution

Rate-of-Change is one of the oldest momentum indicators in the technical analysis literature; specific provenance is diffuse. Thomas Bulkowski's *Encyclopedia of Chart Patterns* documents 20-day-high breakouts extensively. The specific combination — Donchian breakout + accelerating ROC + volume — is a composite synthesis.

## Cross-References

- Live screening: [EasySwing.trading/strategies](https://easyswing.trading/strategies)
- Related: [HHV Breakout (Donchian)](19-hhv-breakout.md), [Multi-Period Strength](12-multi-period-strength.md)
