# Does the Fed Drive the Market?
**S&P 500 Returns vs. Macroeconomic Indicators | Python + FRED API**

## Overview
This project examines whether Federal Reserve policy and key macroeconomic 
indicators — the Fed Funds Rate, CPI, and Unemployment — can explain 
monthly S&P 500 returns. Data is pulled directly from the FRED API 
(Federal Reserve Economic Data) and covers 2000 to present.

## Methodology
- **Data Source:** FRED API via `fredapi` (St. Louis Fed)
- **Series Used:** SP500, FEDFUNDS, CPIAUCSL, UNRATE
- **Analysis:** OLS Multiple Regression (`statsmodels`)
- **Visualizations:** Time series plots, correlation heatmap (`matplotlib`, `seaborn`)

## Key Findings
- The model is statistically significant overall (F-stat p = 0.005)
- **Unemployment** is the strongest individual predictor (coef = 0.91, p < 0.001)
  — consistent with markets rallying during labor market recoveries
- **Fed Funds Rate** shows a borderline positive relationship (p = 0.057)
- **CPI** loses individual significance due to high collinearity with the 
  Fed Funds Rate (r = 0.78) — a multicollinearity limitation noted in the output
- R² = 0.107: macro indicators explain ~11% of monthly return variance, 
  consistent with the noise inherent in short-horizon equity returns

## Limitations
- OLS assumes linear relationships and no serial correlation
- Monthly frequency may obscure lead/lag dynamics between policy and markets
- Multicollinearity between CPI and FedFunds warrants caution in 
  interpreting individual coefficients

## Tools
Python 3.13 | fredapi | pandas | statsmodels | matplotlib | seaborn | Jupyter Notebook
