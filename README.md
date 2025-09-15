# ⚡ Smart Grid Fault Detection & Efficiency Prediction  

## 📌 Project Overview  
This project focuses on analyzing **Smart Grid operational data** to:  
1. **Detect transformer faults** (classification problem).  
2. **Predict power efficiency** (regression problem).  

By leveraging **EDA, feature engineering, and machine learning models**, the project provides actionable insights for improving grid reliability and operational efficiency.  

---

## 📊 Dataset  
- **Size**: 50,000 records × 16 features  
- **Key Features**:  
  - Voltage (V), Current (A), Power Consumption (kW), Reactive Power (kVAR), Power Factor  
  - Solar Power, Wind Power, Grid Supply  
  - Voltage Fluctuation, Overload Condition, Transformer Fault (binary target)  
  - Environmental factors: Temperature, Humidity  
  - Electricity Price, Predicted Load  
- **Target Variables**:  
  - **Transformer Fault** → Binary classification target  
  - **Power Efficiency (%)** → Derived regression target  

---

## 🔍 Exploratory Data Analysis (EDA)  
- Checked for missing values, duplicates, and ensured correct data types.  
- Conducted **univariate and bivariate analysis** (distribution plots, scatter plots, correlation heatmap).  
- Key insights:  
  - **Faults are rare events (≈3%) → highly imbalanced data**.  
  - **Voltage fluctuations & low power factor** strongly linked to faults.  
  - Higher **renewable power contribution** improves efficiency.  

---

## ⚙️ Methodology  

### 1. Preprocessing  
- Converted timestamp to datetime.  
- Created **Power Efficiency metric**:  
  \[
  \text{Efficiency} = \frac{\text{Power Consumption}}{\text{Grid Supply + Solar Power + Wind Power}} \times 100
  \]  
- Handled **class imbalance** with **SMOTE**.  
- Scaled regression features with **StandardScaler**.  

### 2. Modeling  
- **Classification (Fault Detection)**  
  - Models: Logistic Regression, Decision Tree, Random Forest, Gradient Boosting, AdaBoost, XGBoost, LightGBM, CatBoost.  
  - Evaluation: Accuracy, F1-score, ROC-AUC.  
  - Best: **Random Forest → Accuracy = 91.8% (but recall for faults remained low due to imbalance)**.  

- **Regression (Efficiency Prediction)**  
  - Models: Linear Regression, Decision Tree, Random Forest, Gradient Boosting, AdaBoost, XGBoost, LightGBM, CatBoost.  
  - Evaluation: RMSE, MAE, R².  
  - Best: **CatBoost → R² = 0.999, RMSE = 0.57, MAE = 0.29**.  

---

## 📈 Results  

| Task | Best Model | Metrics |
|------|------------|---------|
| Fault Detection | Random Forest | Accuracy = **91.8%**, ROC-AUC ≈ 0.50 |
| Power Efficiency Prediction | CatBoost | R² = **0.999**, RMSE = 0.57, MAE = 0.29 |

---

## 💡 Key Insights  
- Fault detection is challenging due to **rare event imbalance**; anomaly detection methods may perform better.  
- Power efficiency is highly predictable from input features.  
- **Voltage fluctuations & power factor** are strong fault indicators.  
- Increasing **renewable energy share** significantly improves efficiency.  

---

## 🛠️ Tech Stack  
- **Language**: Python  
- **Libraries**: Pandas, NumPy, Scikit-learn, XGBoost, LightGBM, CatBoost, Matplotlib, Seaborn, imbalanced-learn (SMOTE)  

---

## 🚀 Future Work  
- Apply **time-series feature engineering** (rolling averages, lag features).  
- Explore **anomaly detection techniques** for rare fault detection.  
- Deploy best-performing models as a **real-time monitoring API**.  

---
