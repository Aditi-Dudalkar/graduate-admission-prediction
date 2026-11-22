# Graduate Admission Prediction | Jamboree Education

## Project Overview

This project focuses on predicting the probability of a student's admission to a graduate program using academic performance and application-related factors.

The case study uses the Graduate Admissions dataset to build and evaluate regression models that estimate admission chances based on GRE scores, TOEFL scores, CGPA, university rating, Statement of Purpose (SOP), Letter of Recommendation (LOR), and research experience.

The objective is to help Jamboree Education provide data-driven guidance to students, identify areas for profile improvement, and support informed university selection.

## Business Problem

Jamboree Education helps students prepare for graduate admissions. Understanding how different applicant attributes relate to admission chances can help the organization deliver more personalized and effective counselling.

The key business objectives are:

- Identify the factors most strongly associated with graduate admission chances.
- Build a predictive model to estimate admission probabilities.
- Evaluate model performance and reliability.
- Translate analytical findings into actionable recommendations for students and the business.

## Dataset

The dataset contains 500 student records and 9 columns.

| Feature | Description |
|---|---|
| GRE Score | Graduate Record Examination score |
| TOEFL Score | English proficiency test score |
| University Rating | Rating of the student's university |
| SOP | Statement of Purpose strength |
| LOR | Letter of Recommendation strength |
| CGPA | Undergraduate academic performance |
| Research | Whether the student has research experience |
| Chance of Admit | Target variable representing admission probability |

The `Serial No.` column was removed because it serves only as a unique identifier.

## Tools & Technologies

- **Programming Language:** Python
- **Environment:** Google Colab / Jupyter Notebook
- **Data Manipulation:** Pandas, NumPy
- **Visualization:** Matplotlib, Seaborn
- **Statistical Analysis:** Statsmodels, SciPy
- **Machine Learning:** Scikit-learn

## Project Workflow

### 1. Exploratory Data Analysis (EDA)

- Examined dataset structure, dimensions, and data types.
- Checked for missing values and duplicate records.
- Analyzed numerical feature distributions.
- Studied relationships between predictors and the target variable.
- Used correlation analysis and visualizations to identify important patterns.

### 2. Data Preprocessing

- Removed the unique identifier column.
- Verified data quality and handled potential outliers.
- Separated independent variables and the target variable.
- Split the dataset into training and testing sets (80:20).
- Applied StandardScaler to numerical features using training data to avoid data leakage.

### 3. Model Building

Built and compared the following regression models:

- Linear Regression
- Ridge Regression
- Lasso Regression

Used cross-validation and hyperparameter tuning to identify suitable regularization parameters for Ridge and Lasso regression.

### 4. Regression Assumption Testing

Evaluated the key assumptions of linear regression:

- Linearity
- Independence of errors
- Homoscedasticity
- Normality of residuals
- Multicollinearity

Used residual plots, statistical tests, and Variance Inflation Factor (VIF) analysis to evaluate model assumptions.

### 5. Model Performance Evaluation

Evaluated models using:

- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)
- R-squared (R²)
- Adjusted R-squared

Compared training and testing performance to assess generalization and identify potential overfitting or underfitting.

### 6. Actionable Insights & Recommendations

- Ranked predictors using standardized regression coefficients.
- Evaluated predictor significance using p-values.
- Identified additional variables that could improve predictive performance.
- Proposed real-world implementation strategies and potential business benefits for Jamboree Education.

## Model Performance

The three models achieved very similar testing performance.

| Model | Test MAE | Test RMSE | Test R² |
|---|---:|---:|---:|
| Linear Regression | 0.0427 | 0.0609 | 0.8188 |
| Tuned Ridge | 0.0429 | 0.0609 | 0.8185 |
| Tuned Lasso | 0.0426 | 0.0608 | 0.8191 |

**Best-performing model: Tuned Lasso Regression**

Tuned Lasso achieved a marginally better test performance, although the improvement over baseline Linear Regression was negligible.

The baseline Linear Regression model achieved an R² score of approximately 0.819, explaining around 81.9% of the variation in admission chances.

Its test MAE of 0.0427 represents an average absolute prediction error of approximately 4.27 percentage points on the admission probability scale.

## Key Analytical Findings

### 1. Important Admission Predictors

Based on standardized regression coefficients and statistical significance:

| Predictor | Standardized Coefficient | P-value |
|---|---:|---:|
| CGPA | 0.4808 | < 0.001 |
| GRE Score | 0.1897 | < 0.001 |
| TOEFL Score | 0.1297 | 0.002 |
| LOR | 0.1129 | < 0.001 |
| Research | 0.0849 | 0.001 |
| University Rating | 0.0209 | 0.541 |
| SOP | 0.0127 | 0.721 |

CGPA emerged as the strongest predictor, followed by GRE Score and TOEFL Score.

University Rating and SOP were not statistically significant independent predictors in the fitted model.

### 2. Model Diagnostics

- VIF values were below 5, indicating no severe multicollinearity based on the chosen threshold.
- The Breusch-Pagan test indicated evidence of heteroscedasticity.
- The Jarque-Bera test indicated that residuals were not normally distributed.
- The Durbin-Watson statistic was approximately 2.05, suggesting no notable first-order autocorrelation.

These diagnostic findings should be considered when interpreting the model, particularly for statistical inference.

## Business Recommendations

Jamboree Education could use the model as a decision-support tool within its student counselling workflow.

Potential applications include:

- Providing personalized admission chance estimates.
- Identifying areas where students can strengthen their academic profiles.
- Supporting university shortlisting.
- Improving counselling efficiency through data-driven recommendations.
- Developing personalized student engagement and marketing strategies.

The model should be validated on newer and more diverse admission datasets before large-scale deployment. Predictions should be treated as estimates rather than guaranteed admission outcomes.

## Limitations & Future Improvements

- The dataset contains only 500 observations, which limits the diversity of applicant profiles.
- Additional variables such as undergraduate specialization, work experience, research publications, application quality, and university-specific requirements could improve predictions.
- Non-linear models such as Random Forest and Gradient Boosting could be explored.
- Model performance should be validated across different universities, programs, and admission cycles.
- Future versions could incorporate updated admission outcomes and monitor model drift.

## Conclusion

This case study demonstrates an end-to-end regression modeling workflow, from exploratory data analysis and preprocessing to model development, evaluation, diagnostic testing, and business recommendations.

The results indicate that academic performance, particularly CGPA, plays an important role in predicting graduate admission chances within this dataset.

The final model provides a useful starting point for data-driven student counselling, with opportunities for improvement through richer data and further experimentation.

---

**Project Type:** Regression | Supervised Machine Learning | Predictive Analytics | Business Case Study
