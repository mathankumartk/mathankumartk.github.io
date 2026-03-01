# Anomaly Detection in Credit Card Transactions: Leveraging Machine Learning for Fraud Classification

A supervised binary classification project that detects and classifies fraudulent credit card transactions using Logistic Regression, Random Forest, and XGBoost applied to a synthetic dataset of 10,000 transactions. The project addresses the growing challenge of financial fraud by leveraging behavioral and transactional features to move beyond traditional rule-based detection.

---

## Business Problem

Traditional rule-based fraud detectors frequently fall behind increasingly sophisticated scams — producing false positives that block legitimate transactions while still missing real fraud. This project builds a machine learning classifier to distinguish fraudulent from legitimate activity more accurately using behavioral and transactional signals.

**The scale of the problem:**
- Global payment card fraud losses reached **$33.41 billion in 2024**, projected to reach **$49.13 billion by 2034**
- The U.S. represents only 26.31% of global transaction volume but bears **41.87% of global fraud losses**
- The FTC received over **458,000 credit card fraud reports** from U.S. consumers in 2024 alone
- Cardholders aged 60–69 reported the **highest dollar losses, exceeding $1.1 billion**
- Each dollar lost to fraud costs merchants a total of **$3.75** when accounting for chargebacks, investigation, and operational overhead

**Core research questions:**
- Which transactional and behavioral features most strongly predict fraud, and how do they interact?
- How do Logistic Regression, Random Forest, and XGBoost compare in detection accuracy?
- Do high-risk indicators (1 AM–5 AM transactions, foreign transactions, location mismatches) amplify fraud risk?
- Do cardholder demographics (age, senior status) help identify groups more frequently targeted?

---

## Dataset

- **Source:** [Kaggle — Credit Card Fraud Detection Dataset](https://www.kaggle.com/datasets/miadul/credit-card-fraud-detection-dataset/data)
- **Type:** Synthetic credit card transaction dataset designed for fraud detection research
- **Size:** 10,000 transaction records, 10 features
- **Class Distribution:** 9,849 legitimate (98.5%) vs. 151 fraudulent (1.5%) — severe imbalance

### Target Variable
**`is_fraud`** — binary: 0 = Legitimate, 1 = Fraudulent

### Key Features

| Feature | Description |
|---------|-------------|
| `amount` | Transaction value in USD ($0.00–$1,471.04, mean $175.95) |
| `transaction_hour` | Hour of day (0–23); used to engineer high-risk time window |
| `merchant_category` | One of 5 types: Electronics, Travel, Grocery, Food, Clothing |
| `foreign_transaction` | Binary — 1 if transaction occurred in a foreign country |
| `location_mismatch` | Binary — 1 if location doesn't match cardholder's registered address |
| `device_trust_score` | Numerical (1–100); lower scores indicate higher device risk |
| `velocity_last_24h` | Number of transactions by cardholder in the past 24 hours |
| `cardholder_age` | Age in years; used to engineer senior citizen indicator |
| `transaction_id` | Unique identifier — dropped during preprocessing (no predictive value) |

---

## Data Preprocessing

**Data Validation:**
- Confirmed 10,000 records across 10 features with no missing values and no duplicate rows

**Feature Removal:**
- `transaction_id` dropped — serves only as a row identifier with no predictive value

**Encoding:**
- **One-hot encoding:** `merchant_category` (5 categories → 5 binary columns); original column retained for EDA

**Feature Engineering:**
- `transaction_hour_risk_indicator` — flags transactions between 1 AM and 5 AM as high risk (1), all other hours as low risk (0)
- `cardholder_senior_citizen` — flags cardholders aged 65+ (1) to examine demographic targeting patterns

**Feature Scaling:**
- `StandardScaler` applied to `amount`, `device_trust_score`, `cardholder_age`, and `velocity_last_24h`
- Scaled columns created alongside originals to preserve EDA interpretability

**Class Balancing:**
- **SMOTE** applied exclusively within the training pipeline on a **70/30 train-test split** (`random_state=42`)
- Achieved balanced 50/50 class distribution in training set with no data leakage into the test set

---

## Methods

### Models Evaluated

| Model | Role | Key Configuration |
|-------|------|------------------|
| **Logistic Regression** | Linear baseline | StandardScaler pipeline, max_iter=200 |
| **XGBoost Gradient Boosting** | Advanced ensemble | Sequential boosting, logloss evaluation metric |
| **Random Forest + SMOTE** | Bagging ensemble | `class_weight='balanced'` + SMOTE (double imbalance correction) |

### Hyperparameter Optimization (XGBoost — GridSearchCV)

Parameters tuned via `GridSearchCV` with `StratifiedKFold`, optimizing cross-validated F1-score:

| Hyperparameter | Description |
|----------------|-------------|
| `n_estimators` | Number of boosting rounds |
| `learning_rate` | Step size shrinkage |
| `max_depth` | Maximum tree depth |
| `subsample` | Fraction of samples per tree |
| `colsample_bytree` | Fraction of features per tree |
| `min_child_weight` | Minimum sum of instance weight in a child |
| `gamma` | Minimum loss reduction for further partition |

**Post-tuning results: F1 ≈ 0.9974, Accuracy ≈ 0.9975**

### Evaluation Framework
Given the cost asymmetry in fraud detection — where a missed fraud far outweighs a false alarm — **Recall and F1-Score were prioritized** as primary metrics over Accuracy alone.

---

## Key Findings

### Model Performance Comparison

| Model | Accuracy | Precision | Recall | F1-Score |
|-------|----------|-----------|--------|----------|
| Random Baseline | ~50% | — | — | — |
| Logistic Regression | ~96.43% | — | — | ~96.34% |
| **XGBoost (Best)** | **99.63%** | **99.52%** | **99.72%** | **99.62%** |
| XGBoost (Tuned) | **99.75%** | — | — | **99.74%** |

XGBoost achieved the best confusion matrix results with the fewest false positives and false negatives of all models tested.

### Strongest Fraud Predictors
- **`device_trust_score`** — lower trust scores concentrated in fraudulent transactions
- **`location_mismatch`** — strong fraud signal; compounds with `foreign_transaction`
- **`foreign_transaction`** — elevated fraud rate vs. domestic transactions
- **`velocity_last_24h`** — unusual spending velocity is a key behavioral signal
- **`transaction_hour_risk_indicator`** — transactions between 1 AM–5 AM show elevated fraud rates
- **`cardholder_senior_citizen`** — senior cardholders (65+) show demographic vulnerability patterns

### EDA Insights (9 Visualizations)
- **Device Trust Score KDE** — lower trust scores concentrated among fraudulent transactions
- **Cardholder Age KDE** — senior citizen region (65+) highlighted with fraud rate summary
- **Transaction Amount Box Plot** — spread, medians, and outliers compared by fraud status
- **Fraud Rate by Hour** — 1 AM–5 AM window shows elevated rates vs. daytime average
- **Fraud Rate by Merchant Category** — identifies highest-risk merchant types
- **Fraud Rate by Foreign Transaction × Location Mismatch** — compound risk assessment
- **Correlation Heatmap** — pairwise correlations across all features vs. `is_fraud`
- **Amount vs. Device Trust Score Scatter** — fraud clusters in high-amount, low-trust quadrant
- **Class Distribution** — baseline visualization of the 98.5%/1.5% imbalance

---

## Tools & Technologies

| Tool / Library | Purpose |
|----------------|---------|
| **Python** | Primary programming language |
| **Pandas & NumPy** | Data manipulation, cleaning, and feature engineering |
| **Matplotlib & Seaborn** | EDA visualizations (KDE plots, box plots, heatmaps, scatter plots, bar charts) |
| **Scikit-learn** | Logistic Regression, Random Forest, StandardScaler, GridSearchCV, StratifiedKFold, evaluation metrics |
| **XGBoost** | Gradient boosting classifier with logloss optimization |
| **SMOTE (imbalanced-learn)** | Synthetic minority oversampling within training pipeline |

---

## Implementation Roadmap

| Phase | Duration | Activities |
|-------|----------|-----------|
| **Phase 1 — Model Finalization & Validation** | 1–3 months | Finalize XGBoost with tuned hyperparameters; retrain on full preprocessed dataset with stratified sampling |
| **Phase 2 — Interpretability & Compliance** | 1–2 months | Integrate SHAP or LIME for feature importance rankings and individual fraud decision explanations |
| **Phase 3 — System Integration & Pilot** | 3–6 months | Integrate into live transaction processing pipelines; establish continuous monitoring for model drift |
| **Phase 4 — Monitoring & Scaling** | Ongoing | Regular retraining with new transaction data; expand to insurance claims, loans, and digital wallet fraud |

---

## Ethical Considerations

- **Algorithmic & Demographic Bias:** Features like `cardholder_age`, `foreign_transaction`, and `location_mismatch` risk disproportionately flagging legitimate transactions from senior citizens or frequent travelers; fraud decisions must be based on genuine signals, not demographic proxies
- **False Positives & Customer Impact:** Optimizing for recall can generate excessive false positives — declined transactions and frozen accounts for legitimate cardholders; the precision-recall tradeoff is an ethical concern, not just a modeling one
- **Transparency & Explainability:** Black-box ensembles (XGBoost, Random Forest) are difficult to interpret; financial institutions are increasingly obligated to provide explainable and auditable fraud decisions
- **Surveillance & Profiling:** Behavioral features (velocity, device trust scores, location data) raise concerns about customer profiling without explicit consent; the boundary between fraud prevention and invasive surveillance must be carefully managed

---

## Limitations

- The synthetic dataset may not fully capture the complexity, noise, and evolving tactics of real-world fraud, limiting generalizability to live production environments
- Severe class imbalance (1.5% fraud) is a persistent challenge; SMOTE-generated samples may introduce noise not representative of genuine fraudulent behavior
- Black-box ensemble models limit interpretability, making transparent fraud flagging difficult — a critical requirement in regulated financial environments
- Models trained on this dataset may not adapt well to new fraud patterns that emerge after the training period

---

## Assumptions

- The synthetic dataset accurately reflects the behavioral and transactional patterns of real-world credit card fraud
- SMOTE-generated synthetic samples adequately represent the minority fraud class
- The class distribution in the test set accurately reflects real-world imbalance
- Relationships learned during training remain stable and applicable to unseen transaction data

---

## Future Work

- **Real-Time Fraud Detection:** Integrate trained models into live transaction processing pipelines (streaming architecture) to intercept fraudulent transactions before completion
- **Personalized Risk Scoring:** Incorporate spending history, device fingerprinting, and geographic patterns to generate dynamic, cardholder-specific fraud risk scores
- **Broader Anomaly Detection:** Extend feature engineering techniques to insurance claims, loan applications, and digital wallet transactions
- **Enhanced Feature Space:** Add social media activity, merchant reputation scores, and network-based transaction relationships
- **Continuous Retraining:** Regularly update models with new transaction data to stay responsive to evolving fraud tactics

---

## References

- Miah, A. (2025). *Credit Card Fraud Detection Dataset*. Kaggle. https://www.kaggle.com/datasets/miadul/credit-card-fraud-detection-dataset/data
- The Nilson Report. (2026, January 7). *Global Card Fraud Losses at $33 Billion*. GlobeNewswire. https://www.globenewswire.com/news-release/2026/01/07/3214821/0/en/Global-Card-Fraud-Losses-at-33-Billion.html
- Islam, M. A., Uddin, M. A., Aryal, S., & Stea, G. (2023). An ensemble learning approach for anomaly detection in credit card data with imbalanced and overlapped classes. *Journal of Information Security and Applications*, 78, 103618. https://doi.org/10.1016/j.jisa.2023.103618
- *Fairness and Machine Learning*. (n.d.). fairmlbook.org. https://fairmlbook.org
