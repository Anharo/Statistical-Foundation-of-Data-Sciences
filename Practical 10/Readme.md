# 🍷 Wine Dataset Analysis

## 🧭 Objective
The aim of this practical is to analyze the **Wine dataset** using Python libraries such as **NumPy**, **pandas**, and **Matplotlib**.  
The task includes statistical analysis, visualization, covariance interpretation, data scaling, and dimensionality reduction using PCA to study how chemical properties differentiate wine classes.

---

## 📊 Dataset Description

The dataset contains information about **chemical composition of wines** originating from the same region of Italy, categorized into three wine classes.

| Column | Description |
|---------|--------------|
| **Alcohol** | Alcohol content of the wine |
| **Malic Acid** | Amount of malic acid |
| **Ash** | Ash content |
| **Alcalinity of Ash** | Alkalinity level of ash |
| **Magnesium** | Magnesium concentration |
| **Total Phenols** | Total phenolic compounds |
| **Flavanoids** | Phenols contributing to flavor |
| **Nonflavanoid Phenols** | Phenols not contributing to flavor |
| **Proanthocyanins** | Pigment-related compounds |
| **Color Intensity** | Intensity of wine color |
| **Hue** | Shade of the wine |
| **OD280/OD315** | Diluted wine optical measurement |
| **Proline** | Amino acid with high variation across classes |
| **Target** | Wine class (0, 1, 2) |

> 🧩 *Note: This dataset is sourced from `sklearn.datasets` and is widely used for statistical and machine learning analysis.*

---

## ⚙️ Tools Used

Python 3.x

NumPy

pandas

Matplotlib / Seaborn

Scikit-Learn

Jupyter Notebook / Google Colab

---

## 🧾 Conclusion

The dataset is **multivariate and cross-sectional**.

Descriptive statistics show large variation across features, especially **Proline**, leading to scale imbalance.

Scaling using `StandardScaler` improves comparability between features.

Covariance analysis reveals strong relationships between phenolic components.

After applying PCA, **class separation becomes clearer**, showing three distinguishable wine groups.

Statistical analysis and visualizations provide meaningful insights into wine composition and its classification.

---
