# 🎓 Student Lifestyle Analysis

A data analysis and machine learning project exploring how students' daily habits — sleep, study time, social activity, and physical exercise — relate to their **stress levels** and **academic performance (GPA)**.

---

## 📌 Key Findings

- 📚 **Study hours** are the strongest predictor of stress (r = +0.74) — students who study more report significantly higher stress
- 😴 **Sleep** is the most impactful protective factor against stress (r = -0.30)
- 🤖 A **Random Forest classifier** predicts student stress level with **100% accuracy** using only lifestyle features
- 📊 GPA is approximately **normally distributed** with a mean of **3.12** across all students

---

## 📊 Project Overview

This project combines two datasets:
- **Student lifestyle dataset** — daily hours spent on various activities, GPA, and stress level
- **US student demographic dataset** — real names, age, and city

The analysis covers data cleaning, exploratory visualizations, correlation analysis, and a machine learning classifier to predict stress level (Low / Moderate / High).

---

## 📁 Project Structure

```
student-lifestyle-analysis/
├── data/
│   ├── student_lifestyle_dataset.csv   # Lifestyle & academic data
│   └── us_dataset_real_names.csv       # Demographic data
├── results/
│   └── plots/                          # Generated visualizations
├── student_lifestyle_analysis.ipynb    # Main analysis notebook
└── pyproject.toml                      # Project dependencies
```

---

## 🔍 What's Inside the Notebook

1. **Data Loading & Cleaning**
   - Removes duplicates
   - Fixes invalid GPA values (replaced with mean of valid values)
   - Fixes invalid hour values (NaN, negative, or > 24) using proportional fill
   - Encodes stress level as an ordered categorical: Low < Moderate < High

2. **Data Merging**
   - Joins lifestyle data with demographic data on student ID

3. **Exploratory Analysis**
   - Youngest student in the dataset
   - Average GPA ranked by city
   - GPA distribution histogram with mean & median lines

4. **Correlation Heatmaps**
   - Combined matrix of all daily activities vs stress level
   - Focused heatmap: Sleep hours vs stress level

5. **Machine Learning — Stress Level Classifier**
   - Model: `RandomForestClassifier` (100 trees)
   - Features: Study, Sleep, Social, Extracurricular, Physical Activity hours + GPA
   - Train / Test split: 80% / 20%
   - Outputs: Accuracy, Classification Report, Confusion Matrix, Feature Importances

---

## 📈 Results

All generated plots are saved to `results/plots/`:

| File | Description |
|---|---|
| `histogram_gpa.jpg` | GPA distribution across all students |
| `heatmap_combined.jpg` | Correlation matrix: all daily hours & stress level |
| `heatmap_sleep.jpg` | Focused correlation: sleep hours & stress level |
| `confusion_matrix.jpg` | Model prediction accuracy per stress class |
| `feature_importance.jpg` | Which lifestyle features most predict stress level |

---

## 🚀 Getting Started

### Prerequisites

- Python ≥ 3.14
- [uv](https://github.com/astral-sh/uv) *(recommended)* or pip

### Install dependencies

```zsh
uv sync
```

Or with pip:

```zsh
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

### Run the notebook

```zsh
jupyter notebook student_lifestyle_analysis.ipynb
```

---

## 🛠️ Tech Stack

| Library | Purpose |
|---|---|
| `pandas` | Data manipulation and cleaning |
| `NumPy` | Numerical operations |
| `Matplotlib` / `Seaborn` | Visualizations |
| `scikit-learn` | Machine learning |

---

## 👤 Author

**Matej Zemánek** — [github.com/MZemik](https://github.com/MZemik)
