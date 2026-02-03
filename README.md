# Road_Accident_Predictions
"Road_accient_model that can predict the accient"
# 🚧 Accident Risk Prediction using Machine Learning

![Python](https://img.shields.io/badge/Python-3.x-blue.svg)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-ML-orange.svg)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen.svg)

---

## 📌 Project Overview

This project builds an **end-to-end Machine Learning pipeline** to predict **Accident Risk** based on road, traffic, weather, and time-related factors.

The workflow follows **industry best practices**, including:
- Exploratory Data Analysis (EDA)
- Feature engineering & encoding
- Single reusable ML pipeline
- Model training & saving
- Prediction on unseen test data

---

## 📊 Dataset Description

The dataset contains **517,754 records** with the following columns:

### 🔢 Numerical Features
- `num_lanes`
- `curvature`
- `speed_limit`
- `num_reported_accidents`
- `accident_risk` 🎯 *(Target variable)*

### 🧾 Categorical Features
- `road_type`
- `lighting`
- `weather`
- `time_of_day`

### ✅ Boolean Features
- `road_signs_present`
- `public_road`
- `holiday`
- `school_season`

---

## 🔍 Exploratory Data Analysis (EDA)

EDA was performed after:
- ✅ Null value check
- ✅ Duplicate value removal

### 📈 Visual Analysis Included
- Histograms & boxplots for numerical features
- Scatter plots:
  - `speed_limit` vs `accident_risk`
  - `curvature` vs `accident_risk`
  - `num_lanes` vs `accident_risk`
  - `num_reported_accidents` vs `accident_risk`
- Bar charts for categorical & boolean features
- Correlation heatmap for numerical columns

---

## ⚙️ Feature Engineering & Encoding

### 🔁 Encoding Strategy
- **OneHotEncoder** for categorical variables
- Boolean columns retained as `0 / 1`
- Numerical columns passed directly

⚠️ `handle_unknown='ignore'` is used to safely handle unseen categories during prediction.

---

## 🧠 Machine Learning Pipeline

A **single end-to-end pipeline** is created using:

- `ColumnTransformer`
- `OneHotEncoder`
- `RandomForestRegressor`
- `Pipeline`

This ensures:
- No data leakage
- Same preprocessing for train & test data
- Easy deployment and reuse

---

## 🏋️ Model Training

- Model trained using the **training dataset**
- Target variable: `accident_risk`
- Column `id` excluded from training

---

## 💾 Model Saving & Loading

The complete pipeline (preprocessing + model) is saved using `joblib`.

### Save model
```python
joblib.dump(pipeline, 'accident_risk_model.pkl')
