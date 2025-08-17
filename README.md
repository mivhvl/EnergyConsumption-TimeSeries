# **Time Series and Forecasting - Final Project**

## 👥 **Authors & Institution**

- Author(s): Matheus Hirakawa Bissacots, Michal Dawid Kowalski, Bernardo Gil Alves Salgado
- Course: Time Series and Forecasting
- Institution: FCUP – Faculdade de Ciencias da Universidade do Porto
- Date: January 2025

---

## 1. Dataset
**Source:** [Hourly Energy Consumption (Kaggle)](https://www.kaggle.com/datasets/robikscube/hourly-energy-consumption/data)  
**Description:** Over 10 years of hourly energy consumption (MW) from PJM Interconnection LLC, a US regional transmission operator.  
**Focus:** Consumption data for **American Electric Power (AEP)**.  

---

## 2. Data Analysis
- **Daily:** Clear diurnal pattern, lowest at night, peak in the evening.  
- **Weekly:** Slightly lower consumption on weekends.  
- **Seasonal:** Peaks in **winter** (heating) and **summer** (cooling).  
- **Stationarity:** ADF test confirmed non-stationarity → differencing required.  
- **Seasonal Decomposition:** Clear yearly seasonality → monthly aggregation used for modeling.  

---

## 3. Data Split
- **Train:** Before 2016  
- **Test:** From 2016 onward  

---

## 4. Modeling
### SARIMA (Seasonal ARIMA)
- **Non-seasonal params:** p=1, d=1, q=1  
- **Seasonal params:** P=1, D=1, Q=1, s=12  

### Evaluation
- **Residuals:** Approximated white noise  
- **Ljung-Box Test:** No significant autocorrelation  
- **Cross-validation (TimeSeriesSplit):**  
- **Mean RMSE:** ~1080 MW  

---

## 5. Conclusions
- SARIMA (1,1,1)(1,1,1,12) effectively captured overall seasonal and trend patterns.  
- Residual analysis and tests confirmed reasonable model fit.  
- Some anomalies (e.g., early 2006, lag 12 spike) remain for future investigation.  
