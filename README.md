# Real-Estate-Price-Prediction
## Overview
This is a market historical data for real state valuation collected from Taiwan. The calculation of real state value is a regression Problem. The data contains information about the transaction date, the age of house, the distance to nearest metro station, the number of convenience stores in a living circle on foot, and it’s geographical co-ordinates i.e. latitudes and longitudes.
The output is house price of unit area (10000 New Taiwan Dollar/Ping, where Ping is a local unit, 1 Ping = 3.3 meter squared).

## Data Overview
The inputs are as follows
X1=the transaction date (for example, 2013.250=2013 March, 2013.500=2013 June, etc.)
X2=the house age (unit: year)
X3=the distance to the nearest MRT station (unit: meter)
X4=the number of convenience stores in the living circle on foot (integer)
X5=the geographic coordinate, latitude. (unit: degree)
X6=the geographic coordinate, longitude. (unit: degree)

## Univariate Data analysis
### Categorical Variable
![image](https://user-images.githubusercontent.com/37978451/135767259-fde6d5b3-9b1c-4e19-a95a-cfc44dcde9cc.png)
The data is equally distributed for all the values, and there is no value which is too low.

### Continuous Variable
![image](https://user-images.githubusercontent.com/37978451/135767277-5f8e5fc0-477c-4d4c-b900-8f281c209100.png)
After treating outliers the data is equally distributed without much skewness or missing part.

## Bivariate Data analysis
### Cont. vs Cont.
#### Graphical
![image](https://user-images.githubusercontent.com/37978451/135767300-5d27310f-3f26-43fe-a08b-ef458a0db2d0.png)
![image](https://user-images.githubusercontent.com/37978451/135767301-0d248b69-6615-4cd0-af42-43742a15ec4a.png)
![image](https://user-images.githubusercontent.com/37978451/135767305-c9484490-c0ec-47f8-8a89-bb9ce9c21118.png)
![image](https://user-images.githubusercontent.com/37978451/135767306-48e61333-fa52-4a7d-9a22-ad8e78cb9583.png)

#### Statistical
For continuous predictors we created a correlation matrix and calculated the correlation values for the predictors with respect to the target variables and following values were obtained:
![image](https://user-images.githubusercontent.com/37978451/135767331-e2351fab-96c3-429f-b640-779dfd4b1364.png)

Based on the above correlation values all the three predictors were selected for further action.

### Cat. vs Cont.
#### Graphical
![image](https://user-images.githubusercontent.com/37978451/135767364-2a8e973a-6079-4664-8130-b037d15b6a26.png)
#### Statistical
For categorical predictors we used ANOVA test and calculated the P-Values for the predictors with respect to the target variables and following values were obtained:
![image](https://user-images.githubusercontent.com/37978451/135767384-35d1e67e-28fe-4187-9eea-fa4a543b444e.png)

Based on the above correlation values only X4 number of convenience stores for further action.

## Selecting Final Predictors
* X3 distance to the nearest MRT station
* X4 number of convenience stores
* X5 latitude
* X6 longitude

## Building Models
### Multiple Linear Regression
The first model we trained the data through is multiple linear regression.
Following are the observations from the model:
R2 Value is 0.5290934734185615
Mean accuracy on test data is 81.1743518830904%.
Median accuracy on test data is 85.29411764705883%.
The final Average accuracy of the model is 79.91%
In the graph red are the predicted values and blue are the actual values.
![image](https://user-images.githubusercontent.com/37978451/135767458-91bee732-d241-48f1-8faa-a5c35d7a75f7.png)

### Decision Tree Regressor
For decision tree we obtained highest accuracy at the max_depth of 7.
Following are the observations from the model:
R2 Value is 0.8837164818950756
Mean accuracy on test data is 82.61201951953554%.
Median accuracy on test data is 88.54166666666667%.
The final Average accuracy of the model is 83.59%
The graph shows the significance of the variables we used for building the model, the distance from nearest MRT station has most significance in the model, followed by longitude, latitude and number of convenience stores.
![image](https://user-images.githubusercontent.com/37978451/135767474-7479a4ba-fd75-482b-a96d-06ae528ce344.png)

### Random Forest
For Random Forest we obtained highest accuracy at the max_depth of 10 and 150 estimators.
Following are the observations from the model:
R2 Value is 0.9251785485918291.
Mean accuracy on test data is 85.46184807415054%.
Median accuracy on test data is 85.46184807415054%.
The final Average accuracy of the model is 85.67%
The graph shows the significance of the variables we used for building the model, the distance from nearest MRT station has most significance in the model, followed by longitude, latitude and number of convenience stores.

![image](https://user-images.githubusercontent.com/37978451/135767496-a1a4cbae-47ae-49da-b9f7-2583d6fd9c12.png)

### AdaBoost
For AdaBoost we obtained highest accuracy at the max_depth of 3,300 estimators, using a decision tree as a base estimator and keeping learning rate at 0.01.
Following are the observations from the model:
R2 Value is 0.7205230690408295.
Mean accuracy on test data is 83.68780992274554%.
Median accuracy on test data is 88.13559322033899%.
The final Average accuracy of the model is 83.57%
The graph shows the significance of the variables we used for building the model, the distance from nearest MRT station has most significance in the model, followed by longitude, latitude and number of convenience stores.
![image](https://user-images.githubusercontent.com/37978451/135767503-213f1348-5961-4a38-b62f-f726e7b6c86e.png)

### XGBoost
For XGBoost we obtained highest accuracy at the max_depth of 5,300 estimators, using a decision tree as a base estimator and keeping learning rate at 0.1.
Following are the observations from the model:
R2 Value is 0.8524953177199545.
Mean accuracy on test data is 86.8401829057531%.
Median accuracy on test data is 89.61038961038962%.
The final Average accuracy of the model is 85.76%
The graph shows the significance of the variables we used for building the model, the distance from nearest MRT station has most significance in the model, followed by longitude, latitude and number of convenience stores.
![image](https://user-images.githubusercontent.com/37978451/135767516-3a841bf4-a51c-4277-81dd-915c9e1792a9.png)

### KNN
For KNN we obtained highest accuracy at the number of neighbors at 5.
Following are the observations from the model:
R2 Value is 0.6882000552494039.
Mean accuracy on test data is 82.31480966115622%.
Median accuracy on test data is 87.94788273615636%.
The final Average accuracy of the model is 82.25%

## Observations
From the predictors significance charts we can observe that, the significance of variables from higher to lower is as follows:
X3 distance to the nearest MRT station
X6 longitude
X5 latitude
X4 number of convenience stores
Checking the accuracies for all the models, we have observed that XGBoost has the highest average accuracy of 85.76% followed by Random Forest (85.67%), Decision tree Regressor (83.59%), AdaBoost (83.57%), KNN (82.25%), Multiple Linear Regression (79.91%).

## Recommendatitions
From the predictor significance graph, we can conclude that people are more swayed by the presence of metro station in the neighborhood while making an investment in real-estate.
Real estate properties can be constructed keeping nearest metro station in mind so that more people can be attracted.
The properties can also be priced accordingly i.e. the one near the metro station to be priced higher and the one near the convenience store to be priced lower to attract more customers.
The city planning can be done better to include more metro stations. Metro stations can be constructed keeping in mind that the neighborhoods can have easy access to them.

## Conclusions
The regression models can be used in full fledged business applications and price of the new properties can be approximated based on the information given.

The Model can be deployed on the companies website so that customers can get a approximate values of the property based on the information they provide.

Different models have been used to identify the best suited model (XGBoost) for the application.
