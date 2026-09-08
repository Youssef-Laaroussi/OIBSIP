# Task 5 — Sales Prediction from Multi-Channel Advertising Spend

**Program:** Oasis Infobyte Summer Internship Program (SIP) — Data Science Track  
**Author:** **Youssef Laaroussi** (Master's in Data Science & Artificial Intelligence)  
**Deliverable:** `Sales_Prediction.ipynb` (Google Colab & Jupyter Ready, Pre-executed)

---

## 📌 Executive Summary & Objective

Predict product sales volume based on multi-channel advertising budgets across TV, Radio, and Newspaper. The primary objective is to conduct **rigorous residual diagnostics** to determine whether standard linear assumptions hold, uncover market synergies, and accurately rank channel marketing effectiveness without budget scale distortion.

---

## 🔬 Skills & Methodological Rigor

- **Advanced residual diagnostics:** Evaluated baseline linear regression residuals and proved mathematically that errors are not independently and identically distributed (i.i.d.), but strongly correlate with the $TV \times Radio$ interaction term ($r \approx 0.55$).
- **Scale-corrected feature attribution:** Demonstrated that raw unstandardized regression coefficients yield a misleading ranking (Radio appears to dominate TV purely due to smaller budget scale). Standardizing variables before computing coefficients uncovers the true hierarchy ($TV > Radio \gg Newspaper$).
- **Multi-family regression benchmarking:** Evaluated Ordinary Least Squares (OLS) Linear Regression, Random Forest Regressor, and Degree-2 Polynomial Regression on identical train/test splits.
- **Economic & marketing synergy identification:** Proved that marketing channels operate with multiplicative synergy—concurrent investment in TV and Radio drives an exponential lift in customer acquisition.

---

## 📊 Visual Insights & Key Findings

### 1. Advertising Features Pairplot
Clear non-linear concave growth relationship between TV advertising budget and resulting sales volume.

![Advertising Pairplot](assets/advertising_pairplot.png)

### 2. Individual Channel Scatter Dynamics
Sales display a strong positive correlation with TV spend ($r = 0.78$) and moderate correlation with Radio ($r = 0.58$), while Newspaper exhibits near-random dispersion ($r = 0.23$).

![Sales vs Media Spend](assets/sales_vs_media_spend.png)

### 3. Residual Diagnostics (Linear Model Pitfall)
Linear regression produces a distinct parabolic residual pattern, violating Gauss-Markov assumptions. Polynomial regression incorporates interaction terms and eliminates this systematic error.

![Residual Analysis](assets/residual_analysis_pattern.png)

### 4. Attribution & Channel Impact Ranking
Both standardized regression coefficients and Random Forest feature importances independently validate that TV is the primary revenue driver, followed by Radio, with Newspaper offering negligible marginal utility.

![Channel Impact Importance](assets/channel_impact_importance.png)

---

## 📈 Model Performance Comparison

| Model Architecture | Mean Absolute Error (MAE) | Root Mean Squared Error (RMSE) | $R^2$ Score (Test) | Residual Behavior |
| :--- | :---: | :---: | :---: | :--- |
| **Polynomial Regression (Degree 2)** | **0.590** | **0.723** | **0.986** | 🏆 **Optimal (Errors Random & Homoscedastic)** |
| Random Forest Regressor | 0.642 | 0.811 | 0.983 | Captures Non-linearities |
| Linear Regression (Baseline) | 1.227 | 1.785 | 0.899 | Fails to Capture Synergy ($TV \times Radio$) |

---

## 📁 Repository Structure

```text
DataScience-Task5-SalesPrediction/
├── Sales_Prediction.ipynb       # Complete interactive analysis notebook
├── Advertising.csv              # Source advertising budget dataset (ISLR)
├── README.md                    # Technical report & econometric interpretation
└── assets/                      # Generated visualization assets
    ├── advertising_pairplot.png
    ├── sales_vs_media_spend.png
    ├── correlation_heatmap.png
    ├── residual_analysis_pattern.png
    └── channel_impact_importance.png
```

---

## 🚀 How to Run

1. Keep `Advertising.csv` in the current folder.
2. Launch notebook:
   ```bash
   jupyter notebook Sales_Prediction.ipynb
   ```
