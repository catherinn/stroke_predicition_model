# stroke_prediction_model

## Installation (local)
* install Rstudio - the analysis was done with version RStudio Version 2023.03.0+386
* install the packages as defined in the .rmd file
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

**Main techniques and algorithms used:**
  * Exploratory Data Analysis: The analysis includes several visualizations and summaries to understand the data and relationships between variables
  * Survival analysis: Computing and plotting the survival and hazard functions incl comparing multiple groups
  * Univariate and multivariate Cox Model


## Conclusion
After the analysis, we can get the following conclusions:
1)	The dataset contains information about various variables, including the number of investigators, funding awarded, funding years, estimated sample size, time to protocol paper publication, event of protocol paper publication, time to main paper publication, and event of main paper publication. The dataset consists of 74 observations.
2)	The data was relatively clean, but some steps were required to handle missing values and convert certain variables from character to numeric format (estimatedSampleSize).
3)	Exploratory Data Analysis: The analysis includes several visualizations and summaries to understand the data and relationships between variables. We can say that there is homogenous correlation between almost all variables.
4)	The publication of a protocol paper does not seem to have a significant impact to the main event.
5)	Survival analysis techniques were applied to understand the time to chance of main event (i.e. publication of the main paper) and the factors influencing it. We notice that:
   *	The survival function indicates that only 50% of the sample publishes a paper within the observed time. The hazard function provides the instantaneous probability of publishing a paper at any given time.
   *	The impact of individual covariates on the main event was assessed using univariate Cox models. Only fundingYears was shown to have a significant impact.
   *	A multivariate Cox model was built, including fundingYears, timeToProtocol and eventProtocol. These variables remained significant, indicating that longer fundingYears, longer timeToProtocol, and negative eventProtocol increase the risk of not publishing a main paper.
   * FundingYears, timeToProtocol, and eventProtocol have were shown to have significant impact on the main event.
   * Longer FundingYears, timeToProtocol are associated with a decreased likelihood of publishing a main paper.
   * The publication of a protocol paper seems to have a positive impact on the likelihood of publishing a main paper, although results are not statistically significant.
   * The number of investigators, the amount of the funding awarded, and the estimated sample size did not show a significant impact on the time to main event.


## References
The original paper on the topic: https://bmjopen.bmj.com/content/7/3/e012212x`
