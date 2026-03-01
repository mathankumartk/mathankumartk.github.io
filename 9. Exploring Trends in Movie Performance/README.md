# Exploring Trends in Movie Performance: A Machine Learning Classification Approach

A supervised binary classification project that predicts whether movies will receive high ratings (above 7.0) using a dataset of 434,671 films. The project applies Logistic Regression, Random Forest, and XGBoost with Bayesian optimization to help filmmakers, studios, and streaming platforms make data-driven decisions about content development and investment.

---

## Business Problem

The film industry is one of the most capital-intensive sectors in entertainment. The average Hollywood production costs approximately **$100 million** when combining production (~$65M) and marketing (~$35M), with blockbusters averaging **$200 million** per film. Yet analysis of 5,193 Hollywood films over the past 100 years shows that **only 23% broke even**, with failure rates around **80%** in recent decades.

This project addresses five core research questions:

- What movie characteristics most strongly predict high ratings (>7.0)?
- How do genre and genre combinations impact critical reception?
- How does release timing affect ratings and box office performance?
- Does production scale (co-productions, country diversity, language) influence success?
- Which classification algorithms best predict high-rated movies to enable actionable business recommendations?

---

## Dataset

- **Source:** [Kaggle — TMDB + IMDb Merged Movies Dataset](https://www.kaggle.com/datasets/ggtejas/tmdb-imdb-merged-movies-dataset)
- **Size:** ~434,671 unique movie records, 29 features each
- **Data Sources:** The Movie Database (TMDB) and Internet Movie Database (IMDb)

### Target Variable
**High Rating** — binary classification derived from `average_rating`:
- Class 1 (High-Rated): rating > 7.0
- Class 0 (Low-Rated): rating ≤ 7.0

### Feature Groups

| Group | Key Features |
|-------|-------------|
| **Financial** | Budget (USD), Revenue (USD) |
| **Temporal** | Release date, year, decade (engineered), production status |
| **Production** | Production companies, countries, co-production flag, is_US_produced |
| **Content** | Genre binary columns (19 genres), genre count, keywords, overview, tagline |
| **Language** | Original language, spoken languages count, has_english_language flag |

---

## Data Preprocessing

**Missing Value Handling:**
- Records missing `release_date`, `genres`, `production_companies`, `production_countries`, `directors`, `writers`, or `cast` → deleted
- `spoken_languages` → filled using `original_language` via conditional imputation
- Text fields (`homepage`, `overview`, `tagline`, `keywords`) → filled with "no value available"
- Non-essential columns (`backdrop_path`, `poster_path`, `id`, `tconst`) → dropped

**Encoding:**
- **One-hot encoding:** `status` field (Released, In Production, Post Production, Planned); 19 genre binary columns expanded from `genres`
- **Binary encoding:** `adult` feature (Boolean → numerical)

**Feature Engineering:**
- `genre_count` — number of genres per film
- `co_production` — binary flag (1 if multiple production companies)
- `production_countries_count` and `spoken_languages_count`
- `is_us_produced` and `has_english_language` binary flags
- `year` and `decade` extracted from `release_date`
- All column names standardized to lowercase

**Exploratory Data Analysis:**
- Univariate: histograms and boxplots for budget, revenue, and ratings distributions
- Bivariate/Multivariate: correlation matrices and scatter plots across key variables
- Temporal: decade-grouped boxplots revealing shifts in revenue and audience preferences over time

---

## Methods

### Train-Test Split & Scaling
- 80/20 train-test split with `random_state=42` for reproducibility
- `StandardScaler` applied to normalize all numerical features

### Models Evaluated

#### Original Imbalanced Dataset Results

| Model | Accuracy |
|-------|----------|
| Logistic Regression | 69.41% |
| Gradient Boosting | 78.11% |
| **Random Forest** | **83.55%** |

#### After SMOTE Class Balancing

| Model | Accuracy | Notes |
|-------|----------|-------|
| Logistic Regression | 69.31% | Minimal change — insensitive to class imbalance |
| Gradient Boosting | 79.07% | +1.23% improvement |
| Random Forest | 84.48% | +1.11% improvement |
| **XGBoost + Bayesian Optimization** | **88.42%** | **+4.87pp over best baseline** |

### Class Balancing
The target variable showed a 60:40 imbalance (low-rated vs. high-rated). **SMOTE** was applied to the training set after the 80/20 split, generating synthetic minority-class samples via k-nearest neighbor interpolation to achieve a balanced 50:50 training distribution.

### Hyperparameter Optimization (XGBoost — Bayesian Optimization)

| Hyperparameter | Search Range | Optimal Value |
|---------------|-------------|--------------|
| `n_estimators` | 100–300 | 176 |
| `max_depth` | 3–10 | 10 |
| `learning_rate` | 0.01–0.1 | 0.0828 |
| `subsample` | 0.6–1.0 | 0.8249 |
| `colsample_bytree` | 0.6–1.0 | 0.6534 |

- **25 iterations** (5 random explorations + 20 optimization steps)
- **Optimized F1-score: 0.8841**

---

## Key Findings

### Best Model Performance — XGBoost (After Bayesian Optimization)

| Metric | Score |
|--------|-------|
| Accuracy | 88.42% (balanced) / 84.87% (full dataset) |
| Precision | 83.65% |
| Recall | 84.87% |
| F1-Score | 83.49% |

**Confusion Matrix (3,125-sample test set):**

| | Predicted Low | Predicted High |
|-|---------------|----------------|
| **Actual Low** | 1,403 (TN) | 157 (FP) |
| **Actual High** | 205 (FN) | 1,360 (TP) |

- Class 0 (Low-Rated): Precision 87%, Recall 90%, F1 0.91
- Class 1 (High-Rated): Precision 90%, Recall 87%, F1 0.88

### Most Predictive Features
- **Vote Count** — higher audience engagement correlates with higher ratings
- **Revenue & Budget** — financial scale shows modest correlation with critical success
- **Runtime** — movie length influences audience satisfaction
- **Budget-to-Revenue Ratio** — engineered feature reflecting production efficiency
- **Genre Combinations** — Action + Science Fiction + Adventure appear frequently in high-rated films
- **Production Company & Director** — established creators serve as quality indicators

### Correlation Findings
- `vote_average` ↔ `average_rating`: weak positive correlation (0.143)
- `vote_average` ↔ `revenue`: weak positive correlation (0.143)
- `vote_average` ↔ `popularity`: weak positive correlation (0.107)
- High ratings do not directly translate to higher revenue — suggesting other factors drive commercial success independently of critical reception

---

## Tools & Technologies

| Tool / Library | Purpose |
|----------------|---------|
| **Python** | Primary programming language |
| **Pandas & NumPy** | Data manipulation, cleaning, and feature engineering |
| **Matplotlib & Seaborn** | EDA visualizations (histograms, boxplots, correlation matrices, scatter plots) |
| **Scikit-learn** | Logistic Regression, Random Forest, Gradient Boosting, StandardScaler, evaluation metrics |
| **XGBoost** | Advanced gradient boosting classifier |
| **SMOTE (imbalanced-learn)** | Synthetic minority oversampling for class balancing |
| **BayesianOptimization (bayes_opt)** | Hyperparameter search and optimization |

---

## Implementation Roadmap

| Phase | Duration | Activities |
|-------|----------|-----------|
| **Phase 1 — Model Finalization & Validation** | 1–3 months | Finalize XGBoost model; retrain on full preprocessed dataset with class weighting/stratified sampling |
| **Phase 2 — Interpretability & Compliance** | 1–2 months | Integrate SHAP or LIME for feature importance rankings and individual prediction explanations |
| **Phase 3 — System Integration & Pilot** | 3–6 months | Integrate into studio or streaming platform systems; establish continuous monitoring pipelines |
| **Phase 4 — Monitoring & Scaling** | Ongoing | Track model drift, retrain with new release data, scale to additional markets and budget tiers |

---

## Ethical Considerations

- **Representation Bias:** Models trained on historical ratings may undervalue films by underrepresented directors, writers, or casts; regular fairness audits across demographic dimensions are recommended; separate budget-tier models advised to avoid penalizing mid-budget productions
- **Data Privacy:** Actors, directors, and writers did not explicitly consent to commercial predictive modeling; aggregated patterns should be used rather than individual-level predictions; names anonymized in R&D contexts
- **Rating Manipulation:** IMDb/TMDB ratings can be subject to artificial inflation or review bombing; model predictions reflect statistical patterns and require human oversight
- **Economic Inequality:** Budget-rating correlations risk eliminating mid-budget filmmaking; industry guilds and unions should be engaged when implementing algorithmic decision tools

---

## Limitations

- Class imbalance (~79.5% low-rated vs. ~20.5% high-rated in raw data) biases baseline model predictions toward the majority class
- Historical training data may not capture evolving industry dynamics — patterns from the 1980s may be irrelevant for 2025 productions
- Binary classification (high vs. not high) loses rating granularity; the 7.0 threshold is somewhat arbitrary
- XGBoost is a black-box model, limiting interpretability for non-technical stakeholders
- Computational complexity of Bayesian optimization poses practical constraints at scale

---

## Assumptions

- The dataset accurately reflects broader trends in the film industry and captures essential factors influencing ratings
- High ratings (>7.0) are reliable indicators of a movie's critical success and correlate with audience satisfaction
- Historical data patterns remain applicable for predicting future movie performance

---

## Future Work

- **Content Development Support:** Use predictive models to assess scripts at the greenlight stage based on genre, budget, and production characteristics
- **Recommendation Systems:** Integrate findings into streaming platform personalization to align content suggestions with individual viewer preferences
- **Genre-Specific Models:** Develop separate models per genre to capture audience preference variation across categories
- **Social Media Integration:** Incorporate social media metrics and audience demographics as additional predictive signals
- **Continuous Retraining:** Schedule regular model updates with new release data to stay aligned with current industry dynamics

---

## References

- Garg, T. (2023). *TMDB + IMDB Merged Movies Dataset*. Kaggle. https://www.kaggle.com/datasets/ggtejas/tmdb-imdb-merged-movies-dataset
- *Full TMDB Movies Dataset 2023 (930K Movies)*. Kaggle. https://www.kaggle.com/datasets/asaniczka/tmdb-movies-dataset-2023-930k-movies
- *IMDb Non-Commercial Datasets*. (2023). https://developer.imdb.com/non-commercial-datasets/
- Tang, T. (2023). *Class Imbalance Strategies — A Visual Guide with Code*. Medium / TDS Archive. https://medium.com/data-science/class-imbalance-strategies-a-visual-guide-with-code-8bc8fae71e1a
- Jayan, J. (2024). *Importance of Ethical Data Collection*. PromptCloud. https://www.promptcloud.com/blog/importance-of-ethical-data-collection/
