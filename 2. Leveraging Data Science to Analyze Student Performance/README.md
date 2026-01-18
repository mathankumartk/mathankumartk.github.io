# README: Analysis of Student Performance, Stress, and Academic Success - Data Science Approach

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

## Contact

For any questions or feedback, please contact Mathan Kumar Thavu Mudaliar Kanagaraj at [mathankumartk@gmail.com](mailto:mathankumartk@gmail.com).
