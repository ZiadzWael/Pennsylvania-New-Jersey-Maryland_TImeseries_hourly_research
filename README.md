# Time Series Forecasting for Electricity Demand Prediction

## 📋 Project Overview
Research project conducted by **Karim Mohamed**, **Sherin Shady**, and **Sama Eldessouky** implementing and comparing five time series forecasting models for electricity demand prediction using hourly PJMW (PJM West) energy consumption data. The study evaluates classical statistical methods against modern machine learning approaches to determine optimal forecasting techniques for energy load prediction.

## 🎯 Key Findings
- **XGBoost** performed best with MAE: 80.26 MW, RMSE: 108.09 MW, R²: 0.9882
- **CNN** showed strong pattern recognition with MAE: 88.10 MW, RMSE: 110.52 MW
- **LSTM** captured long-term dependencies effectively with MAE: 116.66 MW
- **ARIMA** provided reasonable baseline with MAE: 101.61 MW
- **Prophet** offered interpretability but lower accuracy (MAE: 467.71 MW)

## 👥 Research Team

- **Sherin Shady**
- **Sama Eldessouky** 

## 📁 File Structure
├── research_paper.pdf # Complete research paper

├── Arima-model.ipynb # ARIMA implementation

├── CNN-model.ipynb # CNN model implementation

├── LSTM-model.ipynb # LSTM model implementation

├── prophet-model.ipynb # Prophet implementation

├── XGBoost-model.ipynb # XGBoost implementation

├── finalized-preprocessing.ipynb # Data preprocessing pipeline

├── PJMW_hourly.xlsx # Original dataset

├── PJMW_hourly_diff_arima.xlsx # Differenced data for ARIMA

├── PJMW_hourly_preprocessed_*.xlsx # Preprocessed data for each model

## 🔬 Methodology
### Data Preprocessing
- 140,256 hourly observations from PJM West region
- Time-based interpolation for missing values
- Rolling statistics analysis for stationarity detection
- First-order differencing applied (ADF test: p < 0.05)
- Temporal feature extraction (hour, day, month)

### Model Implementation
1. **LSTM**: Two stacked layers (64 units), 30-hour lookback window
2. **CNN**: 1D convolutional layers with max-pooling
3. **ARIMA**: (1,0,0) configuration with residual diagnostics
4. **Prophet**: Additive seasonality with holiday effects
5. **XGBoost**: Feature engineering with lag variables (1,2,24,168h)

### Evaluation Metrics
- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)
- Mean Absolute Percentage Error (MAPE)
- Coefficient of Determination (R²)
- Akaike/Bayesian Information Criteria (AIC/BIC)

## 🚀 Quick Start
1. Install dependencies:
```bash
pip install pandas numpy scikit-learn matplotlib seaborn tensorflow statsmodels prophet xgboost

jupyter notebook finalized-preprocessing.ipynb

jupyter notebook XGBoost-model.ipynb  # Best performing model
