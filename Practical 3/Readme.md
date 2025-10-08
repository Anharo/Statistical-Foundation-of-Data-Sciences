# 🎓 Teachers Rating Dataset Analysis – Practical 3

## 🧭 Objective
This practical continues the analysis of the **Teachers Rating Dataset** (used in Practical 2).  
The goal is to perform **data filtering, duplication checks, and visualization** to explore relationships between instructors’ age, division, gender, and evaluation scores.

---

## 📊 Dataset Description

The dataset contains information about **university instructors** and their teaching evaluations.

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

---

## ⚙️ Tools Used

Python 3.x

NumPy

pandas

Matplotlib

Jupyter Notebook / Google Colab

## 🧾 Conclusion

Duplicates exist due to multiple courses taught by the same instructor.

Mean age changes slightly when considering unique professors only.

Lower-division instructors may receive slightly higher evaluation scores.

No strong linear relationship is observed between age and ratings.

Visualization by gender and tenure highlights small variations, but no major bias is apparent.
