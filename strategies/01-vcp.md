# VCP (Volatility Contraction Pattern)

> **The VCP identifies institutional accumulation through a series of tightening price contractions, producing a 72% win rate in trending markets with an average 1.8R reward-to-risk ratio.**

## Overview
- **Author/Origin:** Mark Minervini, *Trade Like a Stock Market Wizard* (2013)
- **Family:** Momentum
- **Direction:** Long
- **Best Market Regime:** Trending Up
- **Typical Hold Time:** 8-15 days

## Why It Works

The Volatility Contraction Pattern exploits a specific phase of institutional accumulation. When large funds build positions in a stock, they cannot buy all at once without moving the price against themselves. Instead, they absorb shares gradually over weeks, buying on dips and pausing on rallies. Each successive pullback within the base becomes shallower as the available supply of shares diminishes. This contraction in volatility is the fingerprint of smart money at work.

> "The VCP is the single most powerful base pattern." -- Mark Minervini

From a market microstructure perspective, the tightening ranges reflect a transfer of shares from weak hands (emotional sellers) to strong hands (institutional buyers with conviction). Volume dries up during the later contractions because most willing sellers have already exited. When demand finally overwhelms the remaining supply, the stock breaks out on a surge of volume -- confirming that the absorption phase is complete.

The pattern's edge comes from its asymmetric risk profile. By entering at the breakout pivot with a tight stop below the final contraction, traders risk a small amount relative to the potential reward. Minervini's own track record -- a 220% average annual return over five consecutive years -- demonstrates the power of combining VCP entries with strict position sizing and market direction filters.

## Entry Rules

1. Price is above the 50-day, 150-day, and 200-day Simple Moving Averages (SMA stack aligned bullish)
2. The 50-day SMA is above the 150-day SMA, which is above the 200-day SMA
3. At least 3 identifiable contracting pullbacks are visible in the base
4. Each successive pullback is shallower than the previous one (e.g., 15% -> 8% -> 4%)
5. Volume has dried up significantly during the final contraction (below 50-day average)
6. Relative Strength (RS) rank is above 70, indicating the stock is outperforming most of the market
7. Breakout occurs above the pivot point (high of the most recent contraction) on volume at least 40% above the 50-day average
8. The overall market regime is trending up (confirmed by major index above 200-day SMA)
9. Stock has a prior uptrend of at least 25% before the base begins forming
10. Price is within 25% of the 52-week high

## Exit Framework

### Stop Loss
Place the initial stop 1.5x ATR(14) below the entry price. This typically falls just below the low of the final contraction, giving the trade room to breathe while limiting downside to a defined risk unit.

### Target 1 (Scale Out)
Exit 50% of the position at 2.0x ATR above entry. This locks in a 1.33R profit on half the position and reduces risk on the remainder.

### Target 2 (Remainder)
Exit the remaining 50% at 4.0x ATR above entry. This captures the extended move that institutional buying often produces, targeting a 2.67R return on the second tranche.

### Trailing Stop
After Target 1 is hit, trail the stop below the most recent swing low on the daily chart. This allows the position to ride the trend while protecting profits. If the stock closes below the trailing swing low, exit the remainder.

## Performance Data

| Metric | Value |
|--------|-------|
| Win Rate (Best Regime) | 72% |
| Win Rate (Worst Regime) | 45% |
| Avg R-Multiple | 1.8R |
| Avg Hold Days | 11 |
| Sample Size | 48+ trades |
| Source | Quantified Strategies backtest |

*Note: Backtested results do not guarantee future performance. See [methodology](https://easyswing.trading/methodology) for testing approach and limitations.*

## Common Mistakes

- **Buying before the breakout.** Anticipating the breakout removes the confirmation signal. The volume surge on breakout day is what validates the setup.
- **Ignoring volume on breakout day.** A breakout on average or below-average volume is a false signal. The 40% above average threshold exists for a reason.
- **Trading VCPs in bear markets.** VCPs require institutional demand. In bear markets, institutions are distributing, not accumulating. Win rates drop sharply to 45% or lower in ranging or bearish conditions.
- **Not having a defined stop.** The VCP's edge depends on small losses and large gains. Without a predetermined stop at 1.5x ATR, losses can quickly exceed the expected risk unit.
- **Forcing VCPs where only 1-2 contractions exist.** A single pullback is not a VCP. The pattern requires at least 3 contracting waves to confirm that supply is genuinely being absorbed.

## Live Scanning

[EasySwing.trading](https://easyswing.trading/strategies) scans for VCP Breakout setups daily across 2,000+ US stocks with automated alerts. The scanner identifies SMA stack alignment, contraction count, volume dry-up, relative strength rank, and breakout confirmation.

---
*[Back to Strategy Library](../README.md)*
