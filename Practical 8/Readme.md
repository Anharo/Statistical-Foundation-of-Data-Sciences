# 🌳 Decision Tree Classifier — Pima Indians Diabetes Dataset

## 🧭 Objective
The aim of this practical is to **classify individuals as diabetic or non-diabetic** using the **Decision Tree algorithm** on the **Pima Indians Diabetes dataset**.  
The experiment explores how different health-related factors such as **Glucose**, **BMI**, and **Age** contribute to diabetes prediction.  
Both **Entropy (Information Gain)** and **Gini Index** criteria are used to evaluate model performance and determine the best root node.

---

## 📊 Dataset Description
The dataset named **`diabetes.csv`** contains diagnostic measurements of female Pima Indian patients aged 21 years or older.  
It is used to predict whether a patient has diabetes based on certain physiological features.

| Column | Description |
|---------|-------------|
| **Pregnancies** | Number of times the patient was pregnant |
| **Glucose** | Plasma glucose concentration after 2 hours |
| **BloodPressure** | Diastolic blood pressure (mm Hg) |
| **SkinThickness** | Triceps skin fold thickness (mm) |
| **Insulin** | 2-hour serum insulin (mu U/ml) |
| **BMI** | Body Mass Index (weight in kg / height in m²) |
| **DiabetesPedigreeFunction** | Diabetes heredity function score |
| **Age** | Age of the individual (years) |
| **Outcome** | Target variable — 0 (Non-diabetic), 1 (Diabetic) |

---

## 🧰 Tools & Libraries Used

| Tool/Library | Purpose |
|---------------|----------|
| **Python (v3.x)** | Programming environment |
| **pandas** | Data manipulation and preprocessing |
| **NumPy** | Mathematical and statistical computations |
| **scikit-learn** | Model building and evaluation (Decision Tree, train-test split) |
| **Matplotlib** | Visualization of decision tree and data insights |
| **Jupyter Notebook / Google Colab** | Code execution and result visualization |

---

## ⚙️ Methodology

### 1️⃣ Data Loading and Exploration
- Load the dataset using **pandas** and examine its structure, missing values, and summary statistics.

### 2️⃣ Feature Selection
- Independent variables: All columns except `Outcome`  
- Dependent variable: `Outcome`

### 3️⃣ Train-Test Split
-Split data for training and testing.

### 4️⃣ Model Building
- Build two models using DecisionTreeClassifier:

```python
  dt_entropy = DecisionTreeClassifier(criterion='entropy', max_depth=3, random_state=42)
  dt_gini = DecisionTreeClassifier(criterion='gini', max_depth=3, random_state=42)
```
### 5️⃣ Visualization
- Visualized both the decision trees.

### 6️⃣ Manual Calculation
-Compute Entropy, Information Gain, and Gini Index for the feature Glucose to verify root node selection.

## 🧾 Results Summary

| Criterion      | Root Node | Accuracy | Remarks                  |
| -------------- | --------- | -------- | ------------------------ |
| **Entropy**    | Glucose   | ~75%     | Highest Information Gain |
| **Gini Index** | Glucose   | ~75%     | Highest Gini Reduction   |

-Both criteria produced similar accuracy and tree structures.
-Glucose was identified as the root node due to maximum impurity reduction.
-BMI and Age appeared as secondary splitting factors.

## 🧮 Key Formulas Used
## 📊 Entropy, Gini Index, and Information Gain

## 📊 Entropy, Gini Index, and Information Gain

### 🔹 Entropy
Entropy measures the impurity or uncertainty in a dataset.  
It is calculated using the formula:

**Entropy = − Σ ( pᵢ × log₂(pᵢ) )**

Where:  
- *pᵢ* = probability of class *i*

---

### 🔹 Gini Index
The Gini Index measures the impurity in a dataset and is calculated as:

**Gini = 1 − Σ ( pᵢ² )**

Where:  
- *pᵢ* = probability of class *i*

---

### 🔹 Information Gain
Information Gain (IG) represents the reduction in entropy after splitting the dataset based on an attribute.  
It is calculated as:

**IG = Entropy(parent) − Σ ( (n_child / n_total) × Entropy(child) )**

Where:  
- *Entropy(parent)* = Entropy of the original dataset  
- *n_child* = number of samples in each child node  
- *n_total* = total number of samples before the split  
- *Entropy(child)* = Entropy after the split
