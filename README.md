# 🛒 Grocery Demand Forecasting Using Machine Learning

![Python](https://img.shields.io/badge/Python-3.x-blue)
![Machine Learning](https://img.shields.io/badge/Machine%20Learning-Time%20Series-orange)
![XGBoost](https://img.shields.io/badge/Model-XGBoost-green)
![Prophet](https://img.shields.io/badge/Model-Prophet-purple)
![ARIMA](https://img.shields.io/badge/Model-ARIMA-red)
![Google Colab](https://img.shields.io/badge/Platform-Google%20Colab-yellow)

## 📌 Project Overview

This project presents an end-to-end **Grocery Demand Forecasting** workflow using Python, Machine Learning, and Time Series Forecasting techniques.

Accurate demand forecasting can help retail and grocery businesses improve inventory planning, reduce stockouts and overstocking, optimize promotional strategies, and support better supply-chain decisions.

Using historical grocery sales data from Kaggle, this project explores sales trends, seasonality, promotional effects, and historical demand patterns before developing and comparing three forecasting approaches:

- 📈 **ARIMA**
- 🔮 **Prophet**
- 🚀 **XGBoost**

Based on the final evaluation results, **XGBoost achieved the best forecasting performance** among the three evaluated models.

---

## 🎯 Project Objectives

The key objectives of this project are:

- Analyze historical grocery sales data.
- Identify sales trends and temporal patterns.
- Explore the relationship between promotions and grocery demand.
- Perform exploratory data analysis and time-series analysis.
- Prepare historical sales data for forecasting.
- Build ARIMA, Prophet, and XGBoost forecasting models.
- Apply time-based feature engineering for machine learning.
- Evaluate models using RMSE, MAE, and MAPE.
- Compare forecasting performance and identify the best-performing approach.

---

## 📊 Dataset

This project uses data from Kaggle's **Store Sales – Time Series Forecasting** dataset/competition.

### Main Files Used

- `train.csv`
- `holidays_events.csv`

### Training Dataset Overview

- **Records:** Approximately 3,000,888
- **Date Range:** 2013-01-01 to 2017-08-15
- **Focused Forecasting Analysis:** Store 1 – `GROCERY I`

### Main Features

| Feature | Description |
|---|---|
| `id` | Unique identifier for each observation |
| `date` | Date of the sales record |
| `store_nbr` | Store identification number |
| `family` | Product family/category |
| `sales` | Sales for the corresponding product family |
| `onpromotion` | Number of products under promotion |

`holidays_events.csv` is used to support analysis of holiday-related patterns.

> **Note:** The datasets are not stored directly in this repository. They can be downloaded from the original Kaggle **Store Sales – Time Series Forecasting** source.

---

## 🛠️ Technologies & Libraries

### Programming & Environment

- Python
- Google Colab
- Jupyter Notebook

### Data Analysis & Visualization

- Pandas
- NumPy
- Matplotlib
- Seaborn

### Machine Learning & Time Series

- Scikit-learn
- Statsmodels
- ARIMA
- Prophet
- XGBoost

---

## 🔄 Project Workflow

### 1️⃣ Data Loading & Validation

- Loaded the historical grocery sales dataset.
- Verified dataset dimensions and date range.
- Examined columns, data types, and overall structure.

### 2️⃣ Data Cleaning & Preprocessing

- Checked missing values and duplicate records.
- Converted date information into datetime format.
- Sorted observations chronologically.
- Prepared a continuous daily time series for forecasting.

### 3️⃣ Exploratory Data Analysis

EDA was performed to explore:

- 📈 Sales trends over time
- 📅 Temporal sales patterns
- 🏷️ Promotion-related behavior
- 🎉 Holiday-related patterns
- 🔄 Rolling trends and variations in demand

### 4️⃣ Time Series Analysis

Time-series techniques were used to examine historical demand behavior.

Seasonal decomposition was used to analyze:

- Observed values
- Trend
- Seasonality
- Residual components

### 5️⃣ Chronological Train-Test Split

Because this is a time-series forecasting problem, the data was divided **chronologically rather than randomly**.

Historical observations were used for training, while later observations were reserved for model evaluation.

### 6️⃣ Forecasting

Three forecasting approaches were implemented:

- ARIMA
- Prophet
- XGBoost

### 7️⃣ Model Evaluation

Forecasting performance was evaluated using:

- **RMSE — Root Mean Squared Error**
- **MAE — Mean Absolute Error**
- **MAPE — Mean Absolute Percentage Error**

Lower error values indicate better forecasting performance.

---

# 🤖 Forecasting Models

## 📈 1. ARIMA

ARIMA (**AutoRegressive Integrated Moving Average**) was implemented as a classical statistical time-series forecasting approach.

### Performance

- **RMSE:** 790.35
- **MAE:** 547.96
- **MAPE:** 32.53%

ARIMA served as a useful statistical baseline for comparison with the other forecasting approaches.

---

## 🔮 2. Prophet

Prophet was applied to model time-dependent patterns in grocery sales.

The model also incorporates `onpromotion` as an external regressor.

### Performance

- **RMSE:** 584.51
- **MAE:** 440.30
- **MAPE:** 18.72%

Prophet achieved lower forecasting errors than ARIMA in this evaluation.

> **Modeling Assumption:** Promotion information for the test period is treated as known in advance during evaluation. In a real forecasting scenario, these values would need to come from planned promotional schedules.

---

## 🚀 3. XGBoost

XGBoost was implemented as a machine learning forecasting approach using engineered time-series features.

### Feature Engineering

Features included:

- Day
- Month
- Day of week
- Year
- Lag-1 sales
- Lag-7 sales
- 7-day rolling mean

Lag and rolling features were constructed from historical observations to help capture recent demand behavior while avoiding direct target leakage.

### Performance

- **RMSE:** ⭐ 510.48
- **MAE:** ⭐ 349.52
- **MAPE:** ⭐ 15.13%

XGBoost achieved the **lowest forecasting errors among the three evaluated models**.

---

# 📊 Model Performance Comparison

| Model | RMSE | MAE | MAPE |
|---|---:|---:|---:|
| ARIMA | 790.35 | 547.96 | 32.53% |
| Prophet | 584.51 | 440.30 | 18.72% |
| **XGBoost** | **510.48** | **349.52** | **15.13%** |

## 🏆 Best Performing Model — XGBoost

XGBoost achieved the lowest:

- RMSE
- MAE
- MAPE

The results indicate that, for this forecasting setup, combining historical time-series information with engineered features and gradient boosting produced the strongest predictive performance among the evaluated approaches.

---

## 💡 Key Insights

- Grocery demand demonstrates temporal variation and changing patterns over time.
- Promotional information can provide useful context for understanding changes in sales behavior.
- Lag-based and rolling-window features help machine learning models capture recent historical demand patterns.
- ARIMA provides a useful classical forecasting baseline.
- Prophet improved upon the ARIMA results in this evaluation.
- **XGBoost achieved the strongest overall forecasting performance based on the evaluated error metrics.**

---

## 🏪 Business Applications

Grocery demand forecasting can support:

- 📦 Inventory planning
- 🛒 Stock replenishment
- 📉 Reduction of stockouts
- 📊 Reduction of excess inventory
- 🏷️ Promotion planning
- 🚚 Supply-chain planning
- 💰 Cost optimization
- 📈 Data-driven decision-making

Accurate demand estimates can help retailers better align inventory and operational decisions with expected customer demand.

---

## 📁 Repository Structure

```text
Grocery-Demand-Forecasting/
│
├── Grocery_Demand_Forecasting_Machine_Learning.ipynb
├── README.md
├── requirements.txt
└── .gitignore
```

### Dataset Files Required Separately

```text
train.csv
holidays_events.csv
```

These files should be downloaded from the original Kaggle dataset before running the complete notebook.

---

## ⚙️ How to Run the Project

### Step 1 — Download the Dataset

Download the **Store Sales – Time Series Forecasting** dataset from Kaggle.

The notebook requires:

- `train.csv`
- `holidays_events.csv`

### Step 2 — Download the Repository

Download or clone this GitHub repository to your system.

### Step 3 — Open the Notebook

Open:

`Grocery_Demand_Forecasting_Machine_Learning.ipynb`

using **Google Colab** or a compatible Jupyter Notebook environment.

### Step 4 — Add the Dataset Files

Upload the following files to the notebook environment:

- `train.csv`
- `holidays_events.csv`

### Step 5 — Install Dependencies

Install the required Python libraries using:

```bash
pip install -r requirements.txt
```

### Step 6 — Run the Notebook

Run the notebook cells sequentially from top to bottom.

---

## ⚠️ Modeling Notes

- The dataset used in this project is a **publicly available Kaggle grocery sales dataset** and does not represent proprietary Amazon sales data.
- A small number of missing calendar dates introduced during time-series reindexing were assigned zero sales as a modeling assumption to maintain a continuous daily series.
- These imputed values should not be interpreted as confirmed zero-sales observations.
- Prophet evaluation assumes that promotional schedules for the test period are known in advance.
- A chronological train-test split was used to maintain the temporal order of the data.

---

## 🔮 Future Improvements

Potential extensions to this project include:

- Hyperparameter tuning for XGBoost
- Time-series cross-validation
- Additional lag and rolling-window features
- Forecasting across multiple stores and product families
- Incorporating additional external variables
- Comparing additional forecasting algorithms
- Developing an interactive forecasting dashboard
- Deploying the final forecasting model as an application or API

---

## 📚 Skills Demonstrated

- Python Programming
- Data Cleaning & Preprocessing
- Exploratory Data Analysis (EDA)
- Data Visualization
- Time Series Analysis
- Seasonal Decomposition
- Feature Engineering
- Machine Learning
- ARIMA Forecasting
- Prophet Forecasting
- XGBoost
- Model Evaluation
- Demand Forecasting

---

### ⭐ If you found this project useful, feel free to explore the notebook and repository.
