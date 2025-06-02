# 🏘️ Zameen.com Property Price Prediction

This repository contains a complete machine learning pipeline to predict property prices using a dataset of Zameen.com, Pakistan's largest real estate platform.

---

## 📌 Objective

To build and compare multiple regression and classification models for predicting house prices (continuous values) and categorizing properties into price classes (Low, Mid, High).

---

## 📦 Dataset

- Source: [Kaggle Zameen.com Dataset (2019)](https://www.kaggle.com/datasets/shahzainzaidi/property-dataset-of-pakistan-2019-zameen-com)
- Total Listings: ~4,100
- Features:
  - Location (city, province)
  - Area (converted to Marla)
  - Property Type, Purpose, Furnishing
  - Date added, Price (target)

---

## 🧹 Preprocessing & Feature Engineering

1. Dropped irrelevant columns: IDs, agents, coordinates, links
2. Removed rows with zero or negative prices
3. Extracted area in Marla and created `Area Category` bins
4. Target Encoding for:
   - `property_type`, `city`, `province`, `purpose`, `area_category`
5. Dropped `area_unit` and `date_added` after transformation
6. Final features scaled where required

---

## ⚙️ Models Used

### 🔢 Regression Models:
- Linear Regression
- Decision Tree Regressor
- K-Nearest Neighbors Regressor
- Random Forest Regressor
- LightGBM Regressor
- Stacking Regressor (meta-model: Linear Regression)

### 🧠 Classification Models:
- Logistic Regression
- Decision Tree Classifier
- K-Nearest Neighbors Classifier
- Naïve Bayes Classifier

---

## 📊 Evaluation Metrics

### Regression:
- R² Score
- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)

### Classification:
- Accuracy
- Precision (Macro)
- Recall (Macro)
- F1 Score (Macro)

---

## ✅ Best Model Results

### Regression:
| Model               | MAE (PKR)  | RMSE (PKR) | R² Score |
|--------------------|------------|------------|----------|
| Stacking Regressor | 5.15M      | 16.26M     | 0.7765   |

### Classification:
| Model               | Accuracy | F1 Score |
|--------------------|----------|----------|
| Decision Tree       | 0.7757   | 0.7753   |

---

## 🔬 Insights

- Stacking ensemble improved regression performance
- Decision Tree was the best classifier on price category bins
- LightGBM and Random Forest performed very closely behind
- Removing duplicate rows significantly boosted results

---

## 🚀 How to Run

1. Clone this repository:
   ```bash
   git clone https://github.com/shoaibahmed4/property_price_predication.git
   cd property_price_predication
