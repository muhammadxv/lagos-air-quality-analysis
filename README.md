# Lagos Air Quality Analysis — PM2.5 Forecasting (2023–2025)

This project analyzes and models **PM2.5 air pollution levels in Lagos, Nigeria**  
using open data from **Sensor.Africa** (November 2023 – April 2025).  
It explores pollution patterns, detects anomalies, and builds **time-series forecasting models (AR & ARIMA)**  
to predict short-term air quality dynamics in one of Africa’s most urbanized cities.

 **For full interactive experience, view the Kaggle notebook:**  
👉 [Lagos Air Quality Analysis on Kaggle](https://www.kaggle.com/code/aminumuhammad/lagos-air-quality-ipynb)

---

## Objectives

- Clean and merge open-source PM2.5 datasets from multiple months.  
- Explore temporal pollution patterns across **daily, weekly, and monthly** timeframes.  
- Detect and remove outliers above threshold (PM2.5 > 500 µg/m³).  
- Evaluate baseline forecasting methods (Naive & Mean).  
- Build, tune, and validate **AR (AutoRegressive)** and **ARIMA** models.  
- Perform **walk-forward validation (WFV)** and **residual diagnostics** for robustness.  
- Visualize model forecasts interactively.

---

## Data Source

Data obtained from **Sensor.Africa** public air quality archives:  
 [https://open.africa/en/dataset/sensorsafrica-airquality-archive-lagos](https://open.africa/en/dataset/sensorsafrica-airquality-archive-lagos)

**Dataset (18 months)** also available on Kaggle:  
 [Lagos PM2.5 Dataset on Kaggle](https://www.kaggle.com/datasets/aminumuhammad/sensors-africa-air-quality-archive-lagos)

---

## Methods & Workflow

1. **Data Cleaning & Preparation**
   - Merged monthly CSVs.
   - Handled missing values via interpolation.
   - Removed extreme outliers (PM2.5 > 500).
   - Resampled to daily means.

2. **Exploratory Data Analysis (EDA)**
   - Time series plots (daily, weekly, monthly).
   - ACF & PACF to study lag correlations.
   - Outlier and exceedance visualization.

3. **Baseline Models**
   - Naive forecast (last observed value).
   - Mean forecast (historical mean).  
   - Evaluated with **MAE** and **RMSE**.

4. **Feature Engineering**
   - Created daily averages and rolling windows.
   - Conducted stationarity testing (ADF test).

5. **AR Model**
   - Built with lag = 24 based on ACF insights.
   - Evaluated residuals (white noise check).
   - Performed walk-forward validation (WFV).

6. **ARIMA Model**
   - Grid search over (p ∈ [0–5], d=1, q ∈ [0–5]).
   - Selected best model via MAE minimization.
   - Visualized results with heatmap.
   - Conducted residual diagnostics and forecast visualization.

---

## Results Summary

| Model | MAE | RMSE | Key Insights |
|-------|------|------|--------------|
| Naive Forecast | ~16.1 | ~18.4 | Weak predictive power |
| Mean Forecast | ~9.8 | ~13.2 | Stable baseline |
| AR Model (lag=24) | ↓ (Improved) | ↓ | Captured short-term dependencies |
| **ARIMA (3,1,0)** | **Best (MAE ≈ 4.9)** | **Lowest RMSE** | Strong predictive performance, well-behaved residuals |

### Diagnostic Insights
- **Residuals** approximately normal and uncorrelated.
- **ACF/PACF of residuals** show no remaining signal.
- **Q-Q plots** confirm model adequacy.
- **Forecasts** closely track observed PM2.5 during the test period.

---

## Visual Results Gallery

| Visualization | Description | Link |
|----------------|--------------|------|
| ACF Plots | Autocorrelation structure | [View](__results__files/__results___35_1.png) |
| PACF Plots | Autocorrelation structure | [View](__results__files/__results___36_1.png) |
| AR Model Forecast | Baseline autoregressive fit | [View](models_visuals/AR WFV.png) |
| ARIMA Grid Search | MAE heatmap across p–q | [View](__results__files/__results___66_0.png) |
| Residual Diagnostics | Residual normality & independence | [View](__results__files/__results___73_1.png) |
| ARIMA Forecast | Final model vs actual PM2.5 | [View](models_visuals/ARIMA WFV.png) |

*(Click links above to view full images on GitHub)*

---

## 🗂️ Folder Structure

