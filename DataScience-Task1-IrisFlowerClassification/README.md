# Task 1 — Iris Flower Species Classification

<div align="center">

[![Track](https://img.shields.io/badge/Track-Data%20Science-2ea44f?style=for-the-badge&logo=python&logoColor=white)](https://oasisinfobyte.com/)
[![Task](https://img.shields.io/badge/Task-1%20--%20Iris%20Classification-blue?style=for-the-badge)](https://oasisinfobyte.com/)
[![Status](https://img.shields.io/badge/Status-100%25%20Completed-brightgreen?style=for-the-badge)](#-project-checklist)
[![Best Model](https://img.shields.io/badge/Best%20Model-KNN%20(k=3)-blueviolet?style=for-the-badge)](#-model-benchmark--evaluation-metrics)

**Program:** Oasis Infobyte Summer Internship Program (SIP) — Data Science Track  
**Author:** **Youssef Laaroussi** (Master's in Artificial Intelligence & Big Data)  
**Deliverable:** `Iris_Flower_Classification.ipynb` (Google Colab & Jupyter Ready, Pre-executed)

</div>

---

## 📌 Executive Summary & Objective

Train and rigorously benchmark multiple machine learning classifiers to identify an iris flower's species (*Setosa*, *Versicolor*, *Virginica*) from four physical measurements: sepal length, sepal width, petal length, and petal width. 

The analytical focus is grounded in **statistical feature selection, leak-free cross-validation, and model interpretability**, ensuring that the final model selection is substantiated by mathematical evidence rather than an arbitrary split.

---

## 📋 Project Checklist

- [x] Repository named strictly `OIBSIP`.
- [x] All notebooks pre-executed with visible tables, outputs, and visualizations.
- [x] Load the Iris dataset using `sklearn.datasets.load_iris()` (Section 2).
- [x] Exploratory Data Analysis (EDA): shape verification, dtypes, missing values (0 nulls), summary statistics (Section 3).
- [x] Visualisations: pairplot by species and multi-panel box plots for all dimensions (Section 4).
- [x] Feature selection discussion: quantitative ANOVA F-test (`f_classif`) proving petal length/width dominance ($F > 960$) (Section 5).
- [x] Train / Test Split: 80/20 stratified split (`train_test_split`, `stratify=y`, `random_state=42`) (Section 6).
- [x] Train at least 2 classifiers: 4 distinct model families (Logistic Regression, KNN, Decision Tree, Random Forest) (Section 8).
- [x] Model Evaluation Suite: Accuracy, Confusion Matrix, Classification Report (Precision, Recall, F1, ROC-AUC) (Section 9).
- [x] Best Model Declaration: Declared **K-Nearest Neighbours ($k=3$)** with 96.7% CV accuracy and full justification (Section 11).
- [x] Clean, commented Jupyter Notebook with PCA projection and serialized pipeline.

---

## 🔬 Skills & Methodological Rigor

- **Statistical feature selection:** Applied ANOVA F-test (`f_classif`) to quantitatively rank feature discriminative power before model training.
- **Hyperparameter tuning via cross-validation:** Grid search over KNN's $k$ and Decision Tree's `max_depth` evaluated with `StratifiedKFold` (5 folds) strictly on training data.
- **Comprehensive model comparison:** 4 distinct model families evaluated on both held-out test split and 5-fold CV (Logistic Regression, KNN, Decision Tree, Random Forest).
- **Full metric suite:** Accuracy, Precision, Recall, Macro/Weighted F1-score, ROC-AUC (One-vs-Rest), Cohen's Kappa, and Matthews Correlation Coefficient (MCC).
- **Model interpretability:** Permutation feature importance (robust to collinearity) cross-validated with ANOVA F-rankings.
- **Dimensionality reduction for visualization:** 2D PCA projection with decision boundary visualization.
- **Model persistence:** Production-ready serialized pipeline saved with `joblib` (`iris_best_model.joblib`).

---

## 📊 Visual Insights & Key Findings

### 1. Exploratory Data Analysis & Morphological Separation
Petal length and petal width show complete linear separation for *Iris Setosa*, while *Versicolor* and *Virginica* exhibit slight morphological overlap in transition zones.

![Species Pairplot](assets/pairplot_species.png)

### 2. Statistical Feature Discriminative Power (ANOVA F-Test)
ANOVA F-test demonstrates that petal length ($F \approx 1180$) and petal width ($F \approx 960$) provide over 10× more discriminative power than sepal width ($F \approx 49$).

![ANOVA Feature Ranking](assets/anova_feature_ranking.png)

### 3. Multi-Model Confusion Matrix Comparison
All 4 models were evaluated under identical stratified test conditions. K-Nearest Neighbours ($k=3$) and Random Forest achieve optimal classification with only 2 edge-case misclassifications.

![Confusion Matrices](assets/confusion_matrices.png)

### 4. PCA Decision Boundary & Permutation Importance
PCA projection into 2 principal components illustrates the non-linear boundaries formed by the KNN classifier, while permutation feature importance independently corroborates the ANOVA F-test ranking.

| PCA Decision Boundary | Permutation Feature Importance |
| :---: | :---: |
| ![PCA Decision Boundary](assets/pca_decision_boundary.png) | ![Permutation Importance](assets/permutation_importance.png) |

---

## 📈 Model Benchmark & Evaluation Metrics

| Model | Hyperparameters | 5-Fold CV Accuracy (Mean ± Std) | Held-out Test Accuracy | Macro F1-Score | Status |
| :--- | :--- | :---: | :---: | :---: | :--- |
| **K-Nearest Neighbours** | **$k = 3$, Euclidean** | **96.7% ± 3.3%** | **93.3%** | **0.933** | 🏆 **Selected Best Model** |
| Random Forest | $n = 100$, max_depth=None | 95.0% ± 3.7% | 93.3% | 0.933 | Strong Ensemble Baseline |
| Logistic Regression | $C = 1.0$, L2 penalty | 95.8% ± 3.1% | 93.3% | 0.933 | Competitive Linear Baseline |
| Decision Tree | max_depth = 3 (tuned) | 94.2% ± 4.2% | 90.0% | 0.900 | Interpretable Rule-Based |

---

## 📁 Repository Structure

```text
DataScience-Task1-IrisFlowerClassification/
├── Iris_Flower_Classification.ipynb   # Full interactive notebook with all outputs
├── iris_best_model.joblib             # Serialized best model bundle (model, scaler, metadata)
├── README.md                          # Comprehensive technical report & documentation
└── assets/                            # High-resolution generated plots
    ├── pairplot_species.png
    ├── anova_feature_ranking.png
    ├── confusion_matrices.png
    ├── pca_decision_boundary.png
    └── permutation_importance.png
```

---

## 🚀 How to Run
 
### Option A: Run Locally (Jupyter Notebook / VS Code)
1. **Activate virtual environment & navigate to task:**
   ```bash
   source venv/bin/activate    # On Windows: venv\Scripts\activate
   cd DataScience-Task1-IrisFlowerClassification
   ```
2. **Launch Jupyter Notebook:**
   ```bash
   jupyter notebook Iris_Flower_Classification.ipynb
   ```
   *(The Iris dataset is built directly into scikit-learn — no external CSV download needed).*

### Option B: Run on Google Colab
1. Upload `Iris_Flower_Classification.ipynb` to [Google Colab](https://colab.research.google.com/).
2. Run all cells (`Runtime` ➔ `Run all` or `Ctrl+F9`).

---

### 📦 Reload the Serialized Model in Python
```python
import joblib

bundle = joblib.load("iris_best_model.joblib")
model = bundle["model"]
scaler = bundle["scaler"]
target_names = bundle["target_names"]

print(f"Loaded {model.__class__.__name__} successfully for classes: {target_names}")
```
