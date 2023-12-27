# Model Card

See the [example Google model cards](https://modelcards.withgoogle.com/model-reports) for inspiration. 

## Model Description

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

**Model Architecture:** 
The model uses the XGBoost algorithm and performs a regression analysis on the dataset.

## Performance

The model has a RMSE of 0.20 on the test set. The model was trained using 5-fold cross-validation on a training set comprised of 80% of the data. This means that the error, on average, is around $20,000 given that the standard unit of the target (median house value) is $100,000.

## Limitations

There are only 9 features and the dataset does not take into account common attributes that add or reduce value of a property, including finishes, size of property, energy-efficiency, etc. The model used performs feature engineering naturally on the attributes provided but cannot use feature data it does not have access to. 
A household is a group of people residing within a home. Since the average
number of rooms and bedrooms in this dataset are provided per household, these
columns may take surprisingly large values for block groups with few households
and many empty houses, such as vacation resorts.


