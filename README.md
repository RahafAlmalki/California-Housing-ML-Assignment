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

---

## 🔍 1. Data Exploration & Preprocessing

No missing values were found in the dataset. Mean, median, and standard deviation were computed for every feature, then the numerical features were normalized and a binary target (`Expensive` / `Not Expensive`) was created based on median house price.

<p align="center">
  <img src="assets/House age distribution.png" width="420"/>
  <img src="assets/House value boxplot.png" width="420"/>
</p>

The house age histogram shows most homes fall in the 20–30 year range, with secondary peaks around 15 and 50 years — a non-uniform distribution suggesting real variability in the housing stock. The box plot of median house values shows most prices clustered tightly, with a cluster of high-value outliers above the upper whisker, pointing to a disparity at the top end of the market.

<p align="center">
  <img src="assets/Value vs rooms scatter.png" width="480"/>
</p>

Plotting median house value against average rooms per household shows a general upward trend — more rooms tend to associate with higher value — though with a lot of scatter, meaning room count alone isn't a clean predictor.

---

## 📊 2. Logistic Regression for Classification

Goal: classify whether a house is "Expensive" based on its features.

- Generated degree-2 polynomial features to capture feature interactions
- Applied `SelectKBest` for feature selection and `StandardScaler` for normalization
- 80/20 train-test split

| Metric | Before Scaling/Poly Features | After Scaling/Poly Features |
|---|---|---|
| Accuracy | 79.99% | **84.88%** |
| ROC-AUC | — | **0.93** |

<p align="center">
  <img src="assets/Confusion matrix.png" width="420"/>
  <img src="assets/Roc curve.png" width="420"/>
</p>

The confusion matrix shows balanced performance across both classes — the model isn't skewed toward predicting one class over the other. The ROC curve backs this up with a strong AUC of 0.93, and precision/recall/F1 all land around 0.85 for both classes.

---

## 📈 3. Non-linear (Polynomial) Regression

Goal: predict the continuous `MedHouseVal` using degree-2 polynomial regression.

- **MSE:** 0.46
- **R² Score:** 0.65 (65% of variance explained)

<p align="center">
  <img src="assets/Actual vs predicted.png" width="480"/>
</p>

The predicted line tracks the overall trend of actual values reasonably well, though deviations grow more noticeable at higher price points — suggesting the model captures the general relationship but misses some of the complexity driving the priciest homes.

---

## 🧠 4. Analysis & Reflection

| Feature | Score |
|---|---|
| Latitude | 7,772 |
| Median Income (MedInc) | 7,731 |
| Longitude | 7,214 |
| Average Rooms (AveRooms) | 4,487 |
| Average Bedrooms (AveBedrms) | 1,242 |
| House Age | 411 |

- **Most predictive features:** Latitude, Median Income, and Longitude scored highest via `SelectKBest` — location and income are the strongest predictors of house price.
- **Why polynomial regression outperforms linear regression:** it captures non-linear relationships and feature interactions (e.g., income × location × house age) that a straight-line model misses.
- **Limitations identified:** logistic regression's linearity assumption, overfitting risk with higher-degree polynomial features, and limited interpretability of feature interactions.
- **Proposed improvements:** more advanced models (Random Forest, Gradient Boosting), regularization (Lasso/Ridge), Recursive Feature Elimination, hyperparameter tuning, and cross-validation for more robust results.

---

## 🛠️ Tools Used

<p> <img src="https://img.shields.io/badge/Python-9C27B0?style=flat-square&logo=python&logoColor=white"/> <img src="https://img.shields.io/badge/Scikit--learn-AB47BC?style=flat-square&logo=scikitlearn&logoColor=white"/> <img src="https://img.shields.io/badge/Pandas-BA68C8?style=flat-square&logo=pandas&logoColor=white"/> <img src="https://img.shields.io/badge/Matplotlib-D81B60?style=flat-square&logo=plotly&logoColor=white"/> <img src="https://img.shields.io/badge/Google%20Colab-F06292?style=flat-square&logo=googlecolab&logoColor=white"/> </p>

## 👥 Team

<div align="left">

[![Rahaf Almalki](https://img.shields.io/badge/Rahaf_Almalki-RahafAlmalki-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/RahafAlmalki)
[![Aliyah Alabdali](https://img.shields.io/badge/Aliyah_Alabdali-AliyahAlabdali-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/AliyahAlabdali)

</div>

---

<p align="center"><i>Machine Learning course Assignment — Computer Science & Artificial Intelligence Department, Umm Al-Qura University</i></p>
