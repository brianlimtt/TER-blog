[← Home](https://brianlimtt.github.io/TER-blog/)<br>
- **Jupyter Notebook (.ipynb):** [Link Q8](https://github.com/brianlimtt/TER/blob/main/linear-regression-auto/Linear%20Regression%20Auto%20Q8.ipynb)
- **Jupyter Notebook (.ipynb):** [Link Q9](https://github.com/brianlimtt/TER/blob/main/linear-regression-auto/Linear%20Regression%20Auto%20Q9.ipynb)
  <br>
  <br>
# Linear Regression Analysis of Horsepower vs. Price


This project explores the relationship between **horsepower** and **price** of vehicles using linear regression. We aim to build a predictive model and analyze how changes in horsepower impact vehicle prices.

---

## Table of Contents Q8
1. [Data Exploration](#data-exploration)
2. [Building the Model](#building-the-model)
3. [Making Predictions](#making-predictions)
4. [Model Evaluation](#model-evaluation)
5. [Key Takeaways](#key-takeaways)
6. [Next Steps](#next-steps)

---

## Data Exploration

We started by inspecting the dataset, checking for missing values, and visualizing relationships. Scatter plots between **horsepower** and **price** revealed a roughly linear trend, which is ideal for linear regression.
<br>
![Mpg vs Horsepower with regression line](images/mpg_vs_horsepower_with_regression_line.png)
> *Figure 1: Scatter plot showing the relationship between horsepower and price.*

---

## Building the Model

A linear regression model was created to estimate the relationship between horsepower and price. The regression equation is:

$$
\text{Price} = \beta_0 + \beta_1 \cdot \text{Horsepower}
$$

Where:  
- `β0` = intercept  
- `β1` = slope, representing the change in price per unit increase in horsepower.

This equation allows us to quantify how much price increases for each additional unit of horsepower.

---

## Making Predictions

Using the regression model, we can predict the price of a vehicle with a given horsepower. For example, a vehicle with **98 horsepower** has a predicted price calculated from the equation above.  

Predictions also include a **95% confidence interval**, showing the range in which we can be reasonably confident the true price falls.

![Residuals vs Fitted ](images/residuals_vs_fitted.png)
> *Figure 2: Visualization of predicted prices with confidence intervals.*

---

## Model Evaluation

The model was evaluated for accuracy and reliability:

- **R-squared**: Measures how much of the variation in price is explained by horsepower.  
- **Residual analysis**: Checks for patterns that might indicate violations of linear regression assumptions, such as non-linearity or inconsistent spread of residuals.

![QQ Plot of Residuals](images/qq_plot_of_residuals.png)
> *Figure 3: Residual plot showing the spread of residuals around zero.*

--- 

## Key Takeaways

- **Positive correlation**: Higher horsepower generally results in higher prices.  
- **Simple and effective**: Linear regression works well with a single predictor.  
- **Confidence intervals**: Provide insight into the reliability of predictions.  
- **Residual checks**: Confirm that model assumptions are reasonable.

---

## Next Steps

- Extend the model to include multiple predictors, such as weight, engine size, or fuel efficiency.  
- Explore non-linear models if relationships are not perfectly linear.  
- Compare predicted prices with actual market prices for validation.  
- Visualize model predictions on new datasets for further insights.

---

![Scale-location Plot](images/scale_location_plot.png)
> *This analysis demonstrates a straightforward application of linear regression to real-world vehicle data, showing how predictive modeling can help understand and forecast trends.*



# 🚗 Auto Dataset Analysis — Scatterplot Matrix, Correlation Matrix, and Multiple Linear Regression

## Table of Contents
1. Introduction  
2. About the Dataset  
3. Cleaning the Data  
4. Scatterplot Matrix  
5. Correlation Matrix  
6. Multiple Linear Regression  
7. Key Findings  
8. Conclusion  

---

## Introduction
In this analysis, I explored the Auto dataset, which contains information on fuel efficiency (mpg), engine characteristics, vehicle weight, acceleration, model year, and country of origin.

The goal of this project was to:
- examine pairwise variable relationships  
- compute correlations  
- clean the dataset and remove missing values  
- build a multiple linear regression model predicting **mpg**  
- interpret statistical significance and trends  

This follows typical textbook regression questions but applied to a real dataset.

---

## About the Dataset
The dataset includes the following variables:

- mpg  
- cylinders  
- displacement  
- horsepower  
- weight  
- acceleration  
- year  
- origin  
- name  

The target variable is **mpg**, while all others serve as predictors or categorical identifiers.

---

## Cleaning the Data
The raw dataset contained missing entries marked as `"?"`. These were converted into `NaN` values and dropped to form a clean analysis-ready dataset.

All variables except `name` were converted to numeric types to prepare for correlation and regression analysis.

After cleaning, we retained **392 complete observations**.

---

## Scatterplot Matrix
A **seaborn pairplot** was used to generate a scatterplot matrix of all numerical variables.

This visualization helps identify:
- linear trends  
- outliers  
- nonlinear relationships  
- clusters  
- positive and negative correlations  

The pairplot clearly shows that **mpg decreases** as weight, displacement, horsepower, or cylinders increase.

---

## Correlation Matrix
Next, a correlation matrix was computed using only numeric columns.

Key observations:

- **mpg** has strong negative correlations with  
  - weight (≈ -0.83)  
  - displacement (≈ -0.80)  
  - horsepower (≈ -0.78)  
  - cylinders (≈ -0.78)

- Strong positive correlations exist between predictors, e.g.:  
  - displacement & cylinders (≈ 0.95)  
  - displacement & weight (≈ 0.93)

This indicates **multicollinearity**, meaning many predictors carry redundant information.

A heatmap was generated to visually show these relationships.

---

## Multiple Linear Regression
A multiple linear regression model was fit with **mpg** as the response and all other numeric variables as predictors.

### Model Performance:
- R-squared: **0.821**  
- Adjusted R-squared: **0.818**  
- F-statistic: extremely significant  

This means the model explains **82%** of the variance in mpg.

### Significant Predictors (p < 0.05):
- displacement (positive coefficient)  
- weight (negative coefficient)  
- year (positive coefficient)  
- origin (positive coefficient)  

### Non-significant Predictors:
- cylinders  
- horsepower  
- acceleration  

Because of multicollinearity, some variables become statistically insignificant once others are included in the model.

### Notes:
- Condition number was high (~8.6e4), confirming multicollinearity issues.  
- Weight had the strongest individual effect, with a large negative coefficient.

---

## Key Findings
- Cars become more fuel-efficient over the years (positive coefficient for year).  
- Vehicles from certain origins (e.g., Japan, Europe) tend to have higher mpg.  
- Weight is the single strongest negative predictor of mpg.  
- High correlations between engine size variables lead to multicollinearity.  
- Even with multicollinearity, the model still provides strong predictive power.

---

## Conclusion
This project combined visualization, data cleaning, correlation analysis, and multiple regression modeling into a complete statistical workflow.

By exploring scatterplots, correlations, and model outputs, we gained a detailed understanding of which features drive fuel efficiency and how they interact.

This mirrors the structure of advanced introductory regression problems, but executed with a real dataset and professional analysis tools.



