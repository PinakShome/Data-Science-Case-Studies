## Project Title: Automated Tag Prediction for StackOverflow Questions

## 1. Objective

The primary objective of this project is to construct a machine learning model that can predict appropriate tags for a given StackOverflow question. The model accomplishes this by learning from the text of the question.

## 2. Getting Started

2.1 Prerequisites
This project has been implemented in Python. The following libraries are required:

numpy
pandas
sklearn
matplotlib
seaborn
nltk
datetime
joblib

## 3. Implementation

## 3.1 Dataset Exploration
The first step of the implementation involves exploring the dataset to understand data distributions and correlations. This exploration utilizes visualizations created with matplotlib and seaborn.

## 3.2 Data Preprocessing
In this stage, several steps are performed on the data:

The title and body of the question are combined.
All HTML tags are removed.
Punctuation and special characters are eliminated.
All words are converted to lowercase.
Stopwords are removed.
Words are lemmatized.

## 3.3 Feature Extraction
This step involves transforming the text data into a format understandable by the machine learning algorithm. In this project, the bag of words model is used, with features extracted using CountVectorizer.

## 3.4 Train-Test Split
The dataset is divided into a training set (80% of total data) and a test set (20% of total data).

## 3.5 Model Training
Two models are trained in this project:

Logistic Regression with More Title Weight
Logistic Regression with L1 Penalty
3.6 Model Evaluation and Results
After training, the models are evaluated on the test dataset and performance metrics are calculated.

## 3.6.1 Logistic Regression with More Title Weight

This model's training takes approximately 10 minutes and 14 seconds, and the performance metrics are as follows:

Accuracy: 0.25108
Hamming loss: 0.00270302
Micro-average quality numbers: Precision: 0.7172, Recall: 0.3672, F1-measure: 0.4858
Macro-average quality numbers: Precision: 0.5570, Recall: 0.2950, F1-measure: 0.3710
These results suggest that the model has a decent degree of accuracy, but there is room for enhancement.

## 3.6.2 Logistic Regression with L1 Penalty

The second model uses Logistic Regression with L1 Penalty. The OneVsRestClassifier is employed in conjunction with this logistic regression model. Upon computing performance metrics, a classification report is printed for further evaluation.

## 3.7 Summary

This project demonstrates that machine learning techniques can automate the process of assigning tags to StackOverflow questions. The model performance could be further improved with more sophisticated techniques and additional data.

## 3.8 Running the Code

To run this project, execute the Jupyter Notebook cells in sequence. Since the output of each cell is dependent on the previous ones, they must be run in order.
