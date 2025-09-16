# Statistical Foundation of Data Sciences (CSU1658 Practical)

This repository contains solutions for the **Statistical Foundation of Data Sciences (CSU1658 Practical)**.  
All work was completed in **Google Colab** using Python libraries such as **NumPy and Pandas**.  

---

## 📌 Subject Details
- **Subject Name:** Statistical Foundation of Data Sciences  
- **Subject Code:** CSU1658 Practical  
- **Practical 1**  - Testing Pandas and Numpy
---

## 🛠️ Instructions
- A **synthetic dataset** was created with some `NaN` values to simulate real-world scenarios.  
- A **random seed = 42** was set at the beginning for reproducibility.  
- While solving, `NaN` values were handled carefully (ignored or imputed, but not by dropping entire rows unnecessarily).  

---

## 📝 Practical 1 – Problems & Solutions  

### **Problem 1: Mean, Median, Age-weighted Mean**
- Created a synthetic dataset with **Age** and **Income** columns (with some `NaN` values).  
- Used `pandas.DataFrame.mean()` and `median()` to calculate mean and median while ignoring `NaN`.  
- For **age-weighted mean of income**, used `numpy.average(salary, weights=age)` after removing `NaN`.  
- **Explanation added**: A weighted mean is preferable when different observations contribute unequally (e.g., giving more weight to older individuals when analyzing income).  

---

### Problem 2: Standardization (z-score) & Outliers

**How I did it:**

- First, I calculated the **mean** and **standard deviation** of the `Salary` column while ignoring `NaN` values:
   ```python
   mean_salary = df["Salary"].mean(skipna=True)
   std_salary = df["Salary"].std(skipna=True)
  Then, I computed the z-scores for each value in the Salary column using the formula:
                z= (x-𝜇)/σ          	​
- Counted outliers using the rule `|z| > 3`.  
- Ensured no unnecessary row deletions by using `dropna()` only on relevant columns.  

---

### **Problem 3: Age Bins & Group Statistics**
- Created bins `[18-25), [25-35), [35-45), [45-60)` using `pandas.cut()`.  
- Grouped the dataset by bins using `groupby()`.  
- Computed for each bin:  
  - Count of observations (`count()`)  
  - Mean income (`mean()`)  
  - Median score (`median()`)  
- Displayed results as a **tidy DataFrame** and sorted by age bin.  

---

### **Problem 4: Multi-dimensional Array Operations**
- Created a **2D NumPy array**.  
- Showcased:  
  - **Shape and Resize** → `array.shape`, `array.size`, `array.T` (transpose), and `flatten()`.  
  - **Negative Indexing** → Demonstrated how `array[-1]` works and intentionally caused an error using invalid slicing.  
  - **Arithmetic Operations** → Showed broadcasting (adding scalar to array) and dot product (`np.dot()`).  
  - **Linear Algebra** → Used `numpy.linalg.det()` for determinant and `numpy.linalg.inv()` for inverse.  

---

## 🎯 Goal
To implement statistical concepts step by step, understand their use in real-world data, and strengthen numerical computation skills using Python.  

---

## 🛠️ Tech Stack
- **Python**  
  - NumPy  
  - Pandas  

---

## 🚀 How to Run
1. **Clone the repository**
   ```bash
   git clone https://github.com/Anharo/Statistical-Foundation-of-Data-Sciences.git
2. **Navigate into the project folder**
   ```bash
   cd Statistical-Foundation-of-Data-Sciences
3. **Open the desired practical notebook**
   Using Jupyter Notebook:
   ```bash
   jupyter notebook
Then open the notebook manually, e.g.
Practical 1 Testing Pandas and Numpy/Practical_1.ipynb

Using Google Colab:
Upload the .ipynb file from the folder into Colab and run it there.
