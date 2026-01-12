# 🏠 Tashkent House Prices Prediction Project

## 📌 Project Overview

This repository contains a **machine learning project** to predict the **selling prices of residential apartments in Tashkent, Uzbekistan**. The project uses historical housing data and focuses on building regression models that estimate apartment prices based on features such as district, number of rooms, apartment size, floor level, and total building floors.

The project follows a **structured workflow** and is implemented in a **Jupyter Notebook**, including data preprocessing, model training, evaluation, and testing.

---

## 🏢 Business Understanding

**Client:** Real Estate Analysts / Independent Project  
**Business Task:** Build a system to predict apartment prices in Tashkent districts.  
**Current Approach:** Manual estimation or approximate valuation by real estate agents.  
**Goal:** Provide more accurate and automated price predictions for apartments.  

### ML Problem Definition

* **Learning Type:** Supervised Learning  
* **Problem Type:** Regression  
* **Training Strategy:** Offline batch learning  

### Evaluation Metrics

The models are evaluated using:

* **MAE (Mean Absolute Error)** – average absolute difference between predicted and actual prices  
* **RMSE (Root Mean Squared Error)** – square root of average squared prediction error  

---

## 📁 Repository Structure



---

## 📊 Data Understanding & Preprocessing

### Dataset Overview

- **Number of entries:** 7,565 apartments  
- **Features:**

| Column       | Description |
|-------------|-------------|
| `location`   | Full address of the apartment |
| `district`   | Administrative district in Tashkent |
| `rooms`      | Number of rooms |
| `size`       | Apartment area (sq.m) |
| `level`      | Floor number of the apartment |
| `max_levels` | Total floors in the building |
| `price`      | Selling price (UZS) |

### Preprocessing Steps

1. Remove rows with non-numeric or missing values in `size` and `price`.  
2. Convert `size` to `float` and `price` to `int`.  
3. Encode categorical features:
   - `district` → OneHotEncoder or target encoding  
   - `location` → excluded due to high cardinality  
4. Split data into **train** (80%) and **test** (20%) sets.  

---

## 🤖 Machine Learning Models

### 1. Linear Regression
- Baseline regression model to understand feature relationships.  
- Provides a reference for model performance.  

### 2. Random Forest Regressor
- Ensemble tree-based model capturing non-linear relationships.  
- Tuned hyperparameters:
  - `n_estimators=300`
  - `max_depth=25`
  - `min_samples_leaf=5`  
- More robust to outliers compared to Linear Regression.  

---

## 📈 Model Performance

**Example results on the test set:**

| Model             | MAE (UZS) | RMSE (UZS) |
|------------------|------------|------------|
| Linear Regression | ~67,000    | ~1,367,000 |
| Random Forest     | ~61,000    | ~1,368,000 |

> Note: RMSE is high due to wide price variance and some outliers.

---

## 🚀 Potential Improvements

* Apply Ridge, Lasso, or ElasticNet regression  
* Transform target variable (log scale) to reduce outlier impact  
* Experiment with ensemble models like Gradient Boosting or XGBoost  
* Hyperparameter tuning for Random Forest  
* Deploy model via REST API or web app for real-time predictions  

---

## 🛠 Technologies & Tools

* Python  
* Pandas, NumPy  
* Matplotlib, Seaborn  
* Scikit-learn  
* Jupyter Notebook  

---

## 📄 License

This project is intended for **educational and demonstration purposes**.
