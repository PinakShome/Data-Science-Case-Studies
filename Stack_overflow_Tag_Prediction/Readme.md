# Stack Overflow Tag Prediction
This repository contains the project for predicting tags for questions posted on Stack Overflow using machine learning techniques. The primary goal is to suggest relevant tags based on the content of the question to improve user experience and facilitate better organization of questions.

# Table of Contents 
- Business Problem
- Machine Learning Problem
- Exploratory Data Analysis
- Preprocessing and Feature Engineering
- Modeling
- Future Work

# Business Problem

## Description 

Stack Overflow is a popular online community for developers to learn, share knowledge, and build their careers. The platform features questions and answers on various programming topics. Tags play a crucial role in categorizing questions and making them easily searchable.

# Problem Statement

The objective is to suggest relevant tags for a given question posted on Stack Overflow based on its content.

## Data

The dataset used for this project consists of questions from Stack Overflow. Each question includes a title, body, and tags.

## Type of Problem 

This is a multi-label classification problem where each question can have multiple tags.

## Performance Metric

- Micro-Averaged F1-Score: This is the weighted average of the F1 score of each class.
- Hamming Loss: The fraction of labels that are incorrectly predicted.

# Exploratory Data Analysis

## Data Loading and Cleaning 

- Data was loaded using Pandas and SQLite.
- Duplicate questions were identified and removed.
- Distribution of the number of tags per question was analyzed.
- The most frequent tags were identified using word clouds and bar plots.

## Analysis of Tags

- Total number of unique tags: 42,048
- The top 20 tags were visualized.

# Preprocessing and Feature Engineering

## Preprocessing

- Code snippets were separated from the body of questions.
- Special characters and HTML tags were removed.
- Stop words were removed, and words were stemmed using the Snowball Stemmer.

## Feature Engineering

TF-IDF vectorization was used to convert text data into numerical features.

# MODEL SELECTION

Several models were considered:

- MLkNN
- Logistic Regression with OneVsRest Classifier
- SGDClassifier with OneVsRest Classifier (final model)

## Model Training
The SGDClassifier with OneVsRest Classifier was trained on the featurized data. This model took approximately 6-7 hours to train.

# Future Work

- Improve the model by experimenting with different models and hyperparameters.
- Use more advanced models like transformers for better performance.
- Explore data augmentation techniques to improve the dataset quality.
- Implement a more efficient way to handle the large number of tags.

# Acknowledgments

- The data was sourced from the Kaggle competition: [Facebook Recruiting III - Keyword Extraction](https://www.kaggle.com/c/facebook-recruiting-iii-keyword-extraction/data)
- The project was inspired by various research papers and online resources related to multi-label classification.







