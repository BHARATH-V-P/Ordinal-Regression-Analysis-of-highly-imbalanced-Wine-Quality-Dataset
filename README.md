# Ordinal-Regression-Analysis-of-highly-imbalanced-Wine-Quality-Dataset

This project involves building a classification model to predict the quality of wine based on various chemical properties. The aim is to analyze feature relevance for specific classes given the highly imbalanced nature of the dataset, optimize models to help improve class predictability, and visualize specific patterns in feature distribution from the dataset. The problem at hand is treated as an Ordinal Regression problem where the main objective is to improve the Cohen's Kappa Score. The overall dataset is highly imbalanced with all of its initial predictors existing as numerical continuous variables.

## Table of Contents

- [Introduction](#introduction)
- [Installation](#installation)
- [Usage](#usage)
- [Feature](#feature)
- [Results](#results)
- [License](#license)

## Introduction

Creating a tuned prediction model to determine the quality of wine based on the available independent predictors that categorize the data records broadly based on specific chemical properties. Identifying the data source of the available training set and verifying its similarity with the original dataset is crucial to understand how much of the information is available for model training. The overall dataset is highly imbalanced, with class contributions going as low as 0.5%. The project involves identifying features that best help train the model by reducing any possible uneccessary influence by irrelevant data features. A cross-validation strategy is deployed to help get a better estimate of the reliability of the models. Direct correlation of features helps give a brief idea of the importance of specific features in correctly classifying the minority classes. Performing feature impact analysis methods such as leave one out and feature selection helps determine feature importance and contribution towards making reliable predictions. Some of the model types used for machine learning include SVC, Random Forest Classifier, XGB Classifier, and LGB Classifier. The primary KPI selected for evaluation throughout the project is the Cohen Kappa Score.

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
3. Open the Jupyter Notebook: jupyter notebook "WINE_ORDINAL_REG_final.ipynb"
   The script will:
   - Preprocess the raw data
   - Perform relevant EDA to compensate for the absence of minimum variabaility pretaining to certain classes and the heavy imabalance observed in the dataset.
   - Train and evaluate models
   - Perform neccessary feature engineering and feature seleciton using RFECV
   - Perform Hyperparameter tuning to try and improve model performance
   - Prioritize feature  importance for individual models
   - Keep track of specific KPI metrics such as precision_recall curve and rov_curves to understand model behavior for specific preprocessed datasets
5. Review the results:
   Evaluation Metrics: Found in results/evaluation_metrics.txt
   Predictions: Found in results/predictions.csv

## Features
   - Data Preprocessing: Handles missing values, normalization.
   - Insightful Visualizations to better understand the imabalanced dataset.
   - Get statistical overview of the features involved
   - Evaluate the effecct of different transformation techniques given that all independent variables were continuous numerical.
   - Model Training: Utilizes Logistic Regression, Random Forest Classification, XGBoost , and LGB.
   - Create custom metrics to aid better results from Bayesian Optimization
   - Model Evaluation based on the quality of fitting during data trianing
   - Develop a Voting Classifier to improve overall predictability.

## Results

   ### Baseline Model Performance
   ---------------------------------------------------------------------------------
   The following models were evaluated to establish baseline performance:
   
   - Logistic Regression: Achieved an accuracy of 56.3% with a Cohen Kappa Score of 0.45 and a Logloss of 1.038.
   - SVC (Support Vector Classifier): Showed an accuracy of 55.5%, with a Cohen Kappa Score of 0.46 and Logloss of 1.036.
   - Random Forest Classifier: Had the highest accuracy at 59.2%, a Cohen Kappa Score of 0.55, and Logloss of 1.117.
   - XGB Classifier: Delivered an accuracy of 56.9%, with a Cohen Kappa Score of 0.53 and a Logloss of 1.194.
   - LGB Classifier: Reported an accuracy of 57.8%, Cohen Kappa Score of 0.51, and Logloss of 1.238.
   - Oversampling (os), undersampling (us), and combined methods (os_us) were applied to various models, showing generally lower performance compared to the 
     baseline models.
   
   ### Feature Impact Analysis
   ---------------------------------------------------------------------------------
   Analysis was conducted to evaluate the impact of removing specific features:
   
   - Fixed Acidity: Removal led to a decrease in performance across all models, particularly affecting Random Forest and LGB models.
   - Volatile Acidity: Generally had a negative impact, with notable reductions in accuracy and increases in Logloss.
   - Citric Acid: Removing this feature tended to decrease performance in Random Forest and XGB models.
   - Residual Sugar: Results varied, with some models performing better without this feature.
   - Chlorides, Free Sulfur Dioxide, Total Sulfur Dioxide: Removal of these features showed mixed effects, with some models benefiting while others experienced 
     reduced performance.
   
   ### Principal Component Analysis (PCA) Results
   ---------------------------------------------------------------------------------
   PCA was used to analyze the impact of dimensionality reduction on model performance:
   
   - Top Features: Models with 'Fixed Acidity', 'Volatile Acidity', and 'Total Sulfur Dioxide' showed varying results. Removing certain combinations resulted in 
     improved performance metrics for Random Forest, XGB, and LGB classifiers.
     
   ### Evaluation Metrics for LGB Model- Hyperparameter Tuned
   ---------------------------------------------------------------------------------
   
   - Performance of the LGB model with different tuning methods:
   
      - Bayesian Hyperopt (Original Dataset): Accuracy: 0.583, Cohen Kappa: 0.534, Log Loss: 1.507
      - Optuna (Cross-Validation): Accuracy: 0.589, Cohen Kappa: 0.530, Log Loss: 1.259
      - Bayesian Hyperopt (Oversampled Dataset): Accuracy: 0.841, Cohen Kappa: 0.953, Log Loss: 0.462
        
   ### Voting Classifier Evaluation
   ---------------------------------------------------------------------------------
   - Hard Voting: Accuracy: 0.588, Cohen Kappa: 0.560
   - Soft Voting: Accuracy: 0.589, Cohen Kappa: 0.562
   - Soft Voting with Weights (Best Model): Accuracy: 0.595, Cohen Kappa: 0.568
     
## License

   This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
