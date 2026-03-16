# 💱 LKR/USD Exchange Rate Forecasting
### A CRISP-DM Machine Learning Approach to Currency Risk Prediction

> Research Paper | BSc in Applied Data Science Communication  
> General Sir John Kotelawala Defence University | Department of Languages

---

## 📌 Overview

This research applies the **CRISP-DM** (Cross Industry Standard Process for Data Mining) methodology to build a high-confidence forecasting system for the **LKR/USD exchange rate** using multiple AI and machine learning models.

The study also explores the broader context of **dollar dominance** — its historical evolution, its impact on developing economies, and specifically how Sri Lanka's economic crises relate to USD dependency.

---

## 📊 Dataset

| Attribute | Detail |
|---|---|
| **Source** | Central Bank of Sri Lanka |
| **Period** | May 7, 2010 – February 9, 2026 |
| **Observations** | 3,346 daily records |
| **Features** | Date, LKR/USD Exchange Rate |
| **Train/Test Split** | 80% training (2011–2023) / 20% testing (2023–2026) |

---

## 🤖 Models Implemented

| Model | MAE | RMSE | MAPE | R² |
|---|---|---|---|---|
| **XGBoost** ⭐ | 2.543 | 3.320 | 0.838% | 0.904 |
| Ensemble | 2.847 | 3.578 | 0.940% | 0.889 |
| Gradient Boosting | 3.313 | 3.898 | 1.085% | 0.868 |
| Random Forest | 3.599 | 4.491 | 1.188% | 0.824 |

> **Best Model:** XGBoost with MAPE of **0.838%** — outperforming the 2% industry benchmark  
> **Recommended for Production:** Ensemble model (40% XGBoost + 30% Random Forest + 30% Gradient Boosting)

---

## ⚙️ Feature Engineering

14 features were engineered from the raw exchange rate data:

- **Moving Averages:** MA_7, MA_30, MA_90
- **Volatility Measures:** Volatility_7, Volatility_30
- **Range Indicator:** Range_30
- **Lag Features:** Lag_1, 2, 3, 5, 7, 14, 30

---

## 📁 Repository Structure

```
├── Dollar_Dominance_Final_Paper.pdf     # Full research paper
├── research_report.txt                  # Model evaluation summary
├── future_forecast_30days.csv           # 30-day forecast output (Feb–Mar 2026)
├── visualizations/
│   ├── 01_raw_data.png                  # Historical LKR/USD data (2010–2026)
│   ├── 02_decomposition.png             # Seasonal decomposition (trend, seasonality, residuals)
│   ├── 03_model_comparison.png          # MAE, RMSE, MAPE, R² comparison
│   ├── 04_predictions_comparison.png    # All models vs actual exchange rates
│   ├── 05_error_analysis.png            # Absolute & percentage error analysis
│   └── 06_deployment_forecast.png       # 30-day forecast with 95% confidence intervals
└── README.md
```

---

## 📈 Key Visualizations

### Historical Exchange Rate (2010–2026)
Three distinct phases are visible:
- **Stable Period (2010–2020):** Gradual depreciation from 110 → 200 LKR/USD (~6.2% annually)
- **Crisis Period (2022):** Sharp spike to 365 LKR/USD — an 80% depreciation within months
- **Recovery Period (2023–2026):** Stabilization around 300–310 LKR/USD post-IMF intervention

### 30-Day Forecast (Feb 10 – Mar 10, 2026)
- Day 1 forecast: **307.16 LKR/USD**
- Stabilizes around **301 LKR/USD** by Day 25–30
- 95% Confidence Interval range: **±4.61 LKR**

---

## 🔬 CRISP-DM Framework Applied

```
1. Business Understanding  →  Currency risk management objectives
2. Data Understanding      →  Time series exploration & ADF stationarity test
3. Data Preparation        →  Feature engineering, data splitting, quality checks
4. Modeling                →  Random Forest, XGBoost, Gradient Boosting, Ensemble
5. Evaluation              →  MAE, RMSE, MAPE, R² across all models
6. Deployment              →  Recursive 30-day forecast with 95% confidence intervals
```

---

## 🛠️ Tech Stack

- **Language:** Python 3.11
- **Libraries:** scikit-learn 1.4.0, XGBoost 2.0.3, pandas 2.1.4, numpy 1.26.3
- **Hardware:** Standard CPU — no GPU required
- **Training Time:** ~3–5 minutes
- **Inference Time:** <100ms for 30-day forecast

---

## 👥 Authors

| Student Number | Name |
|---|---|
| D/ADC/24/0047 | MN Mohamed (Muhammed Nasir) |
| D/ADC/24/0007 | MZM Hussein (Hussein Ziyard) |
| D/ADC/24/0008 | WACI Abeysekara (Chamali Abeysekara) |
| D/ADC/24/0036 | RL Hewanayaka (Rajintha Lakshani) |

---

## 📄 Citation

> MZM Hussein, MN Mohamed, WACI Abeysekara, RL Hewanayaka. *"Predicting USD/LKR Exchange Rate: A CRISP-DM Machine Learning Approach."* General Sir John Kotelawala Defence University, 2026.

---

## 📄 License

This project was developed for academic research purposes at General Sir John Kotelawala Defence University.
