# Task 3 — Used Car Price Prediction with Machine Learning

**Program:** Oasis Infobyte Summer Internship Program (SIP) — Data Science Track  
**Author:** **Youssef Laaroussi** (Master's in Data Science & Artificial Intelligence)  
**Deliverable:** `Car_Price_Prediction.ipynb` (Google Colab & Jupyter Ready, Pre-executed)

---

## 📌 Executive Summary & Objective

Build and compare multiple machine learning regression models to predict used car market valuations based on vehicle attributes (brand, vehicle age, mileage, fuel type, transmission, seller type, and ownership history). Every design choice—from target transformation to encoding—is grounded in empirical data analysis.

---

## 🔬 Skills & Methodological Rigor

- **Production-grade free-text feature engineering:** Extracted car brand from complex raw strings, explicitly handling real-world anomalies (e.g., compound brand `"Land Rover"` and concatenated typos `"OpelCorsa"`), verified with programmatical assertions.
- **Time-aware feature derivation:** Derived `car_age` relative to dataset capture year rather than system timestamp to eliminate temporal data leakage.
- **Domain-aligned encoding strategy:** Applied ordinal encoding for inherently ordered variables (`owner`: Test Drive Car $\rightarrow$ First $\rightarrow$ Second $\rightarrow$ Third $\rightarrow$ Fourth & Above) and one-hot encoding for nominal variables (`fuel`, `seller_type`, `transmission`, `brand`).
- **Target stabilization:** Handled severe right-skew in `selling_price` (skewness $\approx 4.9$) via `log1p` transformation during training, with predictions exponentiated back to Indian Rupees (₹) before metric evaluation.
- **Multi-model regression benchmarking:** Compared Linear Regression, Random Forest Regressor, and Gradient Boosting Regressor under identical stratified splits.

---

## 📊 Visual Insights & Key Findings

### 1. Price Distribution & Log Transformation
Raw selling prices exhibit extreme positive skewness and long tails. The `np.log1p` transformation normalizes the distribution, ensuring stable gradient updates and error minimization.

![Price Distribution & Skewness](assets/price_distribution_skewness.png)

### 2. Pricing Dynamics by Fuel Type
Diesel vehicles exhibit higher median valuations and wider variance, while Petrol, CNG, and LPG cluster in lower valuation bands.

![Price vs Fuel Type](assets/price_vs_fuel_type.png)

### 3. Predictor Correlation Matrix
`car_age` shows the strongest negative correlation with selling price ($r = -0.42$), while `km_driven` has a weaker independent impact once age is controlled for.

![Correlation Heatmap](assets/features_correlation_heatmap.png)

### 4. Regression Model Performance Comparison
Tree-based ensemble models substantially outperform the linear baseline by capturing non-linear interactions between brand, transmission, and age.

![Model Evaluation Comparison](assets/models_evaluation_comparison.png)

### 5. Feature Importance of Winning Model
Vehicle age and premium brand markers (e.g., BMW, Audi, Mercedes-Benz, Toyota) dominate the predictive split criteria.

![Feature Importance](assets/car_price_feature_importance.png)

---

## 📈 Model Performance Benchmark (Evaluated in ₹)

| Model Family | Mean Absolute Error (MAE) | Root Mean Squared Error (RMSE) | $R^2$ Score | Status |
| :--- | :---: | :---: | :---: | :--- |
| **Random Forest Regressor** | **₹96,412** | **₹212,840** | **0.865** | 🏆 **Best Performer** |
| Gradient Boosting Regressor | ₹104,180 | ₹228,750 | 0.844 | Strong Gradient Ensemble |
| Linear Regression (Baseline) | ₹182,310 | ₹349,620 | 0.635 | Under-fits Non-linear Terms |

---

## 📁 Repository Structure

```text
DataScience-Task3-CarPricePrediction/
├── Car_Price_Prediction.ipynb       # Full interactive notebook with all visualizations
├── CAR DETAILS FROM CAR DEKHO.csv   # Source dataset (3,577 deduplicated records)
├── README.md                        # Technical report & documentation
└── assets/                          # High-resolution generated plots
    ├── price_distribution_skewness.png
    ├── price_vs_fuel_type.png
    ├── features_correlation_heatmap.png
    ├── models_evaluation_comparison.png
    └── car_price_feature_importance.png
```

---

## 🚀 How to Run

1. Keep `CAR DETAILS FROM CAR DEKHO.csv` in the current folder.
2. Run notebook:
   ```bash
   jupyter notebook Car_Price_Prediction.ipynb
   ```
