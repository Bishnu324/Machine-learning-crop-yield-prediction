# 🌾 Crop Yield Prediction Using Environmental & Pesticide Data

![Python](https://img.shields.io/badge/Python-Data%20Science-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Processing-150458?style=for-the-badge&logo=pandas)
![NumPy](https://img.shields.io/badge/NumPy-Numerical%20Computing-013243?style=for-the-badge&logo=numpy)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-11557c?style=for-the-badge&logo=plotly)
![Scikit-learn](https://img.shields.io/badge/Scikit--Learn-ML%20Models-F7931E?style=for-the-badge&logo=scikitlearn)
![Kaggle](https://img.shields.io/badge/Kaggle-Dataset-20BEFF?style=for-the-badge&logo=kaggle)

---

## 🧠 Project Overview

This project focuses on **predicting crop yield** using multiple environmental and agricultural factors such as **rainfall, temperature, and pesticide usage**.  
The dataset, sourced from **Kaggle**, combines global agricultural statistics from various countries over multiple years.

The analysis includes:
- Data loading, cleaning, and preprocessing  
- Exploratory Data Analysis (EDA)  
- Feature engineering and merging multiple datasets  
- Machine learning model building and evaluation  

The goal is to develop an accurate predictive model for understanding how environmental variables influence crop yield.

---

## 📊 Key Steps Performed

### 1️⃣ Data Loading & Exploration
Loaded four datasets:
- `yield.csv` → Crop yield by country, year, and crop type  
- `rainfall.csv` → Annual rainfall (mm/year)  
- `temp.csv` → Average annual temperature  
- `pesticides.csv` → Pesticide usage per country/year  

---

### 2️⃣ Data Cleaning & Preprocessing
- Removed duplicates & renamed columns for consistency  
- Converted non-numeric strings to numeric format using a custom logic  
- Filled missing values using:
  - **Rainfall:** Mean  
  - **Temperature:** Mean  
  - **Pesticides:** Zero (0)  

**Temperature dataset:**  
Sorted by `Country` & `Year`, filled missing values using `.ffill()` and `.bfill()` within each country group.

---



### 4️⃣ Data Quality Checks
- Verified there were **no missing or duplicate values**  
- Ensured all columns had correct numeric data types  
- Conducted descriptive statistical summaries  

---

## 🧭 Exploratory Data Insights (Visualization Summary)

A detailed **Exploratory Data Analysis (EDA)** was performed using **Matplotlib** and **Seaborn** to identify relationships between features and yield performance.

### 🔹 Key Visualizations
- **Country Distribution:** Count of data entries per country  
- **Crop Type Frequency:** Countplot showing most represented crops  
- **Rainfall vs Yield:** Scatter plot showing correlation between rainfall and yield  
- **Temperature vs Yield:** Line plot showing temperature influence on productivity  
- **Pesticide Trends:** Yearly bar plot of pesticide usage by country  
- **Correlation Heatmap:** Relationship between rainfall, temperature, pesticide use, and yield  
- **Yearly Trends:** Multi-line plot tracking rainfall, temperature, and yield variation over time  

### 🔹 Key Findings
- 📈 **Moderate rainfall and stable temperatures** positively affect crop yield  
- 🌦️ **Extreme weather fluctuations** reduce yield significantly  
- 🧪 **Controlled pesticide use** leads to higher yield, but excessive use shows diminishing returns  
- 🌍 **Certain countries** show consistent yield growth due to better environmental and agricultural conditions  

> ### Exploratory Data Analysis (EDA)

1. **Yield vs Rainfall**  
![Yield vs Rainfall](assets/yield_vs_rainfall.png)

2. **Temperature Trend**  
![Temperature Trend]("https://github.com/Bishnu324/Machine-learning-crop-yield-prediction/blob/main/temperature_trend.jpg")

3. **Correlation Heatmap**  
![Correlation Heatmap]("https://github.com/Bishnu324/Machine-learning-crop-yield-prediction/blob/main/correlation_heatmap.jpg")

---

## ⚙️ Feature Encoding & Scaling
- Encoded categorical features (`Area`, `Item`)  
- Applied scaling to numeric features for uniformity  

---

## 🤖 Model Training & Evaluation

Trained multiple regression models for yield prediction:

| Model | MSE | R² Score |
|--------|-------------|------------|
| Linear Regression | 1.41e9 | 0.707 |
| Ridge Regression | 1.40e9 | 0.707 |
| Lasso Regression | 1.40e9 | 0.707 |
| KNeighbors Regressor | 1.54e8 | 0.967 |
| Decision Tree Regressor | **1.38e8** | **0.971** |

🏆 **Best Model:** `DecisionTreeRegressor`  
- Achieved highest accuracy and the lowest MSE  
- Handles categorical data efficiently without explicit encoding  
- Robust to outliers and non-linear relationships  

---

## 🔍 Key Insights

- **Temperature and rainfall** are dominant predictors of yield variation.  
- **Decision Tree Regressor** performs best with minimal preprocessing.  
- **Rainfall & pesticide use** together show strong correlation with yield.  
- The dataset provides a solid foundation for future predictive agriculture modeling.

---

## 💡 Recommendations

- Integrate **soil quality**, **farming practices**, and **economic indicators** for improved model accuracy.  
- Use **satellite and remote sensing data** for higher spatial precision.  
- Apply **time-series forecasting (ARIMA, LSTM)** for future yield trends.  
- Develop a **Power BI or Streamlit dashboard** for interactive visualization in future iterations.  

---

## 🧰 Tools & Technologies

| Tool | Purpose |
|------|----------|
| **Python (Pandas, NumPy)** | Data Cleaning & Transformation |
| **Matplotlib / Seaborn** | Visualization & EDA |
| **Scikit-learn** | Model Building & Evaluation |
| **Jupyter Notebook** | Analysis Environment |
| **Kaggle Dataset** | Data Source |

---


