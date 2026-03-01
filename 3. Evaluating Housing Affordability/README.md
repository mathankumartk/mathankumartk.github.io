# Evaluating Housing Affordability

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
- Apply clustering techniques to segment rental markets by price tier and identify affordability gaps by region