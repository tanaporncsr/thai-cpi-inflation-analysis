# Thai CPI Inflation Analysis: Decomposition and Forecast Evaluation

## Project Overview

This project analyzes Thailand's headline inflation by examining how month-over-month (MoM) price changes and base effects contribute to year-over-year (YoY) inflation. It also compares Random Forest models with a zero-MoM base-effect baseline to evaluate their forecasting performance using monthly CPI data.

## Objectives

- Analyze the relationship between monthly price changes (MoM) and year-over-year inflation (YoY).
- Examine how base effects contribute to changes in headline inflation.
- Develop and evaluate a zero-MoM base-effect baseline.
- Compare Random Forest models against the baseline and a last-month YoY benchmark.
- Evaluate forecasting performance using walk-forward validation.

## Dataset

- **Data frequency:** Monthly
- **Data period:** January 2020 – August 2026
- **Test period:** February 2024 – August 2026 (31 months)
- **Target variable:** Thailand's headline CPI YoY inflation
- **Data sources:** Bank of Thailand (BOT), Trade Policy and Strategy Office (TPSO), and U.S. Energy Information Administration (EIA)

## Methodology

1. Data Collection and Preprocessing
2. Exploratory Data Analysis of MoM and YoY Inflation
3. Base-Effect Analysis and Decomposition
4. Development of a Zero-MoM Base-Effect Baseline
5. Random Forest Model Development
6. Walk-Forward Forecast Evaluation
7. Model Performance Comparison

**Predictors:** Lagged CPI and policy-rate terms, and USD/THB exchange-rate levels and changes, including the current-month average. Brent crude oil was tested separately but was not included in the final walk-forward evaluation.

## Forecast Evaluation

Forecasting performance was evaluated over a 31-month walk-forward test period using Mean Absolute Error (MAE) and Root Mean Squared Error (RMSE).

The zero-MoM base-effect baseline achieved a lower MAE than the last-month YoY benchmark by **0.146 percentage points**.

| Evaluation | Result |
|---|---:|
| Test Period | 31 months |
| Zero-MoM Baseline MAE | 0.319 |
| MAE Improvement over Last-Month YoY Benchmark | 0.146 percentage points |
| 95% Paired Bootstrap CI | 0.068 – 0.233 percentage points |

The zero-MoM baseline recorded the lowest MAE, while Random Forest v1 recorded the lowest RMSE (0.499, compared with 0.589 for the baseline). The RMSE difference was largely influenced by the April 2026 observation.

Overall, Random Forest models did not demonstrate a clear or consistent improvement over the simpler baseline during the evaluation period.

## Key Findings

- Base effects play an important role in explaining changes in YoY inflation.
- In 5 of the 8 months with the largest Random Forest forecast errors, the base-effect contribution was larger than the current month's MoM price change.
- The zero-MoM base-effect baseline achieved a lower MAE than the last-month YoY benchmark.
- Random Forest models did not consistently outperform the simpler baseline, highlighting the importance of comparing complex models against simple benchmarks.

## Dashboard

An interactive Tableau dashboard was developed to present the analysis of Thailand's headline inflation, including monthly price changes, base effects, and forecasting performance.

**Dashboard Preview**

![Tableau Dashboard Screenshot](images/dashboard-preview.png)

## Limitations

- **Small test sample:** The walk-forward test period contains only 31 monthly observations, limiting the reliability and generalizability of the evaluation.
- **Model selection:** The MoM/base-effect framing was selected after examining test-period errors, and the same test window was reused across experiments. Therefore, the evaluation is not fully independent of the analytical choices.
- **Statistical uncertainty:** Bootstrap confidence intervals do not account for autocorrelation, which may result in overly narrow intervals.
- **Potential look-ahead bias:** Policy-rate lags were selected using full-sample correlations, introducing potential look-ahead bias.
- **Decomposition:** The MoM and base-effect decomposition is an additive approximation, with a maximum residual of approximately 0.13 percentage points.
- **Predictor coverage:** Domestic retail fuel and food prices were not tested. Brent crude oil was tested only on an initial train/test split and was not carried into the walk-forward evaluation.

## Disclaimer

This project was developed for educational and analytical purposes. The findings are based on the selected data, assumptions, and evaluation period and should not be interpreted as evidence of causal relationships or as an official inflation forecast.
