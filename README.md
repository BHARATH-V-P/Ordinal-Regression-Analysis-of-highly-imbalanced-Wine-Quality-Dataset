# Ordinal-Regression-Analysis-of-highly-imbalanced-Wine-Quality-Dataset

This project involves building a classification model to predict the quality of wine based on various chemical properties. The aim is to analyze feature relevance for specific classes given the highly imbalanced nature of the dataset, optimize models to help improve predictability, and visualize specific patterns from the dataset. The problem at hand is treated as an Ordinal Regression problem where the main objective is to improve the Cohen Kappa Score.

## Table of Contents
-[Introduction](#introduction)
-[Installation](#installation)
-[Usage](#usage)
-[Feature](#feature)
-[Results](#results)
-[License](#license)

## Introduction

Creating a tuned prediction model to determine the quality of wine based on the available independent variables that categorize broadly as chemical properties. Identifying the data source for training and verifying its similarity with the original dataset. The overall dataset is highly imbalanced, with class proportions going as low as 0.5%. The project involves identifying features that best help train the model with as much reduced noise as possible. A cross-validation strategy is deployed to help get a better estimate of the reliability of the models. Direct correlation of features helps give a brief idea of the importance of specific features in correctly classifying the minority classes. Some of the model types used for machine learning include SVC, Random Forest Classifier, XGB Classifier, and LGB Classifier. The KPI selected for evaluation is the Cohen Kappa Score.

## Installation

1. Clone The repository:
   git clone https://github.com/BHARATH11112222/Ordinal-Regression-Analysis-of-highly-imbalanced-Wine-Quality-Dataset

2. Navigate to project directory:
   cd Ordinal-Regression-Analysis-of-highly-imbalanced-Wine-Quality-Dataset

3. Install dependencies:
   pip install -r requirements.txt

## Usage
1. Prepare your dataset: Place your datasets in the data/ directory. Ensure it is named WineQT ----------ordinal regression.csv, wine_train.csv and
   wine_test.csv or adjust the script accordingly.
3. Open the Jupyter Notebook: jupyter notebook "WINE_ORDINAL_REG.ipynb"
   The script will:
   -Preprocess the raw data
   -Perform relevant EDA to compensate for the absence of minimum variabaility pretaining to certain classes and the heavy imabalance observed in the dataset.
   -Train and evaluate models
   -Perform neccessary feature engineering and feature seleciton using RFECV
   -Perform Hyperparameter tuning to try and improve model performance
   -Prioritize feature  importance for individual models
   -Keep track of specific KPI metrics such as precision_recall curve and rov_curves to understand model behavior for specific preprocessed datasets
5. Review the results:
   Evaluation Metrics: Found in results/evaluation_metrics.txt
   Predictions: Found in results/predictions.csv

## Features
   -Data Preprocessing: Handles missing values, normalization.
   -Insightful Visualizations to better understand the imabalanced dataset.
   -Get statistical overview of the features involved
   -Evaluate the effecct of different transformation techniques given that all independent variables were continuous numerical.
   -Model Training: Utilizes Logistic Regression, Random Forest Classification, XGBoost , and LGB.
   -Create custom metrics to aid better results from Bayesian Optimization
   -Model Evaluation based on the quality of fitting during data trianing

## Results
