# Volume-Weighted Trend

A multi-day trend confirmation that requires price to be above a rising 21-day VWAP AND recent up-volume to materially exceed recent down-volume. The setup is the swing-timeframe cousin of intraday VWAP-reclaim setups, applied to daily bars.

## Why It Works

VWAP is the institutional execution benchmark. When price is persistently above the 21-day VWAP, the average institutional position entered in the last month is profitable — those holders are motivated to defend the structure. When up-volume dominates down-volume over the same window, the demand is structural, not a single-day artifact.

The combination of above-VWAP price action + up-volume dominance is one of the cleanest "institutions are accumulating, not distributing" signals available on daily bars.

## Entry Rules

1. Price above the 21-day rolling VWAP.
2. 21-day VWAP sloped upward.
3. Up-volume (volume on green bars) over the last 21 bars greater than 1.5x down-volume.
4. Price above the SMA50.
5. RS rank above 70.
6. Entry on a pullback toward the rising 21-day VWAP or on a continuation breakout.

## Exit Rules

- **Stop Loss:** 1.5x ATR below entry, or below the 21-day VWAP, whichever is tighter.
- **Target 1:** 2.0x ATR above entry — scale 50%.
- **Target 2:** Trail with a 1.5x ATR stop.
- **Hard exit:** Close decisively below the 21-day VWAP for two consecutive bars.

## Ideal Market Conditions

Bull or constructive range. The setup requires participation breadth — a rising VWAP plus up-volume dominance is functionally a check that the broader market or sector is contributing demand. In a confirmed downtrend the conditions rarely co-occur, so the setup self-screens.

## Source Attribution

VWAP as an institutional benchmark is decades old. The use of multi-day rolling VWAP (vs intraday session VWAP) is more recent. Brian Shannon's *Technical Analysis Using Multiple Timeframes* (2008) is the most accessible practitioner reference; the academic literature on volume-price interactions is extensive (Karpoff 1987 for an overview).

## Cross-References

- Live screening: [EasySwing.trading/strategies](https://easyswing.trading/strategies)
- Background: [Volume analysis for swing trading](https://easyswing.trading/blog/volume-analysis-swing-trading)
- Related: [Anchored VWAP Bounce](09-anchored-vwap.md), [ADX Trend Momentum](14-adx-trend-momentum.md)
