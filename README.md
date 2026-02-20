# AMD CAPM & Fama-French Factor Analysis

Empirical asset pricing analysis of AMD using CAPM, Fama-French 3-factor and 5-factor models, plus industry portfolio comparison, long-term reversal effects, and value premium testing.

## Overview

Completed as part of **Empirical Methods in Finance 6334** at Northeastern University (Spring 2026). The project applies core asset pricing models to real market data using Python, covering seven analytical questions spanning single-stock analysis to market anomaly testing.

## Analysis Summary

### Q1: Single Stock CAPM — AMD
- AMD beta of **1.89** indicates nearly 2x market sensitivity, consistent with high-cyclicality semiconductors
- Alpha not significant (p = 0.81) — no evidence of abnormal risk-adjusted returns
- R² = 0.347 — market explains ~35% of AMD's return variation; 65% is idiosyncratic risk

### Q2: Two-Stock Comparison — AMD vs. Berkshire Hathaway
- AMD (β = 1.89) vs. Berkshire (β = 0.85) — aggressive vs. defensive risk profiles
- F-test rejects equal betas (F = 6.35, p = 0.014), confirming statistically different systematic risk

### Q3: Fama-French Three-Factor Model
- R² improves from 0.347 (CAPM) to 0.409 (FF3)
- HML coefficient of −0.85 (p = 0.053) — AMD behaves like a growth stock
- Joint F-test: SMB and HML not jointly significant (p = 0.13)

### Q4: Industry Portfolio Analysis — Tech vs. Healthcare
- Tech beta (0.99) > Healthcare beta (0.87); F-test confirms difference (F = 34.24, p < 0.001)
- Healthcare recommended for recession overweight — lower beta, inelastic demand

### Q5: Five-Factor Model
- All five factors jointly significant (F = 5.84, p = 0.0002)
- RMW and CMA add no incremental power (F = 0.20, p = 0.82)
- **FF3 is the best model** — highest adjusted R² (0.323) and lowest AIC (−60.31)

### Q6: Long-Term Reversal Effect
- Full sample: reversal premium of **0.74% per month** (t = 4.96, p ≈ 0)
- 20th century: strong effect (t = 5.19); 21st century: **completely disappears** (t = 0.57, p = 0.57)
- CAPM alpha not significant — reversal likely driven by behavioral overreaction, not risk

### Q7: Is the Value Premium Dead?
- Full sample value premium: essentially zero (0.007% per month)
- Neither century shows statistical significance; sign flips negative post-2000
- Conclusion: weakened but not dead — measurement issues with intangibles and macro conditions explain recent underperformance

## Key Results

| Model | R² | Adj. R² | AIC |
|-------|-----|---------|------|
| CAPM | 0.277 | 0.264 | −57.47 |
| FF3 | 0.359 | 0.323 | −60.31 |
| FF5 | 0.364 | 0.302 | −56.75 |

## Data Sources

- **Stock returns:** Yahoo Finance (AMD, Berkshire Hathaway)
- **Factor data:** [Ken French's Data Library](https://mba.tuck.dartmouth.edu/pages/faculty/ken.french/data_library.html)
- **Portfolios:** 5 Industry Portfolios, 10 Reversal Portfolios, 100 B/M Sorted Portfolios

## Tools Used

- Python (pandas, numpy, statsmodels, scipy)
- OLS regression, F-tests, t-tests, AIC/BIC model comparison

## Files

- `Empirical_Methods_HW.ipynb` — Full Jupyter Notebook with all code and outputs
- `Empirical_Methods_Report.pdf` — Written report with interpretations and economic reasoning
- `AMD - Stock return.xlsx` — AMD monthly return data
- `Berkshire Hathaway Inc.xlsx` — Berkshire monthly price data
- `F-F_Research_Data_Factors.xlsx` — Fama-French 3-factor data
- `F-F_Research_Data_5_Factors_2x3.xlsx` — Fama-French 5-factor data
- `5_Industry_Portfolios.xlsx` — Industry portfolio returns
- `10_Portfolios_Prior_60_13.CSV` — Long-term reversal portfolios
- `100_Portfolios_10x10.xlsx` — Book-to-market sorted portfolios
