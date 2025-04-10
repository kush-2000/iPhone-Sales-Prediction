# 📈 iPhone Sales Time Series Forecasting (India)

This project performs a time series analysis of quarterly iPhone sales in India from Q2 2007 to Q1 2018. The goal is to model the seasonal trends in sales and forecast future demand using ARIMA and SARIMA techniques. The analysis was conducted as part of an academic assignment in time series modeling.

---

## 📂 Project Overview

- **Objective**: To build a seasonal time series model to capture quarterly iPhone sales patterns and provide accurate future forecasts.
- **Data Source**: [Rafael Pereira - Data.World](https://data.world/rflprr/iphone-sales)
- **Frequency**: Quarterly (4 observations per year)
- **Period**: Q2 2007 – Q1 2018 (44 observations)
- **Final Model**: SARIMA(1,0,0)(1,0,0)[4]
- **Forecast Horizon**: 10 steps ahead (2.5 years)

---

## 🔍 Methodology

### 1. Data Preparation
- The dataset was transformed into a quarterly time series object in R.
- Missing quarters were handled and a continuous ts object was created from 2007 Q2 to 2018 Q1.

### 2. Exploratory Analysis
- Seasonal patterns were observed through time plots, seasonal subseries plots, and ACF/PACF graphs.
- iPhone sales spiked every 4th quarter due to September product launches.

### 3. Model Selection
- Multiple models were considered, including SARIMA with seasonal period 4.
- AIC and BIC were used for model comparison.
- The selected model SARIMA(1,0,0)(1,0,0)[4] provided the best performance and residual diagnostics.

### 4. Model Diagnostics
- Residuals were tested for:
  - Independence (Ljung-Box test)
  - Normality (Shapiro-Wilk test)
  - Homoscedasticity
- The residuals resembled white noise, confirming a good model fit.

### 5. Forecasting
- 10-step-ahead forecasts were generated with 80% and 95% confidence intervals.
- Strong seasonal peaks continued in forecasted values.

---

## 📉 Key Results

### SARIMA Model Output
- ARIMA(1,0,0)(1,0,0)[4] with estimated parameters:
  - Non-seasonal AR(1): 0.8598
  - Seasonal AR(1): 0.7611
  - Intercept: 25.06

### Forecasted Values
| Quarter   | Forecast (Millions) | 95% CI Lower | 95% CI Upper |
|-----------|----------------------|---------------|---------------|
| 2018 Q2   | 33.8                | 23.2          | 44.4          |
| 2018 Q4   | 74.7                | 60.1          | 89.3          |
| 2019 Q4   | 71.4                | 48.0          | 94.8          |
| 2020 Q3   | 53.1                | 14.3          | 91.9          |

---

## 📦 Libraries Used

- `forecast` – time series modeling and forecasting
- `tseries` – stationarity testing and ARIMA fitting
- `astsa` – tools for time series plots and diagnostics
- `ggplot2` – visualization
- `zoo`, `xts` – working with time-indexed data
- `lubridate` – date/time manipulation
- `gridExtra` – arranging plots
- `TSA` – supplementary time series analysis tools

---

## 🧠 Insights

- Quarterly seasonality was critical to model performance.
- Forecasts show robust future demand with periodic peaks.
- The methodology can be generalized to other product lines with seasonal sales patterns.

---

## 👥 Authors

- **Kush Patel**  
- **Ogumoshabe Disan**

**Institution**: Uppsala Universitet  
**Course**: Time Series Modeling  
**Date**: May 2021

---
