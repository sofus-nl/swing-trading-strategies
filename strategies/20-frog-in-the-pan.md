# Frog-in-the-Pan

A momentum setup that targets stocks repricing slowly on a steady drumbeat of small positive returns rather than on dramatic news. Named after the "boiling frog" metaphor by Da, Gurun & Warachka (2014), who formalized the effect as "Information Discreteness."

## Why It Works

Markets under-react to gradually-arriving information. A stock with a series of small positive daily returns — none individually large enough to attract retail attention or media coverage — is being repriced quietly by informed participants. The full repricing arrives over weeks or months, not days. By the time the cumulative move is large enough to show up on screens that filter by big single-day gainers, the easy part of the move is over.

Da, Gurun & Warachka demonstrated that within momentum portfolios, stocks with "low information discreteness" (the smooth, gradual gainers) significantly outperformed stocks with "high information discreteness" (the same total return delivered in a few large jumps).

## Information Discreteness (ID) Score

A simple operational version:

```
sign = +1 if cumulative N-month return > 0, else -1
neg_share = fraction of daily returns over N months that are negative
pos_share = fraction of daily returns that are positive
ID = sign * (neg_share - pos_share)
```

Low ID (close to -1 in absolute value when the cumulative return is positive) indicates a smooth, gradual climb — the Frog-in-the-Pan stock.

## Entry Rules

1. Cumulative 6-month return positive AND above sector baseline.
2. ID score low (smooth, gradual gains — typically lowest tercile of ID within the high-momentum cohort).
3. No single daily gap exceeding 6% over the 6-month window (gaps break the "continuous information" hypothesis).
4. Price above SMA50 and SMA200.
5. Entry on a pullback to EMA21 or on a new 20-day high after consolidation.

## Exit Rules

- **Stop Loss:** 2.0x ATR below entry.
- **Target 1:** 2.5x ATR above entry — scale 50%.
- **Target 2:** Trail with swing-low or EMA21 stop.
- **Re-evaluate:** A single large gap (>5%) in either direction invalidates the smooth-information thesis — close or tighten the stop.

## Ideal Market Conditions

Bull market or constructive range. The setup is participation-style — it requires the broader market to allow gradual repricing to proceed. In a high-volatility regime, "smooth" returns are rare (most stocks have at least one large daily move), so the setup self-filters to low-volatility windows.

## Source Attribution

**Primary paper:** Da, Z., Gurun, U. & Warachka, M. (2014). *Frog in the Pan: Continuous Information and Momentum.* Review of Financial Studies, 27(7), 2171–2218. The paper introduces Information Discreteness and demonstrates the within-momentum outperformance of smooth-information stocks. [SSRN preprint](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=1572409).

## Cross-References

- Live screening: [EasySwing.trading/strategies](https://easyswing.trading/strategies)
- Related: [Residual Momentum](15-residual-momentum.md), [Multi-Period Strength](12-multi-period-strength.md)
