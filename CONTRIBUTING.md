# Contributing

We welcome contributions that improve the quality and accuracy of this swing trading strategy reference. Whether you spot a typo, have backtest data to share, or want to propose a new strategy, your input is valued.

## What We Accept

- **Strategy corrections** -- If a rule, statistic, or attribution is wrong, please open a PR with the correction and cite your source.
- **Additional backtest data** -- Performance data from independent backtests strengthens the resource. Include your methodology, sample size, date range, and universe.
- **New strategy proposals** -- Open an issue first to discuss before writing a full strategy document.
- **Typo and formatting fixes** -- PRs welcome, no issue required.
- **Resource additions** -- New glossary terms, risk management techniques, or educational content for the `resources/` directory.

## New Strategy Requirements

Proposed strategies must include:

1. **Entry rules** -- Specific, testable conditions (not "buy when it looks good")
2. **Exit rules** -- Stop loss placement, profit targets, and trailing stop method
3. **Valid market regimes** -- Which of the 5 regimes the strategy works in
4. **Performance data** -- Win rate, average R-multiple, sample size, and source
5. **Attribution** -- Original author or source of the strategy

Follow the existing template structure in `strategies/`. Consistency matters more than creativity in documentation.

## Process

1. **Open an issue first** for new strategies or significant changes
2. **Fork the repo** and create a feature branch
3. **Follow the existing format** -- match heading structure, table format, and tone
4. **Cite sources** for any statistical claims or corrections
5. **Submit a PR** with a clear description of what changed and why

## Guidelines

- All content must be educational and factual
- No promotional content or affiliate links
- No specific ticker recommendations
- Performance claims must include sample size and methodology
- Use plain language -- avoid jargon when a simpler term exists

---

This project is maintained by [EasySwing.trading](https://easyswing.trading).
