# Task 2 — Unemployment Analysis in India (Regional & COVID-19 Impact)

**Program:** Oasis Infobyte Summer Internship Program (SIP) — Data Science Track  
**Author:** **Youssef Laaroussi** (Master's in Data Science & Artificial Intelligence)  
**Deliverable:** `Unemployment_Analysis_India.ipynb` (Google Colab & Jupyter Ready, Pre-executed)

---

## 📌 Executive Summary & Objective

Explore India's state-level unemployment dynamics to uncover regional disparities and temporal trends. The core analytical focus is to **quantify and statistically validate** the macroeconomic impact of the COVID-19 nationwide lockdown (April–June 2020) rather than relying on descriptive speculation.

---

## 🔬 Skills & Methodological Rigor

- **Evidence-based analysis design:** Pre/post-COVID cutoff date derived empirically by inspecting the national monthly trend rather than assuming arbitrary calendar dates.
- **Non-parametric hypothesis testing:** Mann-Whitney U test demonstrating that the pre-vs-lockdown unemployment surge is statistically significant ($p \approx 8.8 \times 10^{-17}$).
- **Real-world data cleaning:** Diagnosed and handled leading whitespace in dates (`" 31-05-2019"`) that silently breaks standard datetime parsing.
- **Production plotting bug diagnosis:** Resolved a pandas `category`-dtype + seaborn interaction bug that caused zero-height invisible bars by implementing direct `matplotlib` horizontal bar rendering.
- **Advanced economic insights:** Evaluated Rural vs. Urban sensitivity and calculated the **"shock magnitude"** (pre-COVID vs. lockdown delta per state), uncovering critical patterns hidden by raw averages.

---

## 📊 Visual Insights & Key Findings

### 1. National Monthly Unemployment Trend (The COVID Structural Break)
National unemployment held steady in the **~9–11% band** from May 2019 to March 2020, then spiked abruptly to **23.6% in April 2020**.

![National Monthly Trend](assets/national_monthly_trend.png)

### 2. Multi-State Temporal Evolution
States experienced divergent recovery trajectories; highly urbanized territories suffered sharper disruptions.

![Major States Trend](assets/major_states_trend.png)

### 3. Top 10 States by Average Unemployment Rate
Tripura (28.4%) and Haryana (26.3%) registered the highest baseline unemployment over the entire recording window.

![Top 10 States](assets/top10_unemployment_states.png)

### 4. Correlation Between Macroeconomic Indicators
Correlation matrix confirming the negative relationship between Estimated Unemployment Rate and Labour Participation Rate ($r = -0.07$) and Employment Rate.

![Correlation Heatmap](assets/indicators_correlation_heatmap.png)

### 5. Pre-COVID vs. Lockdown Comparison & Shock Magnitude
While Tripura had the highest overall average, **Puducherry suffered the largest COVID shock**, skyrocketing from **1.6% pre-COVID to 57.7% during lockdown** (+56.1 percentage points).

![Pre-COVID vs Lockdown Metrics](assets/precovid_vs_lockdown_metrics.png)

---

## 📈 Statistical Hypothesis Testing Results

| Period | Sample Size ($N$) | Mean Unemployment Rate (%) | Median (%) | Mann-Whitney U Statistic | p-value | Significance |
| :--- | :---: | :---: | :---: | :---: | :---: | :--- |
| **Pre-COVID** (May 2019 – Mar 2020) | 588 | 10.37% | 8.83% | — | — | Baseline |
| **Lockdown** (Apr 2020 – Jun 2020) | 152 | 22.84% | 18.15% | $U = 22105.5$ | **$p = 8.78 \times 10^{-17}$** | **Statistically Significant ($p < 0.001$)** |

---

## 📁 Repository Structure

```text
DataScience-Task2-UnemploymentAnalysis/
├── Unemployment_Analysis_India.ipynb   # Full analysis notebook with all visualizations
├── Unemployment in India.csv           # Source dataset (740 records, clean naming)
├── README.md                           # Technical report & economic analysis
└── assets/                             # Visual assets
    ├── national_monthly_trend.png
    ├── major_states_trend.png
    ├── top10_unemployment_states.png
    ├── indicators_correlation_heatmap.png
    └── precovid_vs_lockdown_metrics.png
```

---

## 🚀 How to Run

1. Ensure `Unemployment in India.csv` is located in this directory.
2. Launch with Jupyter:
   ```bash
   jupyter notebook Unemployment_Analysis_India.ipynb
   ```
