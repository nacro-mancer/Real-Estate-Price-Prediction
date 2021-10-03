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







