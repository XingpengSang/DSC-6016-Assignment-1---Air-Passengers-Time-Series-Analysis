# DSC 6016 Assignment 1
## Air Passengers Time Series Analysis

This project analyzes the monthly air passenger time series from 1949 to 1960 as part of **DSC 6016 – Predictive Analytics and Financial Applications**.

## Assignment Objectives

The analysis focuses on:

- Exploratory Data Analysis (EDA)
- Deterministic trend modeling
- Seasonality detection
- Seasonality modeling
- Residual diagnostics
- Model comparison

## Dataset

The dataset contains monthly air passenger observations from **1949 to 1960**, with 144 monthly observations.


| Variable | Description |
|---|---|
| `Month` | Observation month |
| `Passengers` | Number of air passengers |

The dataset was obtained from Kaggle.

## Methodology

The analysis follows these main steps:

1. **Exploratory Data Analysis**
   - Time series plot
   - Histogram
   - Summary statistics

2. **Deterministic Trend Modeling**
   - Linear time trend
   - Ordinary Least Squares (OLS) regression

3. **Seasonality Analysis**
   - Seasonal plot
   - Average passenger count by month
   - Detrended autocorrelation analysis
   - Seasonal lags of 12, 24, and 36 months

4. **Seasonality Modeling**
   - Monthly seasonal dummy variables
   - Trend + seasonality regression model

5. **Residual Diagnostics**
   - Residual time series
   - Residual distribution
   - Residual ACF
   - Ljung–Box test
   - MAE and RMSE

6. **Alternative Log-Scale Model**
   - Log transformation of passenger counts
   - Trend + seasonality regression on the log scale
   - Back-transformation to the original passenger scale

## Main Results

The analysis identifies:

- A clear long-term upward deterministic trend
- A recurring annual seasonal pattern
- Significant temporal dependence remaining in the residuals after deterministic regression

### Trend + Seasonality Model

- R-squared: **0.9559**
- Adjusted R-squared: **0.9518**
- MAE: **19.7736 passengers**
- RMSE: **25.1136 passengers**

### Log Trend + Seasonality Model

After back-transformation to the original passenger scale:

- R-squared (log scale): **0.9835**
- Adjusted R-squared (log scale): **0.9820**
- MAE: **12.8920 passengers**
- RMSE: **16.7280 passengers**

The log-scale model reduces the original-scale MAE and RMSE compared with the original-scale trend + seasonality model. Seasonal-lag residual autocorrelation is also reduced, although some short-term temporal dependence remains.

## Project Structure

```text
DSC6016-Assignment1/
│
├── data/
│   └── AirPassengers.csv
│
├── figures/
│   ├── time_series.png
│   ├── histogram.png
│   ├── trend_model.png
│   ├── seasonal_plot.png
│   ├── monthly_seasonal_pattern.png
│   ├── acf_detrended.png
│   ├── residual_time_series.png
│   ├── residual_histogram.png
│   ├── residual_acf.png
│   ├── log_time_series.png
│   ├── log_trend_seasonality_model.png
│   ├── log_residual_acf.png
│   └── model_comparison.png
│
├── analysis.ipynb
├── requirements.txt
├── README.md
└── .gitignore

## Environment

- Python 3.14.7
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn
- statsmodels
- Jupyter Notebook

## How to Run

Clone this repository and open the project in VS Code.

Install the required packages:

```bash
pip install -r requirements.txt

Then open analysis.ipynb and run the notebook from beginning to end.

