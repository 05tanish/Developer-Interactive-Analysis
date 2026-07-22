# 📊 NovaTech Solutions — Engineering Productivity & Code Quality Analytics

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/Pandas-2.x-150458?style=for-the-badge&logo=pandas&logoColor=white" />
  <img src="https://img.shields.io/badge/NumPy-1.26+-013243?style=for-the-badge&logo=numpy&logoColor=white" />
  <img src="https://img.shields.io/badge/Matplotlib-3.8+-11557c?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Seaborn-0.13+-4c72b0?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white" />
</p>

---

## 📌 Business Problem Statement

**NovaTech Solutions** wants to understand how engineering practices, collaboration, code quality, and software delivery influence overall engineering performance and product reliability. The objective is to uncover hidden patterns, identify bottlenecks, and provide actionable recommendations based on historical engineering data (2023–2025).

---

## 📁 Project Structure

```
Developer-Interactive-Analysis/
│
├── 📄 README.md                              # Project documentation (this file)
├── 📄 requirements.txt                       # Python dependencies
├── 📄 .gitignore                             # Git ignore rules
│
├── 🧹 data_cleaning.ipynb                    # Step 1 — Data Cleaning Pipeline
├── 📊 analysis.ipynb                         # Step 2 — 15 Advanced EDA Questions
├── 📈 basic_analysis.ipynb                   # Step 2 — 15 Standard EDA Questions
│
├── 🛠️ create_analysis_notebooks.py           # Notebook generation script
├── 📂 engineering_productivity_dataset.csv   # Raw dataset (25,000 × 54)
└── 📂 cleaned_engineering_data.csv           # Cleaned dataset (output of Step 1)
```

---

## 📋 Dataset Overview

| Category | Columns |
|:--|:--|
| **Developer** | Developer_ID, Developer_Name, Age, Gender, Country, Experience_Years, Team, Role, Work_Mode |
| **Repository** | Repository_Name, Repository_Type, Language, Framework, Repository_Size_MB, Stars, Forks, Open_Issues |
| **Commit & PR** | Commit_ID, Files_Changed, Lines_Added, Lines_Deleted, PR_Status, Merge_Time_Hours, Review_Time_Hours, Reviewers |
| **CI/CD & Quality** | Build_Status, Build_Duration_Minutes, CI_Failures, Test_Coverage, Deployment_Status, Bugs_Introduced, Production_Bugs |
| **Productivity** | Coding_Hours, Meeting_Hours, Focus_Hours, Story_Points, Sprint, Velocity |

- **Records:** 25,000 rows
- **Columns:** 54 (raw) → 59 (after feature engineering)
- **Time Period:** 2023–2025

---

## 🧹 Data Quality Issues Found & Fixed

| Issue | Details | Fix Applied |
|:--|:--|:--|
| Duplicate rows | Present in raw data | Removed via `drop_duplicates()` |
| Language typos | `Pyhton`, `JavaScrip`, `RUST`, `typescript` | Mapped to standard names (`Python`, `JavaScript`, etc.) |
| Team inconsistencies | `Devops`, `Back-end`, `frontend` | Merged into `DevOps`, `Backend`, `Frontend` |
| Boolean columns | Weekend/Night_Commit had `'YES'`, `'no'`, `'TRUE'`, `'False'` | Converted to binary 0/1 |
| Build Status | `Passed` vs `Success` | Unified to `Success` / `Failed` |
| Negative values | Age, Experience, Repo Size, Stars, Build Duration | Replaced with NaN → median imputed |
| Missing values | Scattered across numeric & categorical columns | Numeric: median, Categorical: mode |
| Floating point noise | `12.000000000000002` in computed columns | Rounded to 2 decimal places |

---

## 📓 Notebooks

### 🧹 `data_cleaning.ipynb` — Data Cleaning Pipeline (Run First)

Loads the raw CSV, performs basic exploration (head, tail, info, describe, missing values, duplicates), cleans all issues listed above, engineers new features (`Code_Churn`, `Total_Work_Hours`, `Experience_Tier`, success flags), and saves `cleaned_engineering_data.csv`.

---

### 📈 `analysis.ipynb` — 15 Standard EDA Questions

| # | Question | Chart Type |
|:--|:--|:--|
| 1 | Which team has the highest productivity? | Bar Chart |
| 2 | Which language has the most bugs? | Bar Chart |
| 3 | Does experience reduce bugs? | Scatter + Regression |
| 4 | Which repos have the most open issues? | Horizontal Bar |
| 5 | Is code churn related to bugs? | Scatter Plot |
| 6 | Does test coverage reduce production bugs? | Scatter Plot |
| 7 | Which sprint had the most bugs? | Bar Chart |
| 8 | Which team spends the most on code reviews? | Box Plot |
| 9 | Is coding time related to productivity? | Scatter Plot |
| 10 | Which repos have the longest build duration? | Horizontal Bar |
| 11 | How does repo size affect build duration? | Scatter Plot |
| 12 | Which developers fixed the most bugs? | Horizontal Bar |
| 13 | Does files changed increase review time? | Scatter Plot |
| 14 | Which teams have the highest deploy success rate? | Bar Chart |
| 15 | Which factors correlate with software quality? | Heatmap |

Ends with a single **Executive Summary**.

---

## 🚀 Getting Started

### Prerequisites

```bash
pip install -r requirements.txt
```

### Run Order

```bash
# Step 1: Clean the data first
jupyter nbconvert --execute data_cleaning.ipynb --to notebook --inplace

# Step 2: Run either analysis notebook
jupyter nbconvert --execute analysis.ipynb --to notebook --inplace
jupyter nbconvert --execute basic_analysis.ipynb --to notebook --inplace
```

Or simply open in Jupyter Notebook:

```bash
jupyter notebook
```

> **⚠️ Important:** Always run `data_cleaning.ipynb` first to generate `cleaned_engineering_data.csv`. The analysis notebooks depend on this file.

---

## 🔧 Tech Stack

| Library | Purpose |
|:--|:--|
| `pandas` | Data manipulation & aggregation |
| `numpy` | Numerical operations & NaN handling |
| `matplotlib` | Chart rendering & customization |
| `seaborn` | Statistical visualizations |

---

## ✅ Quality Checklist

- [x] Clean, modular, well-commented code
- [x] All notebooks run end-to-end without errors
- [x] Separate data cleaning pipeline (`data_cleaning.ipynb`)
- [x] Basic exploration (head, tail, describe, info) in cleaning notebook
- [x] No `display()` calls — output via `print()` and `.to_string()`
- [x] X-axis labels rotated to prevent overlap
- [x] No per-question summaries — single Executive Summary at end
- [x] No loops for question generation — each question written explicitly
- [x] Matplotlib/Seaborn only (no Plotly)
- [x] `README.md` and `requirements.txt` included
- [x] Git version control ready (`.gitignore` configured)

---

## 👤 Author

**Tanish Jain**

---
