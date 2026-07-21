# 🧑‍💻 Developer Interactive Analysis

[![Python](https://img.shields.io/badge/Python-3.10%2B-blue?logo=python)](https://python.org)
[![Pandas](https://img.shields.io/badge/Pandas-2.x-150458?logo=pandas)](https://pandas.pydata.org)
[![NumPy](https://img.shields.io/badge/NumPy-1.26%2B-013243?logo=numpy)](https://numpy.org)
[![Seaborn](https://img.shields.io/badge/Seaborn-0.13%2B-4c72b0)](https://seaborn.pydata.org)
[![Matplotlib](https://img.shields.io/badge/Matplotlib-3.8%2B-11557c)](https://matplotlib.org)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter)](https://jupyter.org)

---

## 📋 Project Overview

This project performs a full **Exploratory Data Analysis (EDA)** and **Data Cleaning Pipeline** on the *Open Source Developer Ecosystem* dataset — a real-world messy dataset capturing developer activity, contributions, coding behaviors, and project metadata across 5,000+ records.

The notebook walks through 15 structured questions that guide data wrangling, statistical analysis, and visualization — transforming raw, noisy data into clean, analysis-ready insights.

---

## 📁 Project Structure

```
Developer Interactive Analysis/
│
├── 📄 README.md                                         ← You are here
├── 📊 Open_Source_Developer_Ecosystem_Messy_Dataset.csv ← Raw unclean dataset
├── 📓 analysis.ipynb                                    ← Main analysis notebook
└── 📦 cleaned_data.csv                                  ← Output: cleaned dataset
```

---

## 📂 Dataset Description

| Field | Description |
|---|---|
| `Developer_ID` | Unique developer identifier (e.g., D0135) |
| `Developer_Name` | Name of the developer (has missing values) |
| `Team` | Team the developer belongs to (Backend, Frontend, DevOps, AI, Platform) |
| `Experience_Years` | Years of experience (has NaN values) |
| `Country` | Country of the developer |
| `Repository` | Project repository name (Atlas, Nova, Forge) |
| `Language` | Programming language used (has typos & inconsistencies) |
| `Stars` | Repository stars (999999 = sentinel for invalid, -5 = invalid) |
| `Forks` | Number of forks |
| `Watchers` | Number of watchers |
| `Open_Issues` | Number of open issues |
| `Closed_Issues` | Number of closed issues |
| `Pull_Requests` | Total pull requests |
| `Merged_PRs` | Merged pull requests |
| `Commit_Date` | Date of commit (mixed formats: YYYY-MM-DD and DD/MM/YYYY) |
| `Commit_Time` | Time of commit (8PM, 00:00, 25:61 = invalid) |
| `Files_Changed` | Number of files changed per commit |
| `Lines_Added` | Lines of code added |
| `Lines_Deleted` | Lines of code deleted |
| `Coding_Hours` | Hours spent coding |
| `Bugs_Introduced` | Number of bugs introduced |
| `Bugs_Fixed` | Number of bugs fixed |
| `Code_Review_Time_Hours` | Hours spent on code review |
| `Build_Status` | CI/CD build status (Success, FAIL, Failed, empty) |
| `CI_Failures` | Number of CI failures |
| `Weekend_Commit` | Whether commit was on weekend (Yes/No) |
| `Night_Commit` | Whether commit was at night (Yes/No) |
| `Sprint` | Sprint identifier (Sprint-1 to Sprint-12) |
| `Repo_Size_MB` | Repository size in megabytes |
| `License` | Open source license (MIT, GPL, Apache-2.0, empty) |

**Total rows:** ~5,011 | **Total columns:** 30

---

## 🧹 Key Data Quality Issues Found

| Issue | Description |
|---|---|
| 🔴 **Sentinel Star Values** | 999999 and -5 used for invalid star counts |
| 🟠 **Mixed Date Formats** | Both YYYY-MM-DD and DD/MM/YYYY present |
| 🟡 **Invalid Times** | 25:61 used as a sentinel for unknown commit time |
| 🟡 **Language Typos** | pyhton, PYTHON, python → all mean Python |
| 🔵 **Missing Names** | Developer names are blank strings or NaN |
| 🔵 **Missing Experience** | ~40% of Experience_Years is missing |
| 🔵 **Inconsistent Build Status** | FAIL, Failed, Success, empty values |
| 🔵 **Missing Language & License** | Several rows have empty language or license |

---

## 🛠️ Libraries Used

| Library | Purpose |
|---|---|
| `pandas` | Data loading, cleaning, and manipulation |
| `numpy` | Numerical operations, NaN handling |
| `matplotlib` | Base plotting and chart generation |
| `seaborn` | Statistical visualizations |
| `pyplot` | High-level matplotlib interface |
| `sklearn` | Clustering via KMeans |

---

## 🚀 Getting Started

### 1. Navigate to the Project

```bash
cd "Developer Interactive Analysis"
```

### 2. Install Dependencies

```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

### 3. Launch Jupyter Notebook

```bash
jupyter notebook analysis.ipynb
```

### 4. Run All Cells

Inside Jupyter: **Kernel → Restart & Run All**

---

## 📊 Analysis Highlights (15 Questions)

| # | Question |
|---|---|
| Q1 | Load and inspect the raw dataset |
| Q2 | Identify all missing values per column |
| Q3 | Fix language name inconsistencies |
| Q4 | Normalize the Build_Status column |
| Q5 | Replace invalid star values with NaN |
| Q6 | Parse and unify mixed date formats |
| Q7 | Handle invalid commit times |
| Q8 | Fill missing Experience_Years with median |
| Q9 | Fill missing License and Developer_Name |
| Q10 | Distribution of developers by country and team |
| Q11 | Correlation heatmap of numeric features |
| Q12 | Build success rate by team |
| Q13 | Coding hours vs bugs introduced scatter plot |
| Q14 | KMeans clustering on developer productivity |
| Q15 | Export the fully cleaned dataset |

---

## 📈 Output

- **`cleaned_data.csv`** — Fully cleaned dataset ready for downstream analysis or ML modeling.

---

## 👤 Author

**Tanish Jain** — Developer Analytics & EDA Project

---

## 📜 License

This project is for educational and analytical purposes.
