# Assessing Loan Default Risks: Predicting Borrower Behavior Using Machine Learning

## Project Overview

This project develops a comprehensive machine learning pipeline to predict the likelihood of loan defaults based on borrower characteristics and loan attributes. Using a dataset of approximately 148,000 mortgage loan records sourced from Kaggle, the study applies extensive data preprocessing, exploratory data analysis, feature engineering, and multi-model evaluation to identify the most reliable classifier for predicting loan default status — ultimately equipping financial institutions with the insights needed to make informed, risk-aware lending decisions.

---

## Problem Statement

Loan defaults pose a significant financial risk to lending institutions. Traditional credit assessment approaches — relying primarily on credit scores — often fail to capture the full spectrum of factors influencing repayment behavior. This project addresses that gap by building a predictive binary classification model that distinguishes between loans likely to default (1) and those that will not (0), enabling lenders to:

- Identify high-risk borrowers before loan approval
- Tailor lending terms and risk mitigation strategies
- Reduce financial losses and improve portfolio quality
- Streamline and improve the efficiency of the loan approval process

---

## Dataset

- **Source:** Kaggle — [Mortgage Loan Default - Data Preprocessing](https://www.kaggle.com)
- **File:** `Loan_Default.csv`
- **Size:** ~148,000 records, 34 columns (33 features + 1 target variable)
- **Target Variable:** `Status` — Binary classification (1 = Default, 0 = No Default)

### Key Features

| Feature | Description |
|---|---|
| `Credit_Score` | Borrower's creditworthiness score |
| `rate_of_interest` | Loan interest rate — higher rates may increase default risk |
| `approv_in_adv` | Pre-approval status — indicates initial creditworthiness assessment |
| `loan_amount` | Total loan amount — larger amounts associated with higher default risk |
| `loan_purpose` | Purpose of the loan (home purchase, improvement, refinancing, other) |
| `Gender` | Borrower gender / applicant type (individual, joint) |
| `Income` | Borrower income level |
| `term` | Loan repayment term |
| `property_value` | Estimated property value |
| `Status` | Target variable — 1 = Default, 0 = No Default |

---

## Methodology

### Exploratory Data Analysis

Five key research questions were investigated through visualization:

1. **Gender & Default Rates:** Joint applicants exhibit the lowest default rates, suggesting the importance of exploring demographic factors such as marital status and dependents
2. **Credit Score Distribution:** Similar credit score distributions among defaulting and non-defaulting borrowers indicate that credit scores alone do not fully predict default risk
3. **Interest Rate Influence:** Defaulted loans have slightly higher median interest rates; non-defaulting loans contain high-interest outliers requiring careful management
4. **Loan Amount Distribution:** Default cases show greater variability and higher median loan amounts — larger loans carry higher default risk, recommending tighter criteria for high-value lending
5. **Pre-Approval Status:** Loans with pre-approval show significantly lower default rates, confirming a strong correlation between pre-approval and reduced default risk

### Data Preparation

**Features Dropped (non-predictive or irrelevant):**
- `ID` — unique identifier with no predictive value
- `year` — single value (2019) across all records
- `submission_of_application` — no interpretable definition
- `dtir1` — no context or definition available
- `construction_type` — only 33 records for `"mh"` category (~0.02% of data)
- `Secured_by` — only 33 records for `"land"` category

**Feature Engineering:**
- **Interest Category:** Binned `rate_of_interest` into 0.5% intervals (0–8%) for risk segmentation
- **Loan Type / Purpose / Occupancy Descriptions:** Mapped coded values to descriptive labels using CFPB reference documentation
- **Monthly EMI:** Calculated equated monthly installment from loan amount, interest rate, and term
- **Loan Amount Risk:** Categorized loans as `"high"` (> $499,999) or `"low"` risk based on loan amount

**Missing Value Strategy:**

| Approach | Columns | Rationale |
|---|---|---|
| Fill with `"unknown"` | Loan Limit, Pre-Approval, Age, Negative Amortization | Avoids skewed model interpretation of categorical variables |
| Fill with mode | Loan Purpose | Preserves overall data distribution |
| Fill with mean | Rate of Interest, Interest Rate Spread, Income | Retains central tendency for normally distributed fields |
| Drop rows | Term, Property Value | Essential features — missing values would degrade model quality |

**Encoding:**
- Created dummy variables using `pd.get_dummies()` for all categorical features including Gender, Pre-Approval, Loan Type, Loan Purpose, Occupancy Type, Credit Type, and more

### Additional Cleaning & Full Encoding

- Dropped remaining code-based columns replaced by description equivalents (`loan_type`, `loan_purpose`, `occupancy_type`, `loan_limit`, `interest_category`)
- Applied full one-hot encoding across all remaining categorical variables
- Treated `Age` and `Total Units` as categorical due to their discrete, non-continuous nature

### Model Building, Evaluation & Overfitting Check

**Train/Test Split:** Standard split with `random_state=42`

**Models Evaluated:**

| Model | Accuracy | Precision | Recall | F1 Score |
|---|---|---|---|---|
| Linear Regression | ~22.1% R² | — | — | — |
| K-Nearest Neighbors (pipeline) | 0.886 | — | — | — |
| KNN (GridSearchCV, n=7) | 0.888 | — | — | — |
| Logistic Regression | 0.889 | 0.884 | 0.889 | 0.886 |
| K-Nearest Neighbors | 0.870 | 0.857 | 0.870 | 0.860 |
| Decision Tree | 0.999 | 0.999 | 0.999 | 0.999 |
| **Random Forest** | **1.000** | **1.000** | **1.000** | **1.000** |

**Best Model: Random Forest Classifier**
- Achieved perfect scores across all metrics (Accuracy, Precision, Recall, F1 = 1.000)
- Overfitting assessment confirmed: training accuracy (1.000) = test accuracy (1.000), confirming the model generalizes well to unseen data and overfitting is not present

---

## Key Findings

- **Random Forest** is the best-performing model, achieving 100% accuracy on both training and test sets with no signs of overfitting
- **Pre-approval status** is one of the strongest indicators of loan repayment reliability
- **Loan amount** is positively correlated with default risk — larger loans are more likely to default
- **Joint applicants** show the lowest default rates across all gender/applicant categories
- **Credit score alone** is insufficient as a default predictor — a multi-feature approach significantly improves classification accuracy
- **Interest rate** shows a modest positive relationship with default — loans with slightly higher rates are marginally more likely to default

---

## Tools & Technologies

| Tool / Library | Purpose |
|---|---|
| **Python** | Primary programming language |
| **Pandas & NumPy** | Data manipulation and feature engineering |
| **Matplotlib & Seaborn** | EDA visualizations (bar charts, box plots, violin plots) |
| **Scikit-learn** | Model building, pipelines, GridSearchCV, evaluation metrics |
| **RandomForestClassifier** | Best performing classification model |
| **KNeighborsClassifier** | Secondary model with pipeline and hyperparameter tuning |
| **LogisticRegression** | Linear baseline classifier |
| **DecisionTreeClassifier** | Tree-based comparison model |
| **LinearRegression** | Initial regression baseline (poor performance) |

---

## Limitations

- The Random Forest's perfect accuracy warrants monitoring in production — while overfitting was not detected on the current test set, performance on a larger and more diverse real-world dataset should be validated
- Missing values in key features (Term, Property Value) required row deletion, potentially introducing selection bias
- The dataset is drawn from a single year (2019) and may not capture temporal shifts in borrower behavior
- As the dataset grows, Random Forest training time and computational cost will increase significantly — the model is also sensitive to parameter and distributional shifts

---

## Recommendations

- **Continuous Monitoring:** Regularly evaluate model performance against new loan data to maintain prediction accuracy
- **Feedback Loop:** Implement a feedback mechanism to capture actual loan outcomes and retrain the model periodically
- **Retraining Pipeline:** Establish an automated retraining mechanism as new data accumulates to keep the model aligned with current market trends
- **Explore Alternatives:** As the dataset grows, consider Gradient Boosting or XGBoost models which may offer comparable accuracy with better scalability
