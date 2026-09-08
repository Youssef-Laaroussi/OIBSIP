# Task 4 — Email & SMS Spam Detection with NLP

**Program:** Oasis Infobyte Summer Internship Program (SIP) — Data Science Track  
**Author:** **Youssef Laaroussi** (Master's in Data Science & Artificial Intelligence)  
**Deliverable:** `Email_Spam_Detection.ipynb` (Google Colab & Jupyter Ready, Pre-executed)

---

## 📌 Executive Summary & Objective

Design and deploy a Natural Language Processing (NLP) classification pipeline to accurately distinguish between spam (unsolicited commercial/malicious messages) and ham (legitimate communication). The project focuses on real-world NLP text preprocessing, handling severe class imbalance, and analyzing the asymmetric trade-off between Precision and Recall in communication systems.

---

## 🔬 Skills & Methodological Rigor

- **Production NLP preprocessing pipeline:** HTML entity decoding (`html.unescape`), lowercase conversion, regex-based punctuation & digit cleaning, stopword removal, and NLTK lemmatization.
- **Corpus bug detection & resolution:** Diagnosed and eliminated corrupting HTML entity leaks (`&lt;#&gt;` placeholder leaking 576+ spurious `"lt"`/`"gt"` tokens), mathematically verifying clean vocabulary distribution before feature extraction.
- **TF-IDF feature extraction:** Vectorized text with Term Frequency–Inverse Document Frequency (TF-IDF, 3,000 max features) capturing discriminating n-grams while downweighting ubiquitous terms.
- **Class imbalance strategy:** Corrected for 87% ham / 13% spam imbalance using stratified train/test partitioning and `class_weight='balanced'` cost-sensitive learning.
- **Decision theory & metric evaluation:** Comprehensive analysis comparing False Positives (legitimate emails sent to spam) vs. False Negatives (spam entering the inbox).

---

## 📊 Visual Insights & Key Findings

### 1. Dataset Class Imbalance
The dataset contains 5,572 raw records with an 87.4% Ham vs. 12.6% Spam distribution, confirming that naive accuracy alone is a misleading metric.

![Class Distribution](assets/spam_ham_class_distribution.png)

### 2. Multi-Model Confusion Matrix Comparison
Comparing Multinomial Naive Bayes, Balanced Logistic Regression, and Balanced Linear SVM:

![Confusion Matrices Comparison](assets/models_confusion_matrices.png)

### 3. WordClouds: Spam vs. Ham Semantic Profiles
Spam messages are heavily clustered around urgency, monetary rewards, and action requests (*"call"*, *"free"*, *"claim"*, *"prize"*, *"txt"*, *"urgent"*), whereas Ham reflects authentic interpersonal communication (*"come"*, *"go"*, *"love"*, *"ok"*, *"time"*).

![WordClouds Spam vs Ham](assets/wordclouds_spam_vs_ham.png)

---

## 📈 Performance Benchmark & Trade-off Analysis

| Model Architecture | Accuracy | Spam Precision | Spam Recall | Spam F1-Score | False Positives | False Negatives |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| **Linear SVM (Balanced)** | **98.4%** | **94.0%** | **94.7%** | **0.943** | **9** | **8** |
| Logistic Regression (Balanced) | 97.6% | 89.8% | 94.0% | 0.919 | 16 | 9 |
| Multinomial Naive Bayes | 97.7% | 98.4% | 85.3% | 0.914 | 2 | 22 |

> **Applied Decision Insight:**  
> Multinomial Naive Bayes minimizes False Positives (only 2 legitimate messages misclassified), making it ideal when missing an important email is catastrophic. Conversely, Linear SVM achieves the highest overall F1-score (0.943) with an optimal balance between catching malicious threats and preserving user trust.

---

## 📁 Repository Structure

```text
DataScience-Task4-EmailSpamDetection/
├── Email_Spam_Detection.ipynb       # Complete pre-executed notebook with outputs
├── spam.csv                         # Source SMS Spam Collection dataset
├── README.md                        # Technical report & NLP documentation
└── assets/                          # Generated visualization assets
    ├── spam_ham_class_distribution.png
    ├── models_confusion_matrices.png
    └── wordclouds_spam_vs_ham.png
```

---

## 🚀 How to Run

1. Keep `spam.csv` in the local directory.
2. Run notebook:
   ```bash
   jupyter notebook Email_Spam_Detection.ipynb
   ```
