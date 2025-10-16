# 🎓 Teachers Rating Dataset Analysis

## 🧭 Objective
The aim of this practical is to analyze a dataset of teachers’ ratings using Python libraries such as NumPy, pandas, and SciPy.
The task involves performing statistical analysis, conducting hypothesis tests, calculating correlations, and interpreting the relationships among variables related to teaching evaluations.

---

## 📊 Dataset Description

The dataset contains information about **university instructors** and their teaching evaluation ratings.

| Column | Description |
|---------|--------------|
| **Prof** | Professor name (duplicates may appear for multiple courses) |
| **Gender** | Male or Female |
| **Tenure** | Indicates whether the professor is tenured (Yes or No) |
| **Beauty** | Instructor’s attractiveness score (contains outliers) |
| **Rating** | Teaching evaluation score (1–5 scale) |
| **Students** | Number of students in the class *(includes one outlier with 300 students)* |
| **Age** | Instructor’s age |
| **Division** | Course type: “Lower” or “Upper” Division |

> 🧩 *Note: This is a synthetic dataset designed for statistical analysis practice.*

---

## ⚙️ Tools Used

- **Python 3.x**  
- **NumPy**  
- **pandas**  
- **Scipy**  
- **Jupyter Notebook / Google Colab**

---

## 🧾 Results Summary
| **Test**            | **Question**                                               | **Hypothesis Decision**            | **Interpretation**                                                                                                                                                                                                                  |
| ------------------- | ---------------------------------------------------------- | ---------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Q1. T-Test**      | Does gender affect teaching evaluation rates?              | p-value ≥ 0.05 → Fail to reject H₀ | Gender **does not affect** teaching evaluation scores. There is **no significant difference** in evaluation means between male and female instructors.                                                                              |
| **Q2. ANOVA**       | Does beauty score for instructors differ by age?           | Fail to reject H₀                  | There is **no significant difference** in beauty scores across different age groups. Age **does not influence** beauty ratings.                                                                                                     |
| **Q3. Chi-Square**  | Is there an association between tenure and gender?         | Fail to reject H₀                  | **Tenure** and **gender** are **independent**. There is **no significant association** between the two categorical variables.                                                                                                       |
| **Q4. Correlation** | Is teaching evaluation score correlated with beauty score? | p-value > 0.05 → Fail to reject H₀ | There is **no significant correlation** between evaluation and beauty scores. Since **corr < 0**, the relationship is **weak and negative**, meaning as beauty increases, evaluation slightly decreases (though not significantly). |

---
## Conclusion

All statistical tests indicate no significant relationships between the tested variables. Gender, age, and tenure show no measurable effect on evaluation or beauty scores, and the weak negative correlation suggests that beauty does not meaningfully influence teaching evaluations in this dataset.


