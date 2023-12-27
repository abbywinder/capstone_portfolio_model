# CALIFORNIA HOUSING PREDICTION MODEL

The objective of the project is to be able to predict California house prices using previous house price data. In practice, the dataset is very outdated, having been collected in 1990, so would not provide any relevant predictions in 2023.

## DATA
**Input:** 
- MedInc        median income in block group
- HouseAge      median house age in block group
- AveRooms      average number of rooms per household
- AveBedrms     average number of bedrooms per household
- Population    block group population
- AveOccup      average number of household members
- Latitude      block group latitude
- Longitude     block group longitude

**Output:** 
The target variable is the median house value for California districts,
expressed in hundreds of thousands of dollars ($100,000).

## MODEL 
The model used is the XGBoost Regression algorithm, as it performed best by around 0.3 points on the validation set, as gathered by using 5-fold cross-validation.

## HYPERPARAMETER OPTIMSATION
Hyperparameters used are as follows:

'booster': 'dart',
'learning_rate': 0.0897756875591105,
'max_depth': 8,
'subsample': 0.8182283761327291,
'colsample_bytree': 0.7022052160044676,
'lambda': 0.7008253701931766,
'alpha': 0.26576879851376356,
'min_child_weight': 7

These hyperparameters were selected using Optuna Bayesian Optimisation over a course of 20 trials.


## RESULTS
The model performed well on the test set, with a RMSE of 0.20, meaning that predictions, on average, are around $20,000 from the value the properties were actually valued at, which is a relatively small error when valuing a property.

