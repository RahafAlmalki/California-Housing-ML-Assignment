<h1 align="center">California Housing — Classification & Regression</h1>
<h3 align="center">Machine Learning Course Assignment</h3>

<p align="center">
  <img src="https://img.shields.io/badge/Course-Machine%20Learning-9C27B0?style=flat-square"/>
  <img src="https://img.shields.io/badge/Umm%20Al--Qura%20University-EC407A?style=flat-square"/>
</p>

<p align="center">
  <a href="https://colab.research.google.com/drive/1IJ5jwh_b38cqLnDMqd0JYdzia5UrJMbt?usp=sharing">📓 Open in Colab</a>
</p>

---

## 📌 Overview

This assignment explores the **California Housing dataset** (20,640 records, 8 features) to predict median house values. It covers the full pipeline: exploratory data analysis, feature engineering, a logistic regression classifier, and a polynomial (non-linear) regression model — with a full evaluation and reflection on model performance.

**Target variable:** `MedHouseVal` — median house value in a region
**Features:** `MedInc`, `HouseAge`, `AveRooms`, `AveBedrms`, `Population`, `AveOccup`, `Latitude`, `Longitude`

## 🔍 1. Data Exploration & Preprocessing

- No missing values in the dataset
- Computed mean, median, and standard deviation for all features
- Visualized house age distribution and median house value spread (box plot, outlier detection)
- Explored the relationship between house value and average rooms per household
- Created a binary target (`Expensive` / `Not Expensive`) and normalized numerical features

## 📊 2. Logistic Regression for Classification

Goal: classify whether a house is "Expensive" based on its features.

- Generated degree-2 polynomial features to capture feature interactions
- Applied `SelectKBest` for feature selection and `StandardScaler` for normalization
- 80/20 train-test split

| Metric | Before Scaling/Poly Features | After Scaling/Poly Features |
|---|---|---|
| Accuracy | 79.99% | **84.88%** |
| ROC-AUC | — | **0.93** |

Confusion matrix showed balanced performance across both classes (precision, recall, and F1-score all ~0.85).

## 📈 3. Non-linear (Polynomial) Regression

Goal: predict the continuous `MedHouseVal` using degree-2 polynomial regression.

- **MSE:** 0.46
- **R² Score:** 0.65 (65% of variance explained)

## 🧠 4. Analysis & Reflection

- **Most predictive features:** Latitude, Median Income, and Longitude scored highest via `SelectKBest` — location and income are the strongest predictors of house price.
- **Why polynomial regression outperforms linear regression:** it captures non-linear relationships and feature interactions (e.g., income × location × house age) that a straight-line model misses.
- **Limitations identified:** logistic regression's linearity assumption, overfitting risk with higher-degree polynomial features, and limited interpretability of feature interactions.
- **Proposed improvements:** more advanced models (Random Forest, Gradient Boosting), regularization (Lasso/Ridge), Recursive Feature Elimination, hyperparameter tuning, and cross-validation for more robust results.

## 🛠️ Tools Used

Python · Scikit-learn · Pandas · Matplotlib/Seaborn · Google Colab

## 👥 Team

<div align="left">

[![Rahaf Almalki](https://img.shields.io/badge/Rahaf_Almalki-RahafAlmalki-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/RahafAlmalki)

[![Aliyah Alabdali](https://img.shields.io/badge/Aliyah_Alabdali-AliyahAlabdali-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/AliyahAlabdali)

</div>

---

<p align="center"><i>Machine Learning course Assignment — Computer Science & Artificial Intelligence Department, Umm Al-Qura University</i></p>
