# Thai CPI Inflation Analysis: YoY Drivers and Forecasting

## Project Overview

This project focuses on analyzing Thailand's headline inflation by examining the contributions of month-over-month (MoM) price changes and base effects to year-over-year (YoY) inflation. It also compares Random Forest models with a zero-MoM base-effect baseline to evaluate their forecasting performance using monthly CPI data.

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
- **Data sources:** Bank of Thailand (BOT), Trade Policy and Strategy Office (TPSO), and U.S. Energy Information Administration (EIA).

## Methodology

1. Data Collection and Preprocessing
2. Exploratory Data Analysis of MoM and YoY Inflation
3. Base-Effect Analysis and Decomposition
4. Development of a Zero-MoM Base-Effect Baseline
5. Random Forest Model Development
6. Walk-Forward Forecast Evaluation
7. Model Performance Comparison

## Forecast Evaluation

Forecasting performance was evaluated using Mean Absolute Error (MAE) over a 31-month walk-forward test period.

The zero-MoM base-effect baseline achieved a lower MAE than the last-month YoY benchmark by **0.146 percentage points**.

| Evaluation | Result |
|---|---:|
| Test Period | 31 months |
| MAE Improvement over Last-Month YoY Benchmark | 0.146 percentage points |
| 95% Bootstrap Confidence Interval | 0.068 – 0.233 percentage points |

The results suggest that incorporating known base effects provides a useful benchmark for forecasting headline inflation. Random Forest models did not demonstrate a clear improvement over this baseline during the evaluation period.

## Key Findings

- Base effects play an important role in explaining changes in YoY inflation.
- In 5 of the 8 months with the largest Random Forest forecast errors, the base-effect contribution was larger than the current month's MoM price change.
- The zero-MoM base-effect baseline outperformed the last-month YoY benchmark in terms of MAE.
- Random Forest models did not consistently outperform the simpler baseline, highlighting the importance of comparing complex models against simple benchmarks.

## Dashboard

An interactive Tableau dashboard was developed to present the analysis of Thailand's headline inflation, including monthly price changes, base effects, and forecasting performance.

[View the Tableau Dashboard](YOUR_TABLEAU_PUBLIC_LINK)

**Dashboard Preview**

![Tableau Dashboard Screenshot](images/dashboard-preview.png)

## Limitations

- The walk-forward test period contains only 31 monthly observations, limiting the reliability and generalizability of the evaluation.
- The base-effect framing was selected after examining test-period forecast errors, meaning the test period was not fully independent of the analytical choices.
- Bootstrap confidence intervals do not account for autocorrelation, which may result in overly narrow intervals.
- Policy-rate lags were selected using full-sample correlations, introducing potential look-ahead bias.
- The MoM and base-effect decomposition is an additive approximation, with a maximum residual of approximately 0.13 percentage points.

## Disclaimer

This project was developed for educational and analytical purposes. The findings are based on the selected data, assumptions, and evaluation period and should not be interpreted as evidence of causal relationships or as an official inflation forecast.
