# Harnessing Predictive Analytics in Real Estate: Housing Price Prediction Using Machine Learning

## Project Overview

This project develops a machine learning pipeline to predict the sale prices of residential properties by analyzing various features and characteristics that influence housing markets. Using the Advance House Price Predictions dataset from Kaggle, the study applies comprehensive data preprocessing, exploratory data analysis, feature engineering, and multi-model regression evaluation — providing actionable insights for buyers, sellers, lenders, and real estate professionals to make informed, data-driven decisions.

---

## Problem Statement

Accurate housing price prediction is a critical challenge in real estate. Buyers risk overpaying without reliable market valuation tools, while sellers may under- or over-price properties, impacting both returns and time-on-market. This project addresses that gap by building regression models that estimate residential sale prices based on property attributes, enabling:

- **Home Buyers** — trustworthy information for smart purchase decisions and effective negotiation
- **Home Sellers** — data-driven pricing to attract buyers and maximize ROI
- **Mortgage Lenders** — accurate property valuations for loan assessment and risk management
- **Appraisers & Market Researchers** — reliable tools for trend analysis and market evaluation
- **Government Agencies** — insights supporting city planning, housing policy, and economic strategy

---

## Dataset

- **Source:** Kaggle — [Advance House Price Predictions](https://www.kaggle.com/datasets/zeeshanmulla/advance-house-price-predicitons/data)
- **Files:** `train.csv` (training set), `test.csv` (test set)
- **Target Variable:** `SalePrice` — Residential property sale price in USD

### Key Features Retained for Modeling

| Feature | Description |
|---|---|
| `GrLivArea` | Above-grade (ground) living area in square feet — strongest predictor of sale price |
| `LotArea` | Total lot size in square feet |
| `OverallCond` | Overall condition rating of the house |
| `KitchenQual` | Kitchen quality (Excellent, Good, Average, Fair, Poor) |
| `BedroomAbvGr` | Number of bedrooms above ground level |
| `GarageCars` | Garage capacity in number of cars |
| `BsmtExposure` | Basement exposure level |
| `BsmtFinType1` | Basement finish type |
| `CentralAir` | Central air conditioning (Y/N) |
| `SalePrice` | Target variable — sale price in USD |

---

## Methodology

### 1. Data Loading & Initial Assessment
- Loaded training and test datasets into pandas DataFrames
- Assessed column types, distributions, and missing value counts
- Confirmed data quality: majority of key features had no missing values

### 2. Data Preparation

**Columns Dropped** (non-essential or redundant):
- `Id`, `MSSubClass`, `MSZoning`, `LotFrontage`, `Street`, `Alley`, `LotShape`, `Utilities`, `LotConfig`
- Secondary dimension columns (e.g., `Exterior2nd` — primary exterior feature already captured)
- Condition-state columns (e.g., `BsmtCond`, `FloorCond`) — quality columns preferred for modeling
- Non-essential features (e.g., `SaleCondition`, `ScreenPorch`, `RoofStyle`)

**Missing Value Handling:**
- `BsmtExposure` and `BsmtFinType1` NaN values → replaced with `"No Basement"` (not ordinal)
- `MiscFeature` NaN values → replaced with `"No Misc Feature"`
- Rows with NaN in `BsmtCond` and `BsmtFinType1` → dropped for Linear Regression and XGBoost models (low count, homes without basements)

**Categorical Encoding:**
- **Binary Encoding:** `CentralAir` (Y → 1, N → 0)
- **Ordinal Encoding:** Quality and condition features with natural ordering — `KitchenQual`, `ExterQual`, `HeatingQC`, and others mapped to numeric scale (Excellent=5, Good=4, Average=3, Fair=2, Poor=1)
- **Ordinal Encoding (Basement):** `BsmtFinType1` mapped from GLQ (6) to Unfin (1)
- **One-Hot Encoding:** All remaining non-ordinal categorical features including `LandContour`, `LandSlope`, `BldgType`, `HouseStyle`, `Foundation`, `Functional`, `MiscFeature`

### 3. Exploratory Data Analysis & Visualizations

| Visualization | Type | Key Insight |
|---|---|---|
| GrLivArea vs SalePrice | Scatter Plot | Strong positive correlation — larger homes sell for higher prices |
| LotArea & SalePrice Distribution | Histogram + KDE | Both distributions are right-skewed; most homes concentrated in lower price/area ranges |
| SalePrice by GarageCars | Box Plot | Clear upward price trend with increasing garage capacity; 2-car garages ≈ $200K median |
| SalePrice by KitchenQual | Box Plot | Higher kitchen quality strongly associated with higher and more variable sale prices |
| Correlation Heatmap | Heatmap | GrLivArea has the strongest positive correlation with SalePrice; OverallCond has near-zero correlation |
| SalePrice KDE | KDE Plot | Right-skewed distribution with peak density ≈ $180,000; few homes above $300,000 |
| SalePrice by OverallCond | KDE Plot | Homes with Overall Condition 5 show the highest density around $200,000 |

**Key Correlation Findings:**
- `GrLivArea` (ground living area) → very strong positive correlation with `SalePrice`
- `BedroomAbvGr` → moderate positive correlation
- `OverallCond` → very weak negative correlation (minimal impact on price)
- `LotArea` → weak positive correlation

### 4. Model Building & Evaluation

Three regression models were built and compared using an 80/20 train-validation split (`random_state=42`):

| Model | MAE (USD) | MSE | RMSE (USD) |
|---|---|---|---|
| **Random Forest** | **17,735.98** | **812,567,500** | **28,505.57** |
| XGBoost | 19,696.98 | 958,456,500 | 30,958.95 |
| Linear Regression | 24,005.45 | 1,604,650,000 | 40,058.08 |

**Best Model: Random Forest Regressor**
- Lowest MAE, MSE, and RMSE across all three metrics
- On average, predictions deviate from actual sale prices by approximately $17,736 — the most accurate of all models tested
- Both XGBoost and Linear Regression showed higher error, with Linear Regression's RMSE of ~$40,058 suggesting significant room for improvement through feature enrichment

---

## Key Findings

- **Ground living area (`GrLivArea`)** is the single strongest predictor of sale price — larger homes consistently command higher prices
- **Garage capacity** significantly impacts price — moving from 0 to 2 garage cars is associated with approximately double the median sale price (~$100K to ~$200K)
- **Kitchen quality** shows a clear upward price trend — excellent kitchen homes show both higher median prices and greater variability, indicating premium buyer demand
- **Overall condition** alone is a weak predictor of sale price — buyers appear to value features and space over condition ratings
- **SalePrice distribution** is right-skewed with a mean of ~$180,921 — the majority of homes sold in the $130K–$215K range
- **Random Forest outperforms** both XGBoost and Linear Regression on all three error metrics, making it the recommended model for deployment

---

## Tools & Technologies

| Tool / Library | Purpose |
|---|---|
| **Python** | Primary programming language |
| **Pandas & NumPy** | Data manipulation, cleaning, and feature engineering |
| **Matplotlib & Seaborn** | EDA visualizations (scatter plots, histograms, box plots, KDE plots, heatmaps) |
| **Scikit-learn** | Train-test splitting, encoding, Random Forest Regressor, Linear Regression, evaluation metrics |
| **XGBoost** | Gradient boosting regression model |
| **RandomForestRegressor** | Best performing model — ensemble of decision trees |
| **LinearRegression** | Baseline regression model |

---

## Risk Assessment & Mitigations

| Risk | Mitigation |
|---|---|
| **Data Quality** — incomplete or inaccurate data degrades model performance | Thorough data cleaning and preprocessing pipeline |
| **Overfitting** — complex models may not generalize to new data | Cross-validation and regularization techniques |
| **High Dimensionality** — SVM and high-feature datasets slow training | Dimensionality reduction (PCA) if needed |
| **Model Bias** — certain features may drive biased predictions | Validate dataset balance and evaluate for feature bias |
| **Market Change** — rapid market shifts reduce model relevance | Regular retraining with updated sales data |
| **External Factors** — interest rates and economic indicators affect prices | Consider adding macroeconomic features to future model versions |

---

## Limitations

- The current Random Forest model shows high MSE (~812M), indicating that while it outperforms alternatives, prediction accuracy on high-value or outlier properties still has room for improvement
- Hyperparameter tuning (GridSearchCV, cross-validation) was identified but not applied in this version — applying it is expected to meaningfully improve model performance
- The dataset reflects a specific geographic market (Ames, Iowa) and may not generalize to other housing markets without retraining
- External economic factors such as interest rates and inflation are not included in the feature set

---

## Recommendations

- **Feature Engineering:** Explore interaction terms between key features (e.g., `GrLivArea × OverallQual`) and polynomial transformations to capture non-linear relationships
- **Model Optimization:** Apply hyperparameter tuning (GridSearchCV with k-fold cross-validation) to Random Forest and XGBoost to further reduce MAE and RMSE
- **Market Research:** Incorporate neighborhood-level and geographic variables to capture location-based price dynamics
- **Continuous Evaluation:** Establish a retraining framework that integrates new sales data regularly to keep the model aligned with current market conditions
- **Outlier Management:** Investigate and handle high-value outliers more carefully to reduce MSE for luxury property predictions