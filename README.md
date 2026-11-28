

# Household Appliance Energy Consumption Analysis

## Project Overview

This project analyzes household appliance energy consumption using Python and data analytics techniques.

The purpose is to understand household electricity usage patterns, identify factors associated with energy consumption, and determine whether indoor conditions, outdoor weather, and time of day can help predict appliance consumption.

## Research Questions

1. Is household appliance energy consumption different during the day and night?
2. Which variables are most associated with household appliance energy consumption?
3. Can indoor conditions, outdoor weather, and time of day predict appliance consumption?

## Dataset Description

The dataset contains household appliance energy consumption readings, indoor environmental measurements, and outdoor weather conditions.

Important variables include:
- Appliances
- Date
- Temperature (T1-T9)
- Relative Humidity (RH_1-RH_9)
- Outdoor Temperature (T_out)
- Outdoor Humidity (RH_out)
- Windspeed
- Visibility
- Atmospheric Pressure
- Lighting (lights)

Dataset Source: [Insert original dataset source and URL]

## Tools and Technologies

- Python
- Jupyter Notebook
- Pandas
- NumPy
- Matplotlib
- Seaborn
- SciPy
- Scikit-learn

## Data Cleaning and Preparation

The following procedures were performed:

1. Converted date values into datetime format.
2. Checked missing values.
3. Checked duplicate records.
4. Created an hour variable.
5. Created a Day/Night classification variable.
6. Removed unnecessary random variables (rv1 and rv2).
7. Examined outliers using the IQR method.

## Exploratory Data Analysis (EDA)

The analysis included:

- Descriptive statistics.
- Mean and median calculations.
- Daytime and nighttime consumption comparisons.
- Distribution analysis.
- Correlation analysis.
- Data visualization.

## Statistical Analysis

A paired-samples t-test was conducted to compare daytime and nighttime appliance consumption.

Hypotheses:

- H0: There is no significant difference between daytime and nighttime consumption.
- H1: There is a significant difference between daytime and nighttime consumption.

A significance level of 0.05 was used.

Additional checks included the Shapiro-Wilk test, Wilcoxon signed-rank test, and bootstrap confidence interval.

## Correlation Analysis

The strongest observed correlations with appliance consumption were:

| Variable | Correlation |
|---|---:|
| Hour of Day | +0.22 |
| Lights | +0.20 |
| Outdoor Relative Humidity | -0.15 |

These results indicate relatively weak linear relationships.

## Linear Regression

Linear Regression was used to predict household appliance energy consumption.

Target variable:
- Appliances

The dataset was divided chronologically:

- Training set: 80% (15,788 observations)
- Testing set: 20% (3,947 observations)

A Mean Baseline model was used for comparison.

Model evaluation:

| Metric | Linear Regression | Mean Baseline |
|---|---:|---:|
| MAE | 49.06 | 52.69 |
| RMSE | 84.77 | 91.05 |
| R-squared | 0.133 | - |

The Linear Regression model performed better than the mean baseline, although its predictive ability remained limited.

## Key Findings

1. Average daytime appliance consumption was approximately 119.7 Wh, compared with 53.7 Wh at night.
2. Hour of day, lighting, and outdoor relative humidity showed the strongest observed correlations.
3. Linear Regression performed better than the mean baseline.
4. The model explained only a limited portion of appliance consumption variation.

## Limitations

- The dataset may not represent every household.
- Some high consumption readings are difficult to predict.
- Individual correlations were relatively weak.
- Seasonal differences may affect model performance.
- Linear Regression may not capture nonlinear relationships.

## Conclusion

This project demonstrates how data analytics and machine learning can be used to understand household appliance energy consumption.

The analysis found a significant difference between daytime and nighttime consumption. Correlation analysis identified several associated variables, while Linear Regression provided modest improvement over a simple mean baseline.

## Files

- analysis_final (2)(2).ipynb - Main analysis notebook.
- energydata_clean.csv - Cleaned dataset.


