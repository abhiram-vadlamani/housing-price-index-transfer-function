# Trend Analysis of the U.S. Housing Price Index using Time Series

A transfer-function time-series study of the relationship between 30-year
mortgage rates and the U.S. Housing Price Index (HPI), using 30 years of monthly
data. Full write-up in **`Trend_analysis_of_Housing_Price_Index.pdf`**.

*Co-authored with Niyati Srivastava and Parth Mahajan (Dec 2023).*

## Summary

The project models HPI as a function of 30-year mortgage rates via a
**transfer-function (cause-and-effect) model**, built through the standard
Box–Jenkins workflow:

- **EDA** — decomposition, distributional analysis, and outlier inspection of
  both series.
- **Prewhitening** — the mortgage-rate (input) series is reduced to white noise;
  because cross-correlation revealed feedback, the HPI (output) series is
  prewhitened as well (ARIMA(1,1,0)).
- **Transfer-function identification** — cross-correlation of the prewhitened
  series identifies the (b, s, r) = (0, 3, ·) structure; competing
  specifications are compared on residual white-noise tests, AIC, and SBC.
- **Noise modelling** — an MA(6)/AR(5) structure is fit to the residual noise;
  the noise-augmented model (Model 4) is selected (AIC 33.72, SBC 72.04).
- **Outlier analysis** — additive and level-shift outliers are detected and
  encoded as indicator variables before forecasting.
- **Forecasting** — 10-month-ahead HPI forecast with confidence bands.

**Finding.** A modest negative causal relationship from mortgage rates to HPI is
established (consistent with demand–supply intuition), though the dynamics are
substantially more complex than a linear relationship.

## Tools

SAS (`PROC ARIMA`: prewhitening, transfer-function estimation, outlier
detection, forecasting) and Python (`pandas`, `statsmodels`, `seaborn` for EDA
and decomposition). Code listings are in the report appendix.

## Contents

```
Trend_analysis_of_Housing_Price_Index.pdf   # full report with all figures
README.md
```
