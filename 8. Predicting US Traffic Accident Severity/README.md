# Predicting Severity of US Car Accidents — A Machine Learning Approach

A supervised machine learning project that classifies the severity of U.S. traffic accidents using a dataset of 7.7 million records, enabling auto insurers, public safety agencies, and transportation departments to shift from reactive response to proactive prevention and resource optimization.

---

## Business Problem

Auto insurance companies, public safety agencies, and state transportation departments face growing challenges from severe traffic accidents — increasing claims, operational disruptions, and budget constraints. Existing practices for assessing risk and allocating resources are primarily reactive and rule-based, limiting their ability to predict and mitigate impact before accidents occur.

In **2024**, early NHTSA estimates indicate **39,345 lives were lost** in traffic accidents, representing an economic loss exceeding **$340 billion annually** in medical expenses, lost productivity, property damage, and emergency services. This project addresses the core challenge of moving from reactive response to proactive, data-driven prevention.

---

## Dataset

- **Source:** [Kaggle — US Accidents (2016–2023)](https://www.kaggle.com/datasets/sobhanmoosavi/us-accidents)
- **Size:** ~7.7 million unique car accident records, 46 features each
- **Coverage:** February 2016 – March 2023 across 49 U.S. states (Alaska excluded)
- **Data Sources:** U.S. and state transportation departments, law enforcement, traffic cameras, road sensors

### Target Variable
**Severity** — ordinal scale from 1 (least severe) to 4 (most severe), representing the impact of an accident on traffic disruption.

### Feature Groups

| Group | Examples |
|-------|---------|
| **Temporal** | Start/end time, sunrise/sunset, civil/nautical/astronomical twilight, year, month, hour, weekday, is_weekend |
| **Locational** | City, county, state, time zone |
| **Environmental** | Temperature, wind chill, humidity, pressure, visibility, wind speed, precipitation, weather condition |
| **Infrastructural** | Binary indicators for amenity, bump, crossing, junction, roundabout, traffic signal, railway, stop, station |
| **Descriptive** | Free-text accident narrative (used for feature extraction only) |

---

## Data Preprocessing

A systematic preprocessing pipeline was applied to ensure data integrity and model readiness:

**Missing Value Handling:**
- Critical columns (`Description`, `City`, `Weather_Condition`, `Sunrise_Sunset`, twilight fields, temperature) → rows with NaN values deleted
- Continuous features (`Humidity`, `Pressure`, `Visibility`, `Wind_Direction`, `Wind_Speed`, `Precipitation`) → interpolation used to preserve records
- `Wind_Chill` → estimated using a scientific formula for missing values
- All remaining NaN rows removed after imputation

**Encoding:**
- **Binary encoding:** Boolean infrastructure features (`Amenity`, `Bump`, `Traffic_Signal`, etc.)
- **Ordinal encoding:** `Sunrise_Sunset` and twilight conditions (natural ordering preserved)
- **One-hot encoding:** `TimeZone` and `Weather_Group`
- **Binning:** Continuous features grouped into range categories; `Weather_Condition` consolidated into broader groups

**Feature Engineering:**
- Column names standardized to uppercase with underscores
- Timestamps converted to proper formats
- New features derived from `Start_Time` and `End_Time`: `Year`, `Month`, `Day`, `Hour`, `Weekday`, `Is_Weekend`
- Non-predictive columns dropped for a focused numerical feature set

---

## Methods

### Models Evaluated

Three classification models were trained and compared — first on the **imbalanced** dataset, then after applying **class balancing** techniques.

#### Imbalanced Dataset Results

| Model | Accuracy | Precision | Recall | F1-Score |
|-------|----------|-----------|--------|----------|
| Logistic Regression | 79.67% | 72.99% | 79.67% | 73.16% |
| Random Forest | 79.93% | 74.33% | 79.93% | 75.03% |
| **Gradient Boosting** | **80.97%** | **77.00%** | **80.97%** | **74.67%** |

#### After Class Balancing (SMOTE / Stratified Sampling)

| Model | Accuracy | Precision | Recall | F1-Score |
|-------|----------|-----------|--------|----------|
| Logistic Regression | 66.52% | 65.53% | 66.52% | 65.68% |
| **Random Forest** | **93.51%** | **93.51%** | **93.51%** | **93.51%** |
| Gradient Boosting | 76.71% | 76.40% | 76.71% | — |

**Best Model: Random Forest (after class balancing)** — achieved 93.51% accuracy with strong class-level recall across all severity levels.

### Hyperparameter Tuning (Random Forest)

Both Grid Search and Random Search were applied to optimize the Random Forest:

| Method | Best Parameters | Best Score |
|--------|----------------|------------|
| Grid Search (12 fits, 4 candidates) | criterion=gini, max_depth=10, max_features=sqrt, n_estimators=50 | ~0.807 |
| **Random Search (200 fits, 40 candidates)** | n_estimators=300, max_features=sqrt, max_depth=20, criterion=gini | **~0.809** |

---

## Key Findings

**Highest Positive Correlations with Severity:**
- `DISTANCE_RANGE_CODE` (+0.0568) — longer traffic disruption distances linked to higher severity
- `WEATHER_RAIN` (+0.0484) — rain conditions associated with more severe accidents
- `JUNCTION` (+0.0440) — proximity to junctions increases severity risk

**Notable Negative Correlations with Severity:**
- `END_YEAR` / `START_YEAR` (−0.2303) — more recent accidents trend toward lower severity ratings, possibly reflecting improved reporting or safety measures
- `CROSSING` (−0.1045) and `TRAFFIC_SIGNAL` (−0.1023) — controlled environments associated with reduced severity

**Geographic Insights:**
- California accounted for 22.53% of total accidents nationally
- Florida and California experienced the highest accident volumes overall
- Severity 2 dominated at ~80% of records; Severity 4 represented fewer than 3%
- A notable spike in severe accidents was observed in 2022, suggesting changes in either incident frequency or reporting practices

---

## Tools & Technologies

| Tool / Library | Purpose |
|----------------|---------|
| **Python** | Primary programming language |
| **Pandas & NumPy** | Data manipulation, cleaning, and feature engineering |
| **Matplotlib & Seaborn** | EDA visualizations (density plots, bar charts, correlation heatmaps) |
| **Scikit-learn** | Logistic Regression, Random Forest, Gradient Boosting, GridSearchCV, evaluation metrics |
| **SMOTE** | Synthetic oversampling for class balancing |

---

## Implementation Roadmap

| Phase | Duration | Activities |
|-------|----------|-----------|
| **Phase 1 — Model Finalization & Validation** | 1–3 months | Retrain top model on full preprocessed dataset with class weighting/stratified sampling |
| **Phase 2 — Interpretability & Compliance** | 1–2 months | Integrate SHAP or LIME for feature importance and prediction explanations |
| **Phase 3 — System Integration & Pilot** | 3–6 months | Deploy to transportation systems; establish real-time inference pipelines |
| **Phase 4 — Monitoring & Scaling** | Ongoing | Track model drift, prediction accuracy, and business impact; retrain with post-2023 data |

---

## Ethical Considerations

- **Data Privacy:** No explicit personal identifiers present; location data aggregated or coarsened in public results; free-text descriptions used only for feature extraction
- **Bias:** Historical reporting practices may skew severity scoring by geography or socioeconomics; fairness assessments conducted across states and urban/rural divides with bias documentation
- **Misuse Prevention:** Outputs reflect statistical patterns only and require human oversight — not to be used to deny insurance claims, assign victim blame, or reduce emergency response coverage
- **Transparency:** All code, preprocessing steps, and model artifacts version-controlled and shared within data licensing constraints to enable independent auditing

---

## Limitations

- Alaska excluded from the dataset, limiting national representativeness
- Dataset lacks direct indicators for driver impairment (DUI), detailed road surface conditions, and vehicle-specific data
- Extreme class imbalance (Severity 2 ≈ 80% of records; Severity 4 < 3%) required sampling that limits use of the full 7.7 million records during training
- Models trained on 2016–2023 data may not generalize to future trends such as electric vehicle adoption, autonomous driving, or shifting climate conditions

---

## Assumptions

- The dataset is comprehensive and sufficiently representative for statistical analysis and machine learning modeling across the 49 included states
- Features accurately reflect real-world conditions at the time of each incident
- Temporal features (start/end time, sunrise/sunset, twilight indicators) reliably capture contextual patterns in accident occurrence and severity

---

## Future Work

- Integrate live data feeds (including Alaska) for real-time severity forecasting
- Explore XGBoost and LightGBM as potential performance improvements over Gradient Boosting
- Incorporate additional risk factors: road surface conditions, speed limits, vehicle type, driver impairment indicators
- Partner with emergency services and transportation departments for pilot deployment and outcome-based model validation

---

## References

- Moosavi, S. et al. *US Accidents (2016–2023)*. Kaggle. https://www.kaggle.com/datasets/sobhanmoosavi/us-accidents
- NHTSA. *Fatality Analysis Reporting System (FARS)*. https://www.nhtsa.gov/research-data/fatality-analysis-reporting-system-fars
- Chen, T., & Guestrin, C. (2016). *XGBoost: A Scalable Tree Boosting System*. KDD '16. https://doi.org/10.1145/2939672.2939785
- Nihlén Fahlquist, J. (2009). *Saving lives in road traffic — ethical aspects*. Journal of Public Health, 17(6). https://doi.org/10.1007/s10389-009-0264-7
