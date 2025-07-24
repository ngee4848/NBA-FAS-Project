# Quantitative Analysis: Predicting NBA 3-Point Shooting Percentage

## Project Overview

This project focuses on building and evaluating various regression models to predict NBA players' seasonal three-point shooting percentage (`three_pct_season`) based on their early-season (October-November) performance metrics. The goal was to identify the most effective predictive model for this financial-analyst-style sports analytics problem.

## Data

The dataset `fas_2024.csv` contains early-season (October-November) shooting statistics for NBA players, including:
- `three_pct_season`: Player's seasonal three-point percentage (target variable)
- `lwr_paint_pct_oct_nov`: Lower paint shooting percentage (Oct-Nov)
- `upr_paint_pct_oct_nov`: Upper paint shooting percentage (Oct-Nov)
- `mid_pct_oct_nov`: Mid-range shooting percentage (Oct-Nov)
- `three_non_cnr_pct_oct_nov`: Non-corner three-point percentage (Oct-Nov)
- `three_cnr_pct_oct_nov`: Corner three-point percentage (Oct-Nov)
- `ft_pct_oct_nov`: Free throw percentage (Oct-Nov)
- And corresponding shot attempt counts for each area.

## Methodology

I explored and compared the performance of several regression models, selecting the optimal model based on Mean Squared Error (MSE) on a held-out test set.

1.  **Exploratory Data Analysis (EDA):** Performed descriptive statistics and correlation analysis to understand variable relationships.
2.  **Model Selection:** Evaluated the following models:
    * **Linear Regression:** A baseline model using all predictor variables.
    * **Backward and Forward Stepwise Regression:** To identify a more parsimonious model with fewer predictors.
    * **Lasso Regression:** Chosen for its ability to perform variable selection by penalizing less predictive features, making it robust when not all variables are equally relevant.
    * **Support Vector Machine (SVM) Model:** To assess the performance of a non-linear regression approach.
3.  **Train-Test Split & Cross-Validation:** Data was split into 80% for training and 20% for testing. Cross-validation was applied to improve model performance and select optimal regularization parameters, particularly for the Lasso model.
4.  **Accuracy Metric:** Mean Squared Error (MSE) was used to measure model accuracy on the test set, as it penalizes larger errors and is a widely accepted metric.

## Results

The Lasso Regression model consistently demonstrated the lowest Mean Squared Error (MSE) on the test set compared to other models, indicating its superior predictive accuracy.

### Model Comparison (Test Set MSE)

| Model                       | MSE (Test Set) |
| :-------------------------- | :------------- |
| Linear Regression           | 0.000825       |
| Forward Stepwise Regression | 0.000786       |
| Backward Stepwise Regression| 0.000786       |
| **Lasso Regression** | **0.000144** |
| Support Vector Machine      | 0.003267       |

*Lasso Regression had the lowest MSE, indicating its predictions were closest to the actual values.*

### Lasso Regression: Actual vs. Predicted Values
[Lasso Regression vs Predicted Values.jpg](Lasso Regression vs Predicted Values.jpg)


*Note: The diagonal red dashed line represents perfect predictions (Actual = Predicted).*

## Key Takeaways

* Lasso regression proved to be the most effective model for predicting NBA 3-point shooting percentages in this study, likely due to its inherent feature selection capabilities, which identified and down-weighted less relevant variables.
* Early-season shooting percentages (especially corner and non-corner three-point percentages, and mid-range percentage) were strong predictors of seasonal performance.
* This project demonstrates proficiency in data loading and manipulation, statistical modeling, model evaluation, and results interpretation using R.


## Files in this Repository
* `FAS_Project_Presentation.pptx`: Presentation slides summarizing the project.
* `FAS_Project.Rmd`: R Markdown notebook containing all the R code and analysis.


## Contact

Feel free to reach out if you have any questions or feedback.

Nathaniel Gee
https://www.linkedin.com/in/nathaniel-gee/

