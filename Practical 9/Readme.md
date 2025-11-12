# 🌸 Iris Dataset – K-Nearest Neighbors (KNN) Classification

## 🧭 Objective
The aim of this practical is to perform **classification using the K-Nearest Neighbors (KNN)** algorithm on the **Iris dataset**.  
The practical focuses on exploring the dataset through **Exploratory Data Analysis (EDA)**, performing **feature scaling**, training the **KNN model**, and determining the **optimal K value** based on the error rate.  
Python libraries such as **pandas**, **NumPy**, **scikit-learn**, and **Matplotlib** were used for data handling, model building, and visualization.

---

## 📊 Dataset Description
The **Iris dataset** is a classic multivariate dataset introduced by **Sir Ronald A. Fisher**.  
It contains 150 samples of iris flowers, categorized into three species — **Setosa**, **Versicolor**, and **Virginica** — with four features describing each flower.

| Column | Description |
|---------|-------------|
| **sepal length (cm)** | Length of the sepal in centimeters |
| **sepal width (cm)** | Width of the sepal in centimeters |
| **petal length (cm)** | Length of the petal in centimeters |
| **petal width (cm)** | Width of the petal in centimeters |
| **species** | Class label representing the flower species (Setosa, Versicolor, Virginica) |

---

## 🧰 Tools & Libraries Used
| Tool/Library | Purpose |
|---------------|----------|
| **Python (v3.x)** | Programming environment for implementation |
| **pandas** | Data handling and manipulation |
| **NumPy** | Numerical computations and scaling operations |
| **scikit-learn (sklearn)** | Model creation, preprocessing, evaluation, and metrics |
| **Matplotlib** | Visualization of error rates and decision boundaries |
| **Google Colab / Jupyter Notebook** | Environment for writing and executing code interactively |

---

## ⚙️ Steps Performed

### **Step 1 – EDA (Exploratory Data Analysis)**
- Displayed dataset using `head()`, `describe()`, and `groupby('species').mean()`.  
- Understood class distribution and relationships between features.

### **Step 2 – Feature Scaling**
- Standardized features using `StandardScaler()` to normalize the data.  
- Ensured all variables contributed equally to the distance metric.

### **Step 3 – Train-Test Split & Model Training**
- Split dataset into **80% training** and **20% testing** data.  
- Trained a **KNN model** using `KNeighborsClassifier`.
  
### Step 4: Making the Confusion Matrix & Predicting Accuracy Score
- Made Confusion Matrix of checking how accurate the classification were.
  
### Step 5: Making Classification Report
- Made Classification report for detailed analysis of model.
  
### **Step 6 – Comparing Error Rate with K Value**
- Tested multiple K values (1–20).  
- Calculated and plotted **Mean Error vs K** to analyze performance.

### **Step 8 – Finding the Best K**
- Determined the **optimal K** with minimum error rate.  
- Retrained the model with best K and evaluated accuracy.

### Step 7: Plot the error values against K values
- Plotted the error values against K values.
  
### **Step 9 – Visualizing Test Results**
- Visualized **decision boundaries** using Petal Length and Petal Width.  
- Displayed classification zones for each flower species.

---

## 🧾 Results Summary
- The **best K value** was found to be around **K = 5**.  
- The model achieved **>95% accuracy** on the test dataset.  
- The **error rate** decreased initially and stabilized after K=5, showing balanced bias-variance trade-off.  
- The **visualization** clearly separated all three species regions.

---

## 🏁 Conclusion
This practical demonstrated how **K-Nearest Neighbors (KNN)** can be applied for **multi-class classification** using the Iris dataset.  
Through this practical, I learned to:

- Perform **data preprocessing, scaling, and EDA**.  
- Implement and tune a **KNN classifier** in Python.  
- Evaluate performance using accuracy and error plots.  
- Visualize decision boundaries to understand classification results.

Overall, this exercise enhanced understanding of **distance-based learning**, **model evaluation**, and **data preprocessing** in **Machine Learning** using Python.

