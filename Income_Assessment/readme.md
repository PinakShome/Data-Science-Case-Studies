## Census Income Data Analysis and Modeling

This project involves analyzing and modeling census income data to predict whether an individual's income exceeds $50,000 per year based on census data. This document outlines the process followed, including data cleaning, preprocessing, exploratory data analysis, and model building.

## Data Cleaning and Preprocessing

- **Cleaning Text Columns:** We clean the text columns by trimming white spaces and replacing '?' with NA values.
- **Inspecting Unique Values:** We inspect unique values in all columns to understand the data better and prepare it for modeling.
- **Setting Correct Data Types:** Based on the dataset schema, we set the correct data types for each column.
- **Handling Missing Values:** We identify and handle missing values by dropping columns and rows based on certain criteria.
- **Mapping Target Variable:** The target variable `income_50` is mapped to binary values for modeling.

## Exploratory Data Analysis (EDA)

We explore the distribution of the target variable `income_50` and note a high imbalance in the dataset.

## Oversampling the Minority Class

To address the imbalance, we use SMOTE (Synthetic Minority Over-sampling Technique) to oversample the minority class in the training data.

## Scaling and Encoding Features

We scale numerical features and encode categorical features using `StandardScaler` and `OneHotEncoder`, respectively, to prepare the data for machine learning models.

## Modeling

We experiment with several machine learning models, including Logistic Regression, Random Forest, XGBoost, and LightGBM. The performance of each model is evaluated based on accuracy, precision, recall, F1 score, and ROC AUC score. Random Forest performs exceptionally well, achieving nearly perfect scores across all metrics. However, to ensure a thorough analysis, we also evaluate other models.

## Feature Importance and Model Comparison

We also explore feature importance using the LightGBM model to gain insights into which features are most predictive of the target variable.

## Conclusions

The Random Forest model showed remarkable performance, but due to its nearly perfect scores, further investigation might be necessary to ensure there's no overfitting. Other models, like Logistic Regression, XGBoost, and LightGBM, also show good performance, demonstrating the potential for machine learning in predicting income levels based on census data.

## Future Work

- Further exploration of feature engineering and selection could improve model performance.
- Hyperparameter tuning could optimize the performance of models other than Random Forest.
- Deploying the model as a web application could make it accessible for real-world testing and usage.

## Acknowledgements

This project is a comprehensive effort to apply machine learning techniques to census income data, offering insights into predictive modeling and data preprocessing strategies.