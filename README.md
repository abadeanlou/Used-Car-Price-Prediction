# Used Car Price Prediction

This project applies machine learning to predict the selling price of used cars based on a comprehensive set of vehicle features and historical data. The notebook demonstrates a full workflow from data acquisition and cleaning to model training, evaluation, and interpretation.

---

## 🚗 Project Objective

**Goal:**  
Predict the selling price of a used car using its attributes (year, mileage, fuel type, engine specs, accident history, etc.), enabling more accurate and data-driven valuations for buyers, sellers, and automotive platforms.

---

## 📂 Dataset Overview

**Source:** [Kaggle: Used Car Price Prediction Dataset](https://www.kaggle.com/datasets/taeefnajib/used-car-price-prediction-dataset/data)  
**Records:** 4,009 entries

**Features:**

- **Vehicle Details:** Brand, model, model year, mileage, fuel type, engine, transmission  
- **Color:** Exterior and interior color  
- **Condition:** Accident history, clean title status  

**Target:**  
- `Price` (in USD)

**Data Quality:**

- Some missing values in `fuel_type`, `accident`, and `clean_title`
- Outliers filtered (`price > $150,000` or `mileage > 300,000` removed)

---

## 🛠️ Workflow Summary

### 1. Data Preparation

**Cleaning:**

- Removed currency symbols and standardized numerical columns (`price`, `mileage`)
- Filtered out extreme outliers
- Handled missing values:
  - Filled categorical nulls with `'Unknown'`
  - Dropped rows with missing `price`

**Feature Engineering:**

- Created `car_age` from `model_year`
- Extracted `horsepower` and `engine size` from engine descriptions

**Encoding:**

- Categorical variables (`brand`, `model`, `fuel_type`, etc.) encoded numerically

---

### 2. Exploratory Analysis

**Descriptive Statistics:**

- Inspected distribution of `model_year`, `price`, and `mileage`
- Examined feature correlations via heatmap

**Insights:**

- Newer cars and those with lower mileage generally command higher prices
- Accident history and clean title status impact price

---

## 3. Modeling

### Model Selection

Multiple regression algorithms were evaluated:

- Linear Regression  
- Ridge Regression  
- Lasso Regression  
- Random Forest Regressor  
- Gradient Boosting Regressor  
- XGBoost Regressor *(if installed)*  
- LightGBM Regressor *(if installed)*

### Preprocessing

- Feature scaling applied to numerical features  
- Train-test split used for robust evaluation  

### Cross-Validation

- 5-fold cross-validation performed for each model to ensure fair comparison

### Hyperparameter Tuning

- Grid search applied to find optimal parameters for ensemble models

---

## 4. Evaluation

### Metrics

- **R²** (coefficient of determination)  
- **RMSE** (Root Mean Squared Error)  
- **MAE** (Mean Absolute Error)  

### Feature Importance

- Identified which features most strongly influence price predictions

### Error Analysis

- Examined residuals and mispredicted cases to extract further insights

---

## 📊 Key Results

### Cross-Validation Performance

| Model            | R² (CV) | RMSE (CV)    |
|------------------|--------:|-------------:|
| LightGBM         | 0.866   | 9,533.74     |
| XGBoost          | 0.860   | 9,740.78     |
| GradientBoosting | 0.833   | 10,649.21    |
| RandomForest     | 0.827   | 10,836.48    |
| Ridge            | 0.640   | 15,653.04    |
| Lasso            | 0.640   | 15,653.44    |
| LinearRegression | 0.640   | 15,653.45    |

### **Best Model: LightGBM**

- **Test MAE:** 5,253.88  
- **Test RMSE:** 7,892.63  
- **Test R²:** 0.89  

### Top Predictive Features

- Car age  
- Mileage  
- Brand/model  
- Engine size and horsepower  
- Accident history, clean title status  

> Ensemble models (LightGBM, XGBoost, GradientBoosting, RandomForest) substantially outperform linear models by capturing non-linear relationships between features and price.

---

## 🔍 Insights

- Car age and mileage are the strongest predictors of price depreciation.  
- Brand and model significantly affect baseline price.  
- Accident history and clean title status impact resale value.  
- Engine specs (size, horsepower) and transmission type add predictive power.

---

## 🚀 How to Use

### Clone the Repository

```bash
git clone https://github.com/yourusername/used-car-price-prediction.git
cd used-car-price-prediction
