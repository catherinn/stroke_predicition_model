# stroke_prediction_model

## Installation (local)
* Activate a virtual environment (this version was tested with python xy)
* Install requirements

```
pip install -r requirements.txt
```


## Context
According to the World Health Organisation (WHO), stroke is the 2nd leading cause of death globally, responsible for approximately 11% of total deaths.

## Scope
This repository contains the code to build a ML model that is able to predict whether a patient is likely to get a stroke based on input parameters like gender, age, various diseases and smoking status. 


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

## Conclusion

## References
