# Causal Inference Study: Impact of Higher Education on Salaries

## Overview
This project explores the causal relationship between higher education (Master's or Doctorate degrees) and salary outcomes using causal inference techniques. By employing advanced regression models and meta-learners, the study analyzes whether obtaining an advanced degree significantly impacts hourly wages compared to those with a bachelor's degree.

---

## Dataset and Preprocessing

### Data Description
- Dataset contains employee details, including education level, salary, and demographic factors.
- **Target Variables**:
  - HourlyRate (continuous)
  - Education Level (categorical)

### Preprocessing Steps
1. **Exploratory Data Analysis (EDA)**:
   - Histograms and pairplots to visualize feature distributions and relationships.
   - Correlation matrix heatmap to identify multicollinearity.
2. **Outlier Detection**:
   - Used **Isolation Forest** to remove anomalies, improving model performance.
3. **Encoding**:
   - Categorical variables (e.g., EducationField, Department, Gender) encoded using LabelEncoder.
4. **Treatment Indicator**:
   - Created a binary treatment variable:
     - `0`: Bachelor's degree
     - `1`: Master's or Doctorate degree
5. **Kernel Density Estimate (KDE) Plots**:
   - Visualized salary distributions across education levels.

---

## Methodology

### Causal Inference Techniques
1. **Average Treatment Effect (ATE)**:
   - Linear Regression (LRSRegressor): 0.0278
   - XGBoost Regression (XGBTRegressor): -0.9807
   - Meta-learners: T-learner, X-learner, R-learner.
   - Results show a minimal effect of advanced degrees on salary.
2. **Conditional Average Treatment Effect (CATE)**:
   - Individual treatment effects analyzed using meta-learners.
   - CATE values clustered near zero, indicating limited individual-level impact.

### Feature Importance
- **XGBTRegressor** identified the following key factors influencing salaries:
  - Age: 0.2034
  - Percent Salary Hike: 0.1250
  - Total Working Years: 0.1205
- **LRSRegressor** failed to calculate meaningful feature importance due to configuration issues.

---

## Results

### Key Findings
1. ATE estimates revealed a minor influence of higher education on salaries:
   - Maximum observed impact: -2.5.
   - Results challenge the conventional belief that advanced degrees significantly boost earnings.
2. Feature importance analysis highlighted demographic and professional factors as more critical than education level.

### Performance Metrics
- **LRSRegressor**:
  - ATE: 0.0278
- **XGBTRegressor**:
  - ATE: -0.9807
  - Key feature: Age (most significant factor influencing salaries).

---

## Conclusion
The study concludes that while advanced degrees are often linked to higher earning potential, their actual impact on salaries is minimal. Instead, other factors like age, work experience, and performance metrics play more substantial roles. This finding highlights the importance of a holistic approach when evaluating career advancement strategies.

---

## Contact
**Seunghyun Park**  
For any inquiries, feel free to reach out via email: seunghyun.park@mail.mcgill.ca.
