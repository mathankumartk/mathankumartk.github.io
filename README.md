# README: Data Science Projects Portfolio

# 1. The Future of ChatGPT - How Will ChatGPT Impact the World?

## Project Overview

This project explores the impact of ChatGPT, a Generative Pretrained Transformer (GPT) developed by OpenAI, on various aspects of society, including business enterprises, healthcare, workforce, and ethical considerations. The study aims to analyze the potential benefits, challenges, and future developments of ChatGPT and its latest iteration, GPT-4.

## Research Questions

1. **Role of ChatGPT in business enterprises**
2. **Potential of ChatGPT in healthcare**
3. **Limitations and ethical concerns of ChatGPT**
4. **Impact of ChatGPT on the workforce**
5. **Future developments of ChatGPT**

## Key Findings

### Business Enterprises

- Streamlines operations like data entry, scheduling, and conflict management.
- Enables employees to focus on acquiring new skills and core business tasks.
- Increasing demand for Generative AI skillsets in the job market.

### Workforce Impact

- Up to 300 million jobs globally could be affected by AI automation.
- Certain job types, such as administrative roles, are at higher risk of replacement.
- 88% of the American workforce is familiar with ChatGPT, making adoption easier.

### Healthcare

- GPT-4 can process visual inputs, aiding in medical diagnoses and treatment planning.
- Potential applications include maintaining patient records, automating administrative tasks, and analyzing treatment progress.
- The global Generative AI in Healthcare market is projected to grow significantly, reaching $17.2 billion by 2032.

### Limitations and Ethical Concerns

Challenges include lack of creativity, bounded knowledge, cognitive limitations, privacy risks, bias, and transparency issues.

## Future Developments

- GPT-4 introduces multimodal capabilities (text, image, audio, video) and internet connectivity for up-to-date responses.
- Increased training dataset size enhances accuracy but raises complexity and ethical concerns.

## Opportunities

- Automating repetitive tasks
- Enhancing security recommendations and risk analysis
- Identifying patterns and anomalies in data
- Augmenting educational resources
- Improving customer support with 24/7 availability
- Advancing healthcare diagnostics and administrative efficiency

## Challenges

- Academic integrity concerns
- Resource constraints due to limited training datasets
- Bias and fairness issues in AI outputs
- Lack of transparency in AI-generated results
- Legal and regulatory compliance
- Balancing human expertise with automation

## Ethical Considerations

- Privacy concerns regarding data usage and anonymization
- Risk of bias and discrimination in AI outputs
- Lack of transparency in AI decision-making processes
- Potential misuse of AI for malicious purposes
- Impact on social justice, individual autonomy, and cultural identity

## Conclusion

ChatGPT is transforming the world by improving communication, efficiency, and accessibility across industries. Its potential is vast, but addressing ethical challenges, reducing bias, and upskilling the workforce are essential to fully realize its benefits. Businesses and organizations should consider integrating ChatGPT into their operations to enhance productivity, innovation, and customer satisfaction.

## References

A comprehensive list of references is provided in the document, including sources from Gitnux, Gartner, CNN, Business.com, and various research studies on ChatGPT's impact on society, healthcare, and the workforce.

## How to Use This Document

This document serves as a comprehensive analysis of ChatGPT's impact on the world. It can be used by researchers, businesses, healthcare professionals, and policymakers to understand the opportunities, challenges, and ethical considerations associated with ChatGPT and Generative AI tools.

# 2. Analysis of Student Performance, Stress, and Academic Success - Data Science Approach

## Project Overview

This project aims to analyze and understand the factors influencing student performance, stress, and academic success using data science methods. By identifying key contributing factors, the study seeks to provide actionable insights to educators, parents, and policymakers to improve student well-being and academic outcomes.

## Objectives

1. **Student Performance Analysis**: Identify factors influencing student performance, including alcohol consumption, family background, and romantic relationships.
2. **Student Stress Analysis**: Determine the primary contributors to student stress, such as psychological, physiological, environmental, academic, and social factors.
3. **Student Academic Success Analysis**: Explore the relationship between grades, personal characteristics, and external economic factors on academic success.

## Research Questions

1. What are the major factors influencing student performance? Are there subject-specific factors (e.g., Mathematics vs. Portuguese)?
2. How does alcohol consumption impact student performance, including weekday vs. weekend consumption?
3. What are the primary contributors to student stress? Is there a linear relationship between contributing factors and stress levels?
4. What are the top indicators within each category (e.g., sleep quality, peer pressure) and their comparative influence across categories?
5. What factors limit or enhance academic success? Are there trends based on age, gender, or nationality?

## Methodology

### 1. Data Collection

- **Datasets Used**:
    - Student Performance Dataset: Factors influencing performance in Mathematics and Portuguese.
    - Student Stress Factors Dataset: Contributing factors to student stress.
    - Student Dropout and Academic Success Dataset: Factors affecting enrollment, dropout, and graduation.

### 2. Data Preparation

- Import datasets using R (`read.csv()` function).
- Clean data by removing duplicates, handling missing values, renaming columns, and ensuring consistency in column headers.
- Transform and enrich data with supplementary information where necessary.

### 3. Exploratory Data Analysis (EDA)

- Visualize data using scatter plots, bar charts, and heatmaps to uncover patterns and relationships.
- Perform descriptive statistics to understand central tendencies and variability.

### 4. Model Building

- Develop logistic regression models to analyze the relationship between predictor variables (e.g., sleep quality, alcohol consumption, grades) and target variables (performance, stress, academic success).

### 5. Results Communication

- Present findings using visualizations (bar charts, scatter plots, heatmaps) and statistical summaries to stakeholders for evidence-based decision-making.

## Key Findings

### Student Performance

- Lower alcohol consumption correlates with higher grades, though the relationship is not strongly linear.
- Failures negatively impact performance, while factors like internet access and romantic relationships show moderate influence.

### Student Stress

- High sleep quality reduces stress, but the relationship is not strictly linear due to other contributing factors.
- Noise level is the highest contributor to stress, followed by sleep quality and teacher-student relationships.

### Student Academic Success

- Higher grades, especially in the second semester, strongly correlate with academic success.
- Gender and age at enrollment are significant factors, with younger students and females showing higher dropout rates.

## Tools and Techniques

- **Programming Language**: R
- **R Packages**:
    - `ggplot2` for data visualization.
    - `dplyr` and `tidyr` for data wrangling and transformation.
    - `janitor` for cleaning column names.
    - `caret` for classification and regression testing.
- **Visualization Methods**: Bar charts, scatter plots, heatmaps, and comparison charts.
- **Machine Learning**: Logistic regression models to predict performance, stress levels, and academic success.

## Limitations

1. Datasets are not collected from the same set of students, limiting the ability to cross-join and directly map performance, stress, and academic success.
2. Data is specific to certain geographies, which may limit the generalizability of findings to a global student population.
3. Missing data for specific scenarios (e.g., female students with mothers who are teachers) restricts the scope of analysis.

## Future Steps

1. Conduct surveys on the same set of students to enable cross-joining of datasets for more comprehensive analysis.
2. Expand datasets to include diverse geographies and demographics for global applicability.
3. Explore additional machine learning models to improve predictive accuracy and identify optimal models for analysis.

## Conclusion

This project highlights the importance of understanding the factors influencing student performance, stress, and academic success. By leveraging data science methods, we can identify key contributors to these outcomes and provide actionable insights to improve the quality of life and academic achievements of students. Future research should focus on larger, more diverse datasets and integrated surveys to enhance the reliability and applicability of findings.

## How to Run the Project

### Prerequisites

- Install R and RStudio.
- Install required R packages: `ggplot2`, `dplyr`, `tidyr`, `janitor`, `caret`.

### Steps

1. Import datasets using the `read.csv()` function.
2. Clean and preprocess data using functions like `subset()`, `is.na()`, `clean_names()`, and `names()`.
3. Perform exploratory data analysis using visualization tools (`ggplot2`).
4. Build logistic regression models using the `glm()` function.
5. Analyze model summaries and interpret results.

### Output

- Visualizations (bar charts, scatter plots, heatmaps).
- Statistical summaries (mean, median, variance, etc.).
- Logistic regression model results.

## References

1. Cortez, Paulo. (2014). Student Performance. UCI Machine Learning Repository. [Link]
2. Student Stress Factors: A Comprehensive Analysis. (n.d.). Kaggle. [Link]
3. Realinho, Valentim, Vieira Martins, Mónica, Machado, Jorge, and Baptista, Luís. (2021). Predict Students’ Dropout and Academic Success. UCI Machine Learning Repository. [Link]

# 3. Evaluating Housing Affordability

## Project Overview

This project analyzes and predicts rental prices for residential properties in India based on various physical and amenity-based features. By examining factors such as living area, number of bedrooms, bathrooms, parking availability, and power backup, the study aims to identify the key drivers of rental pricing and provide data-driven insights for tenants, landlords, and policymakers navigating housing affordability challenges in South Asian markets.

---

## Objectives

- Analyze the relationship between property characteristics and rental prices
- Identify the most influential factors driving rental costs
- Develop predictive regression models to estimate rent based on property features
- Understand the rental distribution across income segments — particularly the affordability gap for middle and lower-income populations

---

## Dataset

The dataset contains rental property listings with the following key variables:

| Variable | Description |
|---|---|
| `Rent` | Cost of renting the home in Indian Rupees (Dependent Variable) |
| `Area` | Total square footage of the living area |
| `Bedrooms` | Number of bedrooms in the rental home |
| `Bathrooms` | Number of bathrooms in the rental home |
| `Parking` | Number of parking spaces available |
| `Power Backup` | Availability of backup power (binary — 0/1) |

---

## Methodology

### 1. Exploratory Data Analysis (EDA)
- **Histograms** to examine the distribution and normality of each variable
- **Descriptive Statistics** to analyze skewness, central tendency, and variability across all features
- **Outlier Analysis** using box plots — outliers were identified above the 3rd quartile and determined to be natural (true) variations representing premium properties, and were retained in the dataset

### 2. Probability Distributions
- **PMF (Probability Mass Function):** Compared rent distributions between homes with and without power backup, revealing that power backup availability is associated with higher rental prices
- **CDF (Cumulative Distribution Function):** Revealed that approximately 80% of rental homes are priced below ₹20,000 (≈ $240 USD), confirming that the majority of the rental market serves middle-class and lower-income populations
- **Analytical Distribution:** Fitted a theoretical distribution model against actual data, confirming close alignment between the model and observed rental price distribution

### 3. Correlation & Scatter Plot Analysis
- **Rent vs. Total Sq. Ft. Living Area:** Positive relationship identified; Spearman correlation exceeded Pearson correlation (r = 0.17), indicating a non-linear association less sensitive to outliers
- **Rent vs. Number of Bedrooms:** Strong positive linear relationship confirmed; correlation coefficient of 0.69 indicates that number of bedrooms is the strongest individual predictor of rent

### 4. Hypothesis Testing
- Conducted hypothesis testing on parking amenities and rent — p-value < 0.05, confirming that parking availability is a statistically significant predictor of rental price

### 5. Regression Analysis
- **Single Explanatory Variable (Number of Bedrooms):** R² = 0.476, indicating that number of bedrooms alone explains approximately 47.6% of the variability in rent
- **Multiple Explanatory Variables (Bedrooms, Bathrooms, Power Backup, Gated Community, Furnishing):** R² = 0.542, indicating that the combined model explains approximately 54.2% of the variability in rent

---

## Key Findings

- **Number of Bedrooms** is the strongest individual predictor of rent, with a correlation coefficient of 0.69 and an R² of 0.476 in single-variable regression
- **Power Backup** availability is associated with higher rental prices, as evidenced by PMF comparison
- **80% of rental homes** are priced below ₹20,000 (~$240 USD), confirming that the rental market is predominantly serving middle-class and lower-income populations
- **Multiple regression** combining bedrooms, bathrooms, power backup, gated community, and furnishing improved the model's explanatory power to 54.2%
- Outliers in rent and bedroom/bathroom counts represent premium properties in upscale localities and were retained as true natural variations

---

## Tools & Technologies

| Tool | Purpose |
|---|---|
| Python | Primary programming language |
| Pandas & NumPy | Data manipulation and numerical analysis |
| Matplotlib & Seaborn | Data visualization (histograms, scatter plots, box plots) |
| SciPy | Statistical analysis, hypothesis testing, and distribution fitting |
| Scikit-learn | Regression modeling and model evaluation |

---

## Limitations

- The dataset is specific to the Indian rental market and may not generalize to other geographies or housing markets
- The multiple regression model explains only 54.2% of rental price variability, suggesting that additional features — such as location, proximity to transit, and neighborhood quality — could significantly improve predictive performance
- Positive skewness in rent and area distributions indicates that the model may be less accurate for premium high-value properties at the upper tail of the distribution

---

## Future Work

- Incorporate location-based features (e.g., city, neighborhood, proximity to schools and transit) to improve model accuracy
- Explore non-linear models such as Random Forest or Gradient Boosting to better capture complex relationships between features and rent
- Expand the dataset to include diverse geographies for broader applicability and cross-market comparison
- Apply clustering techniques to segment rental markets by price tier and identify affordability gaps by regionx`

# 4. Unveiling the Social Progress: Socio-Economic Dynamics Across Nations

## Project Overview

This project analyzes the relationships between crime rates, corruption perceptions, social progress indices, and economic indicators across various countries to identify socio-economic patterns and insights that may influence policy-making and development strategies. Data was sourced from three distinct channels — a flat file, web scraping, and a public API — and integrated into a unified SQLite database for cross-dataset analysis and visualization.

---

## Objectives

- Analyze the relationship between GDP and Social Progress Index across countries
- Examine the correlation between inflation and key economic indicators
- Study the interplay between crime rates, corruption perception, and social progress
- Identify the impact of inflation on health, wellness, and safety indices
- Explore the combined role of social progress and crime index in a country's economic standing

---

## Datasets

Three datasets were collected, cleaned, and integrated from distinct sources:

| Dataset | Source Type | Description |
|---|---|---|
| **Crime & Corruption Perception Index** | Flat File (CSV) | Country-level crime index scores and corruption perception indices sourced from World Population Review and Numbeo |
| **Social Progress Index** | Web Scraping (Wikipedia) | Country-level social progress scores compiled by the Social Progress Imperative, including health, sanitation, safety, and environmental indicators |
| **Economic Indices** | World Bank API | GDP, GDP growth rate, inflation, and goods & services export values by country (2023) |

All three datasets were cleaned, standardized to ISO country name format, and loaded into a unified SQLite database (`socio_economic_dynamics.sqlite`) for integrated analysis.

---

## Methodology

### 1. Data Collection & Extraction

- **Flat File:** Crime and Corruption Perception data imported using `pandas.read_csv()`
- **Web Scraping:** Social Progress Index scraped from Wikipedia using `BeautifulSoup` and parsed into a structured DataFrame
- **API:** Economic indices (GDP, GDP growth, inflation, exports) fetched from the World Bank API using the `requests` library

### 2. Data Cleaning & Preparation

- Validated and removed duplicate records across all three datasets
- Handled NaN values in essential columns — countries with missing key values were excluded from the Crime dataset; Social Progress and Economic datasets had no missing values
- Corrected data type inconsistencies across numerical and categorical fields
- Standardized country names to ISO format using the `pycountry` library to enable accurate cross-dataset joining
- Examined outliers and determined them to be natural variations (e.g., Australia's high GDP from natural resources, Guyana's rising GDP from oil production) — retained in the dataset

### 3. Data Integration

- All three cleaned datasets were loaded into a SQLite database using `SQLAlchemy`
- A final combined DataFrame (`socia_economic_final_df`) was created by joining all three tables on the standardized country name field

### 4. Exploratory Data Analysis & Visualizations

Five visualizations were produced to uncover socio-economic patterns:

| Visualization | Datasets Used | Objective |
|---|---|---|
| **Scatter Plot 1** | Economic Indices + Social Progress | Compare GDP vs. Social Progress Score across top 10 and bottom 10 GDP countries |
| **Scatter Plot 2** | Economic Indices | Compare GDP vs. Inflation across top 10 and bottom 10 GDP countries |
| **Line Plot** | Economic Indices + Crime & Corruption | Study the correlation between Social Progress Score and Crime Index across countries |
| **Column Bar Chart** | All Three Datasets | Study the impact of inflation on Health & Wellness and Safety Index across top/bottom 10 inflation countries |
| **Bubble Chart** | All Three Datasets | Explore the combined role of Social Progress and Crime Index in a country's GDP value |

---

## Key Findings

- Countries with higher GDP values generally exhibit higher Social Progress scores, though the relationship is not perfectly linear — some high-GDP nations still underperform on social metrics
- High inflation countries tend to show weaker safety and health & wellness indices, suggesting that economic instability has measurable social consequences
- Crime Index and Social Progress Score show an inverse relationship — countries with higher crime indices tend to score lower on social progress measures
- The bubble chart reveals that the combination of high social progress and low crime index is strongly associated with higher GDP, reinforcing the multi-dimensional nature of national prosperity
- Approximately 80% of countries in the dataset have Social Progress Scores that cluster in a mid-range band, with outlier nations at both extremes driven by unique geopolitical and economic circumstances

---

## Tools & Technologies

| Tool / Library | Purpose |
|---|---|
| **Python** | Primary programming language |
| **Pandas & NumPy** | Data manipulation, cleaning, and transformation |
| **BeautifulSoup** | Web scraping of Social Progress Index from Wikipedia |
| **Requests** | World Bank API data retrieval |
| **pycountry** | ISO country name standardization for cross-dataset joining |
| **SQLAlchemy** | SQLite database creation and data loading |
| **SQLite** | Unified database storage for all three datasets |
| **Matplotlib & Seaborn** | Data visualization (scatter plots, line plots, bar charts, bubble charts) |

---

## Ethical Considerations

### Data Licensing & Legal Compliance
- **Crime & Corruption Dataset:** Terms of Use from World Population Review and Numbeo permit free use for personal, academic, and journalistic purposes — not used for commercial purposes
- **Social Progress Dataset:** Wikipedia content is licensed under Creative Commons Attribution-ShareAlike 4.0 International License, allowing use with proper attribution
- **Economic Dataset:** World Bank data is provided under Creative Commons Attribution 4.0 International License, permitting sharing and adaptation with attribution

### Data Credibility & Verification
- Crime data was requested directly from the World Population Review administrator
- Social Progress Index was developed in consultation with MIT researchers and validated against real-world data
- World Bank GDP and economic data is considered one of the most trusted global sources; outlier values (e.g., Guyana, Sudan, Australia) were individually verified against geopolitical context

### Ethical Risks & Mitigations
- Crime reporting standards vary significantly across countries — comparisons should be interpreted with awareness that reported crime data does not uniformly reflect actual crime rates
- Social progress indices reflect culturally specific values; different societies prioritize different indicators of progress
- Economic analyses should highlight and address disparities rather than perpetuate global inequalities; local researchers and stakeholders should be involved in interpretation

---

## Limitations

- Countries with missing Crime Index values were excluded from the analysis, limiting the scope of crime-based comparisons
- Missing values in the Crime dataset were filled using mean imputation for time-series data, which may reduce accuracy for specific countries
- Visualizations were produced using filtered subsets (e.g., top/bottom 10 GDP countries, top/bottom 10 inflation countries) — findings reflect subsets and should not be generalized to the full global dataset without further validation
- The dataset represents a single year (2023) of economic data — longitudinal trends are not captured

---

## Future Work

- Expand the analysis to include longitudinal data across multiple years to identify trends and trajectories in social progress and economic development
- Incorporate additional social indicators such as education quality, gender equality, and environmental sustainability
- Apply clustering techniques (e.g., K-Means) to group countries by socio-economic profile and identify development archetypes
- Build predictive models to forecast social progress scores based on economic indicators
- Extend geographic coverage by resolving missing country data through alternative data sources

# 5. Assessing Loan Default Risks: Predicting Borrower Behavior Using Machine Learning

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

# 6. Harnessing Predictive Analytics in Real Estate: Housing Price Prediction Using Machine Learning

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

# 7. Major Factors Influencing the Cost of Child Care in the United States

A data analysis project examining the economic, demographic, and policy-related variables that drive child care affordability across the U.S., using the **National Database of Childcare Prices** from the U.S. Department of Labor.

---

## Overview

Child care centers play a crucial role in early childhood development while enabling parents to participate in the workforce. Yet affordability remains a major challenge — in over 30 U.S. states, the average cost of infant child care **exceeds in-state public college tuition**. This project identifies and analyzes the key factors behind these costs to surface actionable insights for policymakers, families, and child care providers.

---

## Dataset

- **Source:** National Database of Childcare Prices (U.S. Department of Labor)
- **Original Features:** 227
- **Features Used:** 70 (refined subset)
- **Key Variables:** Median household income, male/female median earnings, number of households per county, proportion of single-mother households, dual-income families, poverty rate, unemployment rate, employment rate

> **Note:** Median child care price data is unavailable for Indiana and New Mexico and those states were excluded from the analysis.

---

## Methodology

### Affordability Score

A custom affordability index was created to standardize comparisons across states and years:

```
Affordability Score = Median Price of Child Care Cost / Median Household Income
```

A score above 10% indicates financial strain on families.

### High-Level Workflow

1. Data Loading
2. Data Preparation (standardizing feature names, handling missing values)
3. Exploratory Data Analysis
4. Visualization

### Technology Stack

| Tool | Purpose |
|------|---------|
| Python | Data processing and analysis |
| pandas | Data manipulation |
| matplotlib / pyplot | Plotting |
| seaborn | Statistical visualizations |
| numpy | Numerical operations |
| Tableau | Interactive dashboards and maps |

---

## Key Findings

### Affordability
- Higher median household income generally correlates with higher affordability scores (families can afford more, but costs are also higher in wealthier states).
- Affordability slightly improved over time despite rising costs, as household earnings grew proportionally.
- Significant racial disparities exist — minority groups generally face higher child care costs relative to their income.

### Economic Factors
- A **positive correlation** exists between median child care prices (ages 6–11) and median household income.
- Male and female median earnings have grown steadily, but child care costs have risen faster, widening the gap.
- A **negative correlation** exists between female unemployment rates (ages 20–64) and median prices — higher unemployment is associated with lower child care costs.

### Social Factors
- **Poverty:** Higher poverty rates are associated with lower child care costs, but reflect limited access to quality care rather than affordability.
- **Race/Ethnicity:** Groups such as Asian and American Indian populations show a significant negative correlation with median prices, indicating potential higher cost burdens.
- **Single Mothers:** A weak national correlation between single-mother households and child care costs strengthens significantly in the top 10 states by single-mother population, underscoring regional variation.
- **Women's Workforce Participation:** States with higher child care costs show lower female labor force participation, highlighting child care as a structural economic barrier.

---

## Visualizations

Delivered via **Tableau Dashboards** and **PowerPoint Presentation**:

- Affordability scores for high-cost states (2016–2023)
- Affordability vs. Median Income — U.S. state map
- Affordability by racial/ethnic group
- Affordability scores by state (ranked)
- Affordability vs. Median Price and Median Earnings over time
- Affordability vs. Unemployment Rate

> Alaska was omitted from the map visualization for aesthetic consistency, focusing on contiguous U.S. states.

---

## Deliverables

| Medium | Audience | Focus Area |
|--------|----------|------------|
| Tableau Dashboard | Policymakers, Government Officials, Child Care Organizations | Affordability (Affordability Score vs. Median Income) |
| PowerPoint Presentation | Policymakers, Parents/Guardians | Economic Factors (Median Income, Labor Force Participation, Employment Rate) |
| Web Blog | Parents/Guardians, General Public | Social Factors (Race, Poverty, Single Mothers, Women's Workforce Engagement) |

---

## Ethical Considerations

- No PII (Personally Identifiable Information) exists in the dataset — no anonymization required.
- Data was acquired from a trusted government source (U.S. Department of Labor) and is not used for commercial purposes.
- No changes were made to the underlying data beyond omitting Indiana and New Mexico (missing child care price data) and standard technical transformations (feature renaming, missing value handling).
- Bias considerations were reviewed to ensure no underrepresentation of regions or provider types.

---

## Assumptions

- Prices in the dataset accurately reflect actual charges from child care providers at the time of data collection.
- Data collection methodology was consistent across years, allowing for valid temporal comparisons.
- Median prices are used over mean prices to reduce the effect of skewed distributions.

---

## Recommendations

| Area | Recommendation |
|------|---------------|
| **Subsidies** | Design income-based child care subsidies targeting low- and middle-income families |
| **Data Collection** | Expand data collection to include provider size, quality ratings, and staff qualifications |
| **Workforce** | Invest in training programs for child care workers to improve quality and attract professionals |
| **Policy** | Advocate for comprehensive family leave and flexible work policies |
| **Communication** | Improve outreach to ensure families are aware of available subsidies and resources |

---

## References

Hardy, K. (2025, March 9). *Costs of child care now outpace college tuition in 38 states, analysis finds*. Iowa Capital Dispatch. https://iowacapitaldispatch.com/2025/03/09/costs-of-child-care-now-outpace-college-tuition-in-38-states-analysis-finds/

National Database of Childcare Prices. U.S. Department of Labor. https://www.dol.gov/agencies/wb/topics/childcare/ndcp

# 8. Predicting Severity of US Car Accidents — A Machine Learning Approach

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

# 9. Exploring Trends in Movie Performance: A Machine Learning Classification Approach

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

# 10. Anomaly Detection in Credit Card Transactions: Leveraging Machine Learning for Fraud Classification

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


## Contact

For any questions or feedback, please contact Mathan Kumar Thavu Mudaliar Kanagaraj at [mathankumartk@gmail.com](mailto:mathankumartk@gmail.com).
