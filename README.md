# Wine Sales Time Series Forecasting

## Project Overview

This project builds an end-to-end time series forecasting pipeline to analyze and predict monthly Australian red wine sales.

The objective is to evaluate multiple statistical forecasting approaches and determine which model best captures long-term trends and recurring seasonal patterns in the data.

The project integrates:

- Time series conversion and indexing  
- Train / validation time-based splitting  
- Linear trend regression modeling  
- Seasonal regression modeling  
- Combined trend + seasonality modeling  
- Simple Exponential Smoothing (SES)  
- Out-of-sample forecast evaluation  

---

## Business Context

Accurate demand forecasting is essential for:

- Inventory planning  
- Production scheduling  
- Supply chain optimization  
- Seasonal promotion strategy  

Monthly wine sales data is used to evaluate how well different statistical models capture underlying trend and seasonality patterns.

**Objective:**

- Identify dominant time series components  
- Compare regression-based and smoothing-based approaches  
- Evaluate forecasting performance on unseen data  

---

## Technical Approach

### 1. Time Series Preparation

- Converted the `Month` column into a proper datetime format  
- Created a time-indexed Pandas Series  
- Visualized the full time series to inspect trend and seasonal structure  

---

### 2. Train / Validation Split

To evaluate true forecasting performance:

- Final 24 months used as validation set  
- Remaining observations used as training data  

This ensures out-of-sample performance assessment rather than in-sample fit.

---

### 3. Model 1 — Linear Trend Model

Regression model using time trend:

red ~ trend

Captures long-term growth patterns but ignores seasonality.

---

### 4. Model 2 — Additive Seasonality Model

Regression model using monthly categorical indicators:

red ~ C(Month)

Captures recurring seasonal effects but does not model trend.

---

### 5. Model 3 — Trend + Seasonality Model

Combined regression model:

red ~ trend + C(Month)

Captures both:

- Long-term growth trend  
- Monthly seasonal patterns  

This model typically improves forecast accuracy when both components are present.

---

### 6. Model 4 — Simple Exponential Smoothing (SES)

Applied smoothing-based forecasting:

- Automatically estimates smoothing parameter (α)  
- Minimizes sum of squared errors (SSE)  
- Places greater weight on recent observations  

SES is useful when trend and seasonality are limited or stable.

---

## Model Evaluation

Models were evaluated using validation-set performance metrics to compare out-of-sample forecasting accuracy.

Comparisons were conducted using:

- Regression summary statistics  
- Forecast error metrics via regressionSummary  

This framework allows objective comparison across multiple modeling approaches.

---

## Key Skills Demonstrated

- Time Series Data Handling  
- Trend Modeling  
- Seasonal Regression Modeling  
- Exponential Smoothing  
- Forecast Validation  
- Out-of-Sample Performance Evaluation  
- Comparative Model Analysis  

---

## Impact & Practical Application

This project demonstrates how different statistical forecasting techniques capture distinct components of time series behavior:

- Linear regression captures long-term growth  
- Seasonal regression captures recurring monthly effects  
- Combined models improve predictive accuracy  
- Smoothing models offer adaptive forecasting alternatives  

The methodology can be extended to:

- Holt’s Linear Trend Method  
- Holt-Winters Seasonal Smoothing  
- ARIMA / SARIMA modeling  
- Automated model selection frameworks  

---

## Tools & Libraries

- Python  
- Pandas  
- NumPy  
- Statsmodels  
- Matplotlib  
- dmba  

---

## Author

Qusai Fattah  
Time Series Analysis | Forecasting | Applied Statistical Modeling
