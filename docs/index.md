# GDP per Capita and CO₂ Emissions per Capita

## Project Overview

This project uses Python and linear regression to explore whether GDP per
person can help predict annual CO₂ emissions per person.

The project reuses a professional predictive-analytics workflow: prepare
data, split it into training and test sets, compare a linear regression
model with a baseline, evaluate the results, and visualize predictions and
residuals.

## Question

**How well does GDP per person predict annual CO₂ emissions per person?**

## Data Preparation

The dataset contains one country or entity in one year per row. I created a
new `gdp_per_capita` feature by dividing GDP by population. I used this
derived value to reduce the influence of total population when comparing
observations.

The dataset began with 350 rows. After removing rows that were missing
values needed for the model, 308 rows remained.

## Modeling Process

* Feature: GDP per capita
* Target: CO₂ emissions per capita
* Training data: 246 rows
* Test data: 62 rows
* Baseline: Predict the average CO₂ emissions per person
* Model: Simple linear regression

## Results

| Model             | RMSE | R-squared |
| ----------------- | ---: | --------: |
| Baseline          | 5.61 |    -0.009 |
| Linear regression | 3.09 |     0.693 |

The linear regression model reduced the typical prediction error by 2.52,
or about 45%, compared with the baseline. Its R-squared value of 0.693
indicates that GDP per person explained about 69% of the variation in CO₂
emissions per person for the held-out test observations.

## Visualizations

### Predictions

![Actual and predicted CO₂ emissions per capita](images/co2-per-capita-regression-predictions.png)

### Residuals

![Residuals for the GDP-per-capita model](images/co2-per-capita-regression-residuals.png)

## Interpretation and Limitations

The results show a positive relationship between GDP per person and CO₂
emissions per person in this dataset. GDP per person was a useful single
predictor, but it did not fully explain emissions.

The residual plot shows that prediction errors were more spread out at
higher GDP-per-capita values. Other factors—such as energy sources,
industrial activity, and national policies—may improve future
predictions. This analysis identifies an association; it does not prove
that GDP causes CO₂ emissions.

## Run the Project

From the project root folder, run:

```powershell
uv run python -m datafun.co2_per_capita_model
```
