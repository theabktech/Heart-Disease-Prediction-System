# Heart Disease Prediction
## Based on Cleveland UCI Data
[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

This system can predict whether a patient can contract a heart
disease based on data.
## Database
The database has been taken from kaggle, based on data provided
by Cleveland UCI. It contains 303 rows and 13 columns and 1 label.

- age: age in years
- sex: sex (1 = male; 0 = female)
- cp: chest pain type
-- Value 0: typical angina
-- Value 1: atypical angina
-- Value 2: non-anginal pain
-- Value 3: asymptomatic
- trestbps: resting blood pressure (in mm Hg on admission to the hospital)
- chol: serum cholestoral in mg/dl
- fbs: (fasting blood sugar > 120 mg/dl) (1 = true; 0 = false)
- restecg: resting electrocardiographic results
-- Value 0: normal
-- Value 1: having ST-T wave abnormality (T wave inversions and/or ST 
elevation or depression of > 0.05 mV)
-- Value 2: showing probable or definite left ventricular hypertrophy by Estes' criteria
- thalach: maximum heart rate achieved
- exang: exercise induced angina (1 = yes; 0 = no)
- oldpeak = ST depression induced by exercise relative to rest
- slope: the slope of the peak exercise ST segment
-- Value 0: upsloping
-- Value 1: flat
-- Value 2: downsloping
- ca: number of major vessels (0-3) colored by flourosopy
- thal: Thalassemia: A blood disorder called 'Thalassemia' 
-- 0 = normal
-- 1 = fixed defect
-- 2 = reversable defect
- condition: 0 = no disease, 1 = disease

You can find the database on this [link](https://www.kaggle.com/ronitf/heart-disease-uci).


## Tech

- Python - Google Colab/Jupyter Notebook
- Pandas library
- Numpy library
- H2O AutoML
- H2O Stacked Ensemble
- H2O GradientBoostingMachine

H2O has been used in this system for model exploration and feature selection.

## Feature Selection
Automatic Feature Selection technique has been used (original on kaggle).
The techniques used are -
- Pearson Correlation
- Linear SVC
- Lasso CV
- SelectKBest
- Regressive Feature Elimination using Logistic Regression
- Variance Threshold

## Models Used

- Stacked Ensemble 
-- GradientBoostingMachine
-- Random Forest
- Gradient Boosting Machine

### Stacked Ensemble
Stacked ensemble is made up of GBM and Random Forest. The data used here is completely
unadultrated. The data has been directly split up into train and test data using random
sample. Make sure you save the train and test data as csv and use the import file function
in H2O to import the file. Otherwise it will show error.
#### ModelMetricsBinomialGLM: stackedensemble
** Reported on test data. **
- MSE: 0.1262443225071656
- RMSE: 0.35530877065893773
- LogLoss: 0.39211292860497726
- Null degrees of freedom: 61
- Residual degrees of freedom: 59
- Null deviance: 87.33823102336312
- Residual deviance: 48.62200314701718
- AIC: 54.62200314701718
- AUC: 0.9052083333333333
- AUCPR: 0.8998449632217862
- Gini: 0.8104166666666666


### Gradient Boosting Machine
The data used in GBM is after feature engineering and selection. Once the process is done, 
save the data into csv and call it using importfile function in H2O.
#### ModelMetricsBinomial: gbm
** Reported on train data. **
- MSE: 0.174590790367034
- RMSE: 0.4178406279516558
- MAE: 0.3175680380336407
- RMSLE: 0.29333831652179715
- Mean Residual Deviance: 0.174590790367034

Happy predictions!!!

Also, feel free to contact me via email (kulshreshthabhinav@gmail.com) if you have any suggestions for the model or you find a model better than this.
