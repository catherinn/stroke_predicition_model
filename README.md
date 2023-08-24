# stroke_prediction_model

## Installation (local)
* Activate a virtual environment 
* Install requirements

```
pip install -r requirements.txt
```


## Context
According to the World Health Organisation (WHO), stroke is the 2nd leading cause of death globally, responsible for approximately 11% of total deaths.

## Scope
This repository contains the code to data analysis of underlying factors that lead up to stroke and finding a ML model that is able to predict whether a patient is likely to get a stroke based on input parameters like gender, age, various diseases and smoking status. The focus is on trying out different techniques.


## Dataset used
You can find the original dataset in the stroke_data.csv file. The data contains information about:
1) id: unique patient identifier
2) gender: “Male”, “Female” or “Other”
3) age: age of the patient
4) hypertension: 0 (if the patient doesn’t have hypertension) or 1 (if the patient has hypertension)
5) heart_disease: 0 (if the patient doesn’t have a heart disease) or 1 (if the patient has a heart disease)
6) ever_married: “No” or “Yes”
7) work_type: “children”, “Govt_job”, “Never_worked”, “Private” or “Self-employed”
8) Residence_type: “Rural” or “Urban”
9) avg_glucose_level: average glucose level in the blood
10) bmi: body mass index
11) smoking_status: “formerly smoked”, “never smoked”, “smokes” or “Unknown” (in
this case the information for the patient is not available)
12) stroke: 1 (if the patient had a stroke) or 0 (if the patient didn’t have a stroke)


## Proposed algorithms
Various algorithms and feature engineering and selection techniques were used in the notebook:

**Main classification algorithms:**
  * Logistic Regression
  * Multilayer Perceptron
  * Decision Tree
  * Random Forest
  * K-nearest Neighbours
  * Support Vector Classification
  * Gaussian Naive Bayes 
  * AdaBoost 
  * GradBoost
  * XGBoost

**Techniques and experiments:**
  * pipelines 
  * ColumnTransformer with separate dealing with categorical and numerical data
  * sample balancing techniques (SMOTE, underbalancing)
  * various scalers (MinMaxScaler, StandardScaler, RobustScaler)
  * validation and testing techniques: cross-validation on training set with ROC AUC; classification report, confusion matrix on testing set
  * PCA
  * manual outlier removal
  * GriDSearchCV hyperparameter tuning on 2 best performing models (Logistic Regression, SVC)


## Conclusion
The best performing model achieved was Logistic Regression with 0.84 accuracy (ROC AUC). 
While the initial models have achieved higher accuracy (around 0.95), due to the highly imbalanced character of the dataset (minority for stroke == 1), these models are tuned to predict stroke == 0. However, they perform very poorly for stroke == 1 which is the goal of this study. 

The model that I have reached is still weak and is not usable in commercial usage. It has been tuned for achieving as good predictions for stroke == 1 as possible, specifically focusing on recall. I consider the of false negatives (predicting no stroke when it should be yes) much higher than for false positives (predicting stroke when there is none) as focusing on prevention and regular check ups is not causing any harm, while not predicting a stroke has severe consequences.

The overall conclusion and so the ultimate next step would be to collect further samples of patients with stroke == 1 as the sample given is highly imbalanced and only contains 249 samples for stroke == 1. As our goal is to predict when a person will get stroke, this is definitely not enough to build a high accuracy model.

## References
