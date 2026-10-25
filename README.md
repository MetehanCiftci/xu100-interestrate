# Interest Rates and BIST100 Returns

Do changes in Turkish interest rates explain BIST100 returns, and does the relationship differ between TRY and USD terms?

This project analyzes about 15 years of monthly data (2011–2026) using simple linear regression. It was built as an applied project after completing HKUST's *Python and Statistics for Financial Analysis* course.

## Data

| Variable | Source |
|---|---|
| BIST100 index (`XU100.IS`) | Yahoo Finance via `yfinance` |
| USD/TRY exchange rate (`TRY=X`) | Yahoo Finance via `yfinance` |
| CBRT weighted average cost of funding (`TP_APIFON4`) | CBRT EVDS, monthly, end-of-month value |

Monthly frequency is used because the policy rate changes only a few times a year; at daily frequency, the rate-change variable would be zero on almost every day.

## Method

1. Monthly log returns of BIST100 in TRY and USD terms, and monthly changes in the interest rate (percentage points)
2. Descriptive analysis: level charts, scatter plots, histograms, correlations
3. Regressions of returns on same-month and one-month-lagged rate changes
4. Subperiod analysis across three policy regimes (2011–2021, 2021–2023 easing, 2023 onward)
5. Regression assumption checks and a robustness check excluding the largest rate hikes

## Key Findings

- **Nominal gains largely reflect currency depreciation.** BIST100 rose about twentyfold in TRY terms but ended below its starting level in USD terms.
- **No significant relationship in the full sample.** Rate changes explain at most 1.3% of monthly return variation and do not predict next month's returns.
- **The relationship depends on the policy regime.** During the 2021–2023 easing period, each one-point cut was associated with a 6.8% higher monthly TRY return, with no significant effect in USD terms.
- **The effect depends on the size of the change.** Excluding the four largest hikes, a one-point hike is associated with a 1.3% lower monthly USD return (p = 0.01). Large, decisive hikes coincided with positive returns.

## Limitations

Small and regime-dependent sample, possible reverse causality, nominal rates without an inflation adjustment, heteroskedastic residuals, and exploratory subsample and robustness tests. See the conclusion section of the notebook for details.

## How to Run

Requirements:

Place `EVDS_25-10-2026.xlsx` in the same folder as the notebook and run `xu100interestrate.ipynb` from top to bottom.

## Author

Metehan Çiftçi
