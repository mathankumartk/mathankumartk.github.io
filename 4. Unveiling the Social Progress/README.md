# Unveiling the Social Progress: Socio-Economic Dynamics Across Nations

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