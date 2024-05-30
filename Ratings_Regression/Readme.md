# INTRODUCTION
This case study explores the intricate details of how machine learning models differ in making predictions when the dataset used has characteristics which are partially (but not completely) favorable to all the models being implemented. Since a soccer database is being used here, it has significance in understanding how analytics of different characteristics can have an impact on the game. But mainly, this aims to provide a concise model selection recommendation when the features of the dataset don’t clearly fit the criteria of any specific model. It provides insights into what models would be most suited for a given task with computational and metric prediction accuracy constraints in mind.

# Table of Contents 

- Dataset Description
- Preprocessing and EDA
- Modelling
- Conclusion
- Recommendation

# DATASET DESCRIPTION

Taken from : https://www.kaggle.com/datasets/hugomathien/soccer
(10k rows after cleaning - Mid Sized). This was originally a sql database file. I’ve extracted two tables of all available for this case study. The general trend of this dataset is:
All higher value float64 variables contribute to a higher target variable rating.

### Anomaly: 
There are several instances of rows where the target variable values are higher even though most of their ‘float64’ magnitudes are lower, which tell us that the features are not necessarily strong indicators of the target. This makes it suitable for
analyzing how models would learn on datasets with no clear patterns and help us understand the nuances of how we can leverage model architectures when there is no clear-cut trends present.
