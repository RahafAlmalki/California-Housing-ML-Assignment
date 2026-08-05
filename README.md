<h1 align="center">California Housing: Classification & Regression</h1>
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

This assignment explores the **California Housing dataset** (20,640 records, 8 features) to predict median house values. It covers the full pipeline: exploratory data analysis, feature engineering, a logistic regression classifier, and a polynomial (non-linear) regression model, followed by a full evaluation and reflection on model performance.

**Target variable:** `MedHouseVal` (median house value in a region)  
**Features:** `MedInc`, `HouseAge`, `AveRooms`, `AveBedrms`, `Population`, `AveOccup`, `Latitude`, `Longitude`

---

## 🔍 1. Data Exploration & Preprocessing

No missing values were found in the dataset. Mean, median, and standard deviation were computed for every feature. The numerical features were then normalized, and a binary target (`Expensive` / `Not Expensive`) was created based on the median house price.

<p align="center">
  <img src="assets/House age distribution.png" width="465"/>
  <img src="assets/House value boxplot.png" width="420"/>
</p>

The house age histogram shows most homes fall in the 20-30 year range, with secondary peaks around 15 and 50 years. This non-uniform distribution suggests real variability in the housing stock. The box plot of median house values shows most prices clustered tightly, with a group of high-value outliers above the upper whisker. This points to a disparity at the top end of the market.

<p align="center">
  <img src="assets/Value vs rooms scatter.png" width="480"/>
</p>

Plotting median house value against average rooms per household shows a general upward trend. More rooms tend to be associated with higher values, although the large amount of scatter indicates that room count alone is not a strong predictor.

---

## 📊 2. Logistic Regression for Classification

Goal: classify whether a house is **Expensive** based on its features.

- Generated degree-2 polynomial features to capture feature interactions
- Applied `SelectKBest` for feature selection and `StandardScaler` for normalization
- 80/20 train-test split

| Metric | Before Scaling/Poly Features | After Scaling/Poly Features |
|---|---|---|
| Accuracy | 79.99% | **84.88%** |
| ROC-AUC | N/A | **0.93** |

<p align="center">
  <img src="assets/Confusion matrix.png" width="420"/>
  <img src="assets/Roc curve.png" width="435"/>
</p>

The confusion matrix shows balanced performance across both classes. The model is not skewed toward predicting one class over the other. The ROC curve supports this result with an AUC of 0.93, while precision, recall, and F1-score are all close to 0.85 for both classes.

---

## 📈 3. Non-linear (Polynomial) Regression

Goal: predict the continuous `MedHouseVal` using degree-2 polynomial regression.

- **MSE:** 0.46
- **R² Score:** 0.65 (65% of the variance explained)

<p align="center">
  <img src="assets/Actual vs predicted.png" width="480"/>
</p>

The predicted values follow the overall trend of the actual values reasonably well. However, deviations become more noticeable at higher price points, suggesting that the model captures the general relationship but misses some of the complexity behind the most expensive homes.

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

- **Most predictive features:** Latitude, Median Income, and Longitude scored highest using `SelectKBest`. This indicates that location and income are the strongest predictors of house price.
- **Why polynomial regression outperforms linear regression:** It captures non-linear relationships and feature interactions, such as income, location, and house age, that a simple linear model cannot represent.
- **Limitations identified:** Logistic regression assumes linear decision boundaries, polynomial features may increase the risk of overfitting, and feature interactions become harder to interpret.
- **Proposed improvements:** Random Forest, Gradient Boosting, regularization (Lasso/Ridge), Recursive Feature Elimination, hyperparameter tuning, and cross-validation.

---

## 🛠️ Tools Used

<p>
  <img src="https://img.shields.io/badge/Python-9C27B0?style=flat-square&logo=python&logoColor=white"/>
  <img src="https://img.shields.io/badge/Scikit--learn-AB47BC?style=flat-square&logo=scikitlearn&logoColor=white"/>
  <img src="https://img.shields.io/badge/Pandas-BA68C8?style=flat-square&logo=pandas&logoColor=white"/>
  <img src="https://img.shields.io/badge/Matplotlib-D81B60?style=flat-square&logo=plotly&logoColor=white"/>
  <img src="https://img.shields.io/badge/Google%20Colab-F06292?style=flat-square&logo=googlecolab&logoColor=white"/>
</p>

## 👥 Team

<div align="left">

[![Rahaf Almalki](https://img.shields.io/badge/Rahaf_Almalki-RahafAlmalki-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/RahafAlmalki)
[![Aliyah Alabdali](https://img.shields.io/badge/Aliyah_Alabdali-AliyahAlabdali-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/AliyahAlabdali)

</div>

---

<p align="center"><i>Machine Learning Course Assignment, Computer Science & Artificial Intelligence Department, Umm Al-Qura University</i></p>
