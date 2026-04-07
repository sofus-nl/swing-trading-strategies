# Risk Management for Swing Traders

> **The difference between profitable and unprofitable traders is rarely strategy selection -- it is risk management.**

Every strategy in this repository assumes disciplined risk management. A strategy with a 70% win rate will blow up an account without proper position sizing and drawdown controls. The rules below are non-negotiable fundamentals.

---

## The 1-2% Rule

Never risk more than 1-2% of your total account equity on a single trade. "Risk" means the dollar amount you lose if your stop loss is hit -- not the total position value.

**Example:** $50,000 account with a 1% risk limit.

- Maximum risk per trade: $50,000 x 0.01 = **$500**
- If your stop is $2 below entry, you can buy 250 shares ($500 / $2)
- If your stop is $5 below entry, you can buy 100 shares ($500 / $5)

The 1% rule ensures that even a string of 10 consecutive losses only draws down the account by approximately 10%. At 2% risk, that same losing streak costs approximately 18%. Above 2%, the math turns destructive quickly.

---

## Position Sizing Formula

```
Position Size (shares) = Risk Amount / (Entry Price - Stop Price)
```

**Worked example:**

| Parameter        | Value   |
|------------------|---------|
| Account size     | $50,000 |
| Risk per trade   | 1%      |
| Risk amount      | $500    |
| Entry price      | $48.00  |
| Stop price       | $45.50  |
| Risk per share   | $2.50   |
| **Position size** | **200 shares** |
| Position value   | $9,600 (19.2% of account) |

Notice that the position value ($9,600) is a consequence of the risk calculation, not the input. You never decide position size based on "I want to put 20% into this stock." You always derive it from risk.

ATR-based stops produce consistent position sizing because ATR normalizes for a stock's volatility. A $500 stock with ATR $15 gets the same dollar risk as a $25 stock with ATR $0.75.

---

## R-Multiple Tracking

An R-multiple expresses trade outcomes as multiples of initial risk (R).

- Entry at $48, stop at $45.50 = R = $2.50
- Exit at $53 = profit of $5 = **+2.0R**
- Exit at $45.50 (stopped out) = loss of $2.50 = **-1.0R**

R-multiples allow direct comparison across trades regardless of share price, position size, or account value.

**A 50% win rate strategy is profitable if the average winner exceeds the average loser.** The table below shows expected R per trade for various win rate and reward-to-risk combinations:

| Win Rate | 1:1 R:R | 1.5:1 R:R | 2:1 R:R | 3:1 R:R |
|----------|---------|-----------|---------|---------|
| 40%      | -0.20R  | +0.10R    | +0.20R  | +0.60R  |
| 50%      | 0.00R   | +0.25R    | +0.50R  | +1.00R  |
| 60%      | +0.20R  | +0.50R    | +0.80R  | +1.40R  |
| 70%      | +0.40R  | +0.75R    | +1.10R  | +1.80R  |

Key insight: a strategy with a 40% win rate and 3:1 R:R (+0.60R expected) outperforms a strategy with a 70% win rate and 1:1 R:R (+0.40R expected). Win rate alone is meaningless without the R:R context.

Track every trade in R-multiples. After 30+ trades, your average R tells you exactly how your strategy performs.

---

## Maximum Open Positions

Limit concurrent open positions to **5-8 trades maximum**.

**Why:**

- **Concentration risk.** 10+ positions in the same sector during a sector rotation event creates correlated losses that exceed single-trade risk limits.
- **Attention capacity.** Each open position requires monitoring for stop adjustments, target exits, and changed conditions. Beyond 8 positions, execution quality degrades.
- **Correlation.** In a market selloff, most long positions decline together. Eight 1%-risk positions that all hit their stops simultaneously produce an 8% drawdown -- survivable. Fifteen positions produce 15% -- damaging.

A practical allocation framework:

| Account Tier     | Max Positions | Risk Per Trade |
|------------------|---------------|----------------|
| Under $25,000    | 4-5           | 1%             |
| $25,000-$100,000 | 5-7           | 1%             |
| Over $100,000    | 6-8           | 0.5-1%         |

Reduce the number of open positions in High Volatility and Transitioning regimes.

---

## Drawdown Management

Drawdowns are inevitable. The question is how you respond to them.

**Rules:**

1. **After 3 consecutive losses:** Reduce position size by 50% (from 1% to 0.5% risk per trade). This is not a punishment -- it is a statistical response. Three consecutive losses may indicate a regime change that your strategy is not suited for.

2. **After 5% portfolio drawdown:** Stop opening new positions for the remainder of the week. Review all open positions and tighten stops. Assess whether the market regime has changed.

3. **After 10% portfolio drawdown:** Move to cash entirely. Conduct a full strategy review. Do not resume trading until you have identified the cause (regime mismatch, execution errors, or normal variance).

4. **Recovery scaling:** When resuming after a drawdown halt, start at 50% position size for the first 5 trades. Return to full size only after 3 of those 5 trades are profitable.

The math of recovery is asymmetric: a 10% loss requires an 11.1% gain to recover. A 20% loss requires 25%. A 50% loss requires 100%. Aggressive drawdown management keeps you in the recoverable zone.

---

Position sizing and drawdown management are mechanical processes. Remove emotion by calculating these numbers before entering every trade.

For automated position sizing calculations and risk management tools, visit [EasySwing.trading](https://easyswing.trading).
