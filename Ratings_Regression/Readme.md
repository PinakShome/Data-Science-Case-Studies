# INTRODUCTION
This case study explores the intricate details of how machine learning models differ in making predictions when the dataset used has characteristics which are partially (but not completely) favorable to all the models being implemented. Since a soccer database is being used here, it has significance in understanding how analytics of different characteristics can have an impact on the game. But mainly, this aims to provide a concise model selection recommendation when the features of the dataset don’t clearly fit the criteria of any specific model. It provides insights into what models would be most suited for a given task with computational and metric prediction accuracy constraints in mind.

# Table of Contents 

- Dataset Description
- Preprocessing
- Exploratory Data Analysis
- Feature Engineering
- Modelling
- Results
- Conclusion
- Recommendation

# DATASET DESCRIPTION

Taken from : [Dataset-Soccer](https://www.kaggle.com/datasets/hugomathien/soccer)
(10k rows after cleaning - Mid Sized). This was originally a sql database file. I’ve extracted two tables of all available for this case study. The general trend of this dataset is:
All higher value float64 variables contribute to a higher target variable rating.

### Anomaly: 
There are several instances of rows where the target variable values are higher even though most of their ‘float64’ magnitudes are lower, which tell us that the features are not necessarily strong indicators of the target. This makes it suitable for
analyzing how models would learn on datasets with no clear patterns and help us understand the nuances of how we can leverage model architectures when there is no clear-cut trends present.

# Preprocessing
Steps included:

1)Dropping rows with null values: To ensure the quality of the data.
2)Mean imputation for numeric features and mode imputation for categorical features: This was done for each player's repeated instances.
3)Converting the 'date' column to age: Since age is more relevant to player performance.
4)Merging relevant tables: This formed a comprehensive dataset combining player attributes and ratings.

## Detailed Steps:

### Data Loading:

1) Connected to the SQLite database.
2)Extracted tables including Player_Attributes and Player.

### Initial Data Cleaning:

1)Dropped columns like id, player_fifa_api_id, and date.
2)Converted categorical variables (preferred_foot, attacking_work_rate, defensive_work_rate) to numeric values where appropriate.

### Handling Null Values:
    
1)Removed rows with any null values.
2)Performed mean imputation for numeric columns and mode imputation for categorical columns.

### Merging Data:

1)Merged Player_Attributes and Player tables on player_api_id.

# Exploratory Data Analysis

EDA involved visualizing the distributions of player attributes and their relationships with the overall rating. Key observations included:

1)Linearity and collinearity: Significant linearity was observed between some features and the target variable.
2)Anomalies: Instances where higher attribute values did not necessarily lead to higher ratings.

## Visualizations:

1)Histograms: For overall rating and other numeric features.
2)Correlation Matrix: Heatmap showing the correlations between different features.
3)Scatter Plots: For numeric features against overall rating.
4)Bar Plots: For categorical features like preferred_foot, attacking_work_rate, and defensive_work_rate.

# Feature Engineering

Steps included:

1)Creating 'age' from 'birthday': To capture the effect of a player's age on their performance.
2)Dropping less significant columns: Columns like birthday, player_name, and other IDs were dropped after extraction of useful features.

# Modeling

The following models were implemented and compared:

1)Linear Regression
2)Ridge Regression
3)Lasso Regression
4)Random Forest Regressor
5)Neural Networks

## Model Workflow
- Baseline Model: Mean of the training set target variable.
- Preprocessing Pipeline: Included standard scaling for numeric features and one-hot encoding for categorical features.
- Hyperparameter Tuning: Conducted for the Random Forest model using GridSearchCV.

### Model Workflow Summary

Picked three variations of linear models (Linear, Lasso and Ridge) pertaining to the fact that the dataset displayed linearity between features and the target variable. Since there was non linearity and complex relationships present as well (Referencing correlation matrix and Pearson-correlation values), I’ve additionally picked the random forest regressor and lastly neural nets to compare how well random forest is capturing the dynamics of relationships between all the variables (Given Feature Irrelevance). Since this dataset isn’t very high dimensional with over-complexity and has features that truly do not contribute to the target variable along with some complex relationships between features, Random forest may not perform significantly better than linear models. We’ll use neural networks to have a benchmark of Random Forest’ performance.



# Results

- Baseline Model (Mean): MSE = 37.736
- Linear Regression: MSE = 3.410
- Ridge Regression: MSE = 3.410
- Lasso Regression: MSE = 6.505
- Random Forest Regressor: MSE = 1.841
- Random Forest (Tuned): MSE = 1.830
- Neural Networks: Achieved the best performance due to their ability to capture complex relationships.

# Conclusion

- Base Linear regression and Ridge Regression perform very similar to random forest. Neural Nets perform best due to their ability to learn patterns through their hidden layers even if there is a high degree of feature irrelevance.
- Lasso Regression performs poorly compared to the other linear models because of its feature elimination process in a dataset with low feature relevance.
- There is a good deal of linearity in the dataset, which explains the enhanced performance of linear models compared to base-mean model.
- Random Forest does not outperform the linear models due to feature irrelevance present, along with lack of very high dimensionality and dataset size which prevents it from learning the dataset optimally.
 

# Recommendations

- For small datasets with mid to low dimensionality with significant presence of linearity even with collinear features existing, linear models should be preferred over more complex models if a small margin error of accuracy is acceptable.
- For high dimensional datasets with complex features relationships, more complex models like Random Forest and Neural Nets should be prioritized.
- For large datasets with high dimensionality and feature irrelevance neural networks do a very good of learning a pattern and optimizing predictions.
- Neural Networks are also significantly more computationally expensive as compared to RF models, so unless feature irrelevance is very high, RF could still give us very similar performance.
- For very sparse datasets, Neural Networks will outperform Random Forest models and hence should be prioritized if complex models are being used
- For small datasets, complex models do not generalize well beyond training data, so if scoring metrics are not a very huge concern and computing resources are limited, simpler linear models make a better choice.








