<div align="center">

# 📊 Oasis Infobyte SIP — Data Science Track

[![Python](https://img.shields.io/badge/Python-3.9%2B-blue?logo=python&logoColor=white)](https://www.python.org/)
[![Track](https://img.shields.io/badge/Track-Data%20Science-2ea44f)](https://oasisinfobyte.com/)
[![Internship](https://img.shields.io/badge/Oasis%20Infobyte-OIBSIP-orange)](https://oasisinfobyte.com/)
[![Tasks Completed](https://img.shields.io/badge/Tasks%20Completed-5%20%2F%205%20(100%25)-brightgreen)](#-project-portfolio--executive-dashboard)
[![Code Style](https://img.shields.io/badge/Code%20Style-Production%20ML-blueviolet)](#-senior-data-science-methodology)
[![License](https://img.shields.io/badge/License-MIT-lightgrey)](LICENSE)

<p align="center">
  <strong>Comprehensive Machine Learning, NLP, Time-Series & Econometric Regression Portfolio</strong><br>
  Built during the <em>Oasis Infobyte Summer Internship Program (SIP)</em>.
</p>

---

### 👨‍💻 Candidate Profile
**Youssef Laaroussi**  
*Master's in Data Science & Artificial Intelligence*  
Specialized in Applied Machine Learning, Statistical Inference, and Predictive Modeling.  
🌐 [GitHub Profile](https://github.com/Youssef-Laaroussi) • 💼 [LinkedIn](https://linkedin.com) • 📧 Available for full-time Data Scientist & ML Engineer opportunities

---

</div>

## 📌 Executive Summary

This repository contains the complete portfolio of **all 5 tasks** developed for the **Oasis Infobyte Summer Internship Program (SIP) — Data Science Track**. While the program requirement mandates a minimum of 3 completed tasks, **100% of the tasks (5/5) have been completed** to the highest professional standard.

Every task goes beyond standard introductory machine learning tutorials by implementing:
- **Formal Statistical Hypothesis Testing:** (ANOVA F-tests, non-parametric Mann-Whitney U tests).
- **Leakage-Free Feature Engineering:** (Transformers fitted strictly on training folds, time-aware variable derivation).
- **Advanced Diagnostics:** (Residual analysis revealing econometric synergies, PCA projection).
- **Business-First Metric Alignment:** (Evaluation in real client currency ₹, cost-sensitive learning for class imbalances).

---

## 🏆 Project Portfolio & Executive Dashboard

| Task # | Project Title | Domain & Methodology | Best Model / Technique | Key Performance Metric | Directory |
| :---: | :--- | :--- | :--- | :--- | :---: |
| **01** | **[Iris Flower Species Classification](./DataScience-Task1-IrisFlowerClassification)** | Multi-class Classification & Statistical Feature Selection | **K-Nearest Neighbours ($k=3$)** | **96.7% 5-Fold CV Accuracy** *(93.3% Test)* | [`Explore ➔`](./DataScience-Task1-IrisFlowerClassification) |
| **02** | **[Unemployment Analysis in India](./DataScience-Task2-UnemploymentAnalysis)** | Temporal Econometrics & Macroeconomic Shock Analysis | **Mann-Whitney U Test & Time-Series** | **$p = 8.78 \times 10^{-17}$** *(COVID shock: +56.1% in Puducherry)* | [`Explore ➔`](./DataScience-Task2-UnemploymentAnalysis) |
| **03** | **[Used Car Price Prediction](./DataScience-Task3-CarPricePrediction)** | Non-Linear Regression & Free-Text Feature Engineering | **Random Forest Regressor** *(Trained on $\log(y)$)* | **$R^2 = 0.865$, MAE = ₹96,412** | [`Explore ➔`](./DataScience-Task3-CarPricePrediction) |
| **04** | **[Email & SMS Spam Detection](./DataScience-Task4-EmailSpamDetection)** | Natural Language Processing & Cost-Sensitive Learning | **Linear SVM (Balanced) + TF-IDF** | **98.4% Accuracy, 0.943 Spam F1** | [`Explore ➔`](./DataScience-Task4-EmailSpamDetection) |
| **05** | **[Multi-Channel Sales Prediction](./DataScience-Task5-SalesPrediction)** | Econometric Regression & Marketing Channel Attribution | **Degree-2 Polynomial Regression** | **$R^2 = 0.986$, RMSE = 0.723** | [`Explore ➔`](./DataScience-Task5-SalesPrediction) |

---

## 🏛️ Repository Architecture

The repository strictly follows the official Oasis Infobyte standardized nomenclature:  
`OIBSIP/[TrackName]-[Level/Task]-[ProjectName]/`

```text
OIBSIP/
├── .gitignore                                          # Git ignore configuration
├── requirements.txt                                    # Environment dependencies
├── README.md                                           # Master Portfolio Executive README
│
├── DataScience-Task1-IrisFlowerClassification/
│   ├── Iris_Flower_Classification.ipynb                # Pre-executed interactive notebook
│   ├── iris_best_model.joblib                          # Serialized trained model bundle
│   ├── README.md                                       # Comprehensive technical report
│   └── assets/                                         # Visual plots (pairplot, confusion matrix, PCA)
│
├── DataScience-Task2-UnemploymentAnalysis/
│   ├── Unemployment_Analysis_India.ipynb               # Pre-executed interactive notebook
│   ├── Unemployment in India.csv                       # Clean source dataset (740 records)
│   ├── README.md                                       # Macroeconomic & policy analysis
│   └── assets/                                         # Visual plots (time-series, regional shock)
│
├── DataScience-Task3-CarPricePrediction/
│   ├── Car_Price_Prediction.ipynb                      # Pre-executed interactive notebook
│   ├── CAR DETAILS FROM CAR DEKHO.csv                  # Deduplicated vehicle dataset
│   ├── README.md                                       # Feature engineering & regression report
│   └── assets/                                         # Visual plots (distributions, importance)
│
├── DataScience-Task4-EmailSpamDetection/
│   ├── Email_Spam_Detection.ipynb                      # Pre-executed interactive notebook
│   ├── spam.csv                                        # SMS Spam Collection dataset
│   ├── README.md                                       # NLP preprocessing & decision theory
│   └── assets/                                         # Visual plots (wordclouds, confusion matrices)
│
└── DataScience-Task5-SalesPrediction/
    ├── Sales_Prediction.ipynb                          # Pre-executed interactive notebook
    ├── Advertising.csv                                 # Multi-channel media spend dataset
    ├── README.md                                       # Econometric residual diagnostics
    └── assets/                                         # Visual plots (interaction synergies, residuals)
```

---

## 🔬 Senior Data Science Methodology

Each project in this repository adheres to production machine learning principles:

1. **Defensive Data Cleaning:**
   - Uncovering subtle edge-cases (e.g., corrupted CSV exports, two-word brand anomalies like *"Land Rover"*, hidden whitespace in datetime strings).
2. **Preventing Data Leakage:**
   - Preprocessing pipelines (`StandardScaler`, `TfidfVectorizer`) are fit strictly on training partitions and applied to validation/test sets.
3. **Statistical Justification Over Heuristics:**
   - Utilizing formal inferential statistics (ANOVA, Mann-Whitney U, residual correlation with interaction terms) rather than subjective visual guesses.
4. **Metric Translation to Real Business Impact:**
   - Regressors evaluated in real currency (Indian Rupees ₹) after stabilizing log-transformations.
   - Binary classifiers analyzed through the operational trade-off of False Positives vs. False Negatives.

---

## ⚙️ Quickstart & Local Installation

### Prerequisites
- Python 3.9+ installed
- Git installed

### 1. Clone the Repository
```bash
git clone https://github.com/Youssef-Laaroussi/OIBSIP.git
cd OIBSIP
```

### 2. Set Up Virtual Environment & Dependencies
```bash
python3 -m venv venv
source venv/bin/activate    # On Windows: venv\Scripts\activate
pip install -r requirements.txt
```

### 3. Launch Interactive Analysis
```bash
jupyter notebook
```
Navigate to any of the 5 task directories to inspect or rerun the notebooks.

### 4. Or Run via Google Colab
All notebooks are fully compatible with [Google Colab](https://colab.research.google.com/). Each notebook includes a resilient multi-path data loader that automatically resolves candidate paths (local workspace, Colab `/content/` root, customizable Google Drive path such as `/content/drive/MyDrive/your_path/`, or an interactive upload widget fallback).

---

## 📋 Project Checklist

This project is prepared in full compliance with the **Oasis Infobyte Master Onboarding Checklist**:
- [x] Repository named strictly `OIBSIP`.
- [x] Strict standardized folder naming format applied across all tasks.
- [x] All notebooks pre-executed with visible tables, outputs, and visualizations.
- [x] Each task folder contains source code, dataset, visual assets, and a standalone comprehensive README.
- [x] 100% completion (all 5 tasks delivered with statistical rigor).

---

## 📬 Contact & Opportunities

I am actively seeking opportunities in **Data Science**, **Machine Learning Engineering**, and **Applied AI**.

- **Author:** Youssef Laaroussi
- **Degree:** Master of Science in Data Science & Artificial Intelligence
- **GitHub:** [Youssef-Laaroussi](https://github.com/Youssef-Laaroussi)
- **Organization:** [Oasis Infobyte](https://oasisinfobyte.com/)
