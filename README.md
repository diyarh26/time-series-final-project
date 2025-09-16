# Time Series Final Project — Global Land Temperatures
[📄 View Full Report (PDF)](report.pdf)  
This project explores global climate data through time series analysis.  
Using monthly land temperature records from 1900–2015 and CO₂ trends as an exogenous variable,  
we apply classical models (SARIMA, Fourier regression), modern forecasting tools (Prophet),  
and machine learning methods. The project also includes change-point detection to highlight  
historical structural shifts in climate behavior.

## Dataset
- **Global Land Temperatures** (Kaggle, monthly data 1900–2015)  
- **Exogenous Variable:** CO₂ trend (NOAA Global Monitoring Laboratory)  
- Variables:  
  - Date  
  - Land Average Temperature (°C)  
  - CO₂ trend (ppm)

## Methods
- **SARIMA** — captured seasonal and autoregressive structure, selected via ACF/PACF & BIC.  
- **Prophet** — modeled nonlinear trend and seasonality with flexible components.  
- **Fourier + Trend Regression** — deterministic approach for annual cycles with linear warming.  
- **Machine Learning models** — Random Forest, XGBoost, SVR, Ridge/Lasso regression using Fourier features + CO₂.  
- **Change-Point Detection (CUSUM)** — identified years of structural shifts in climate (e.g., 1932, 1978, 1986, 1993).  

## Key Findings
- Clear long-term **warming trend** and strong **annual seasonality**.  
- **SARIMA(1,1,2)(1,1,2)[12]** achieved the lowest error and most robust forecasts.  
- **Prophet** performed comparably with simpler parameter tuning.  
- **Fourier + Trend** provided interpretability but left autocorrelation in residuals.  
- **Machine Learning models** showed potential; Random Forest performed best, though the CO₂ variable had weak predictive power (correlation ≈ 0.07).  
- Change-point analysis aligned with **real-world climate events**, highlighting meaningful structural changes.  

## Repository Contents
- `report.pdf` — Full academic report  
- `notebook.ipynb` — Code and analysis (Jupyter Notebook)  
- `notebook.html` — HTML export of the notebook  
- `mixed_dataset.csv` — Cleaned dataset (temperature + CO₂)  
- `README.md` — Project overview  

## Requirements
```bash
pandas
numpy
matplotlib
statsmodels
scikit-learn
pmdarima
prophet
hmmlearn
xgboost
