# Major Factors Influencing the Cost of Child Care in the United States

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
