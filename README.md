# Used Car Price Prediction

This project applies machine learning to predict the selling price of used cars based on a comprehensive set of vehicle features and historical data. The notebook demonstrates a full workflow from data acquisition and cleaning to model training, evaluation, and interpretation.

---

## 🚗 Project Objective

**Goal:**  
Predict the selling price of a used car using its attributes (year, mileage, fuel type, engine specs, accident history, etc.), enabling more accurate and data-driven valuations for buyers, sellers, and automotive platforms.

---

## 📂 Dataset Overview

**Source:** [Kaggle: Used Car Price Prediction Dataset]([https://www.kaggle.com/datasets/ziya07/smart-mobility-traffic-dataset](https://www.kaggle.com/datasets/taeefnajib/used-car-price-prediction-dataset/data))  
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

### 3. Modeling

**Model Selection:**

- Regression algorithms (e.g., Linear Regression, Random Forest Regressor)

**Preprocessing:**

- Feature scaling applied to numerical features
- Train-test split for robust evaluation

**Hyperparameter Tuning:**

- Grid search for optimal Random Forest parameters

---

### 4. Evaluation

**Metrics:**

- RMSE (Root Mean Squared Error)
- MAE (Mean Absolute Error)
- R² score

**Feature Importance:**

- Identified which features most strongly influence price predictions

**Error Analysis:**

- Examined residuals and mispredicted cases for further insights

---

## 📊 Key Results

| Model             | Test RMSE     | Test MAE      | R² Score      |
|------------------|----------------|---------------|---------------|
| Random Forest     | [Insert value] | [Insert value] | [Insert value] |
| Linear Regression | [Insert value] | [Insert value] | [Insert value] |

**Top Predictive Features:**

- Car age  
- Mileage  
- Brand/model  
- Engine size and horsepower  
- Accident history, clean title status  

**Summary:**  
Random Forest provided the most accurate predictions, capturing non-linear relationships between features and price.

---

## 🔍 Insights

- Car age and mileage are the strongest predictors of price depreciation.
- Brand and model significantly affect baseline price.
- Accident history and clean title status impact resale value.
- Engine specs (size, horsepower) and transmission type add predictive power.

---

## 🚀 How to Use

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/used-car-price-prediction.git
cd used-car-price-prediction
