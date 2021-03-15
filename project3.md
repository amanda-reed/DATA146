## Project 3

#### KFold Linear Regression Model for Charleston Home Asking Price

To train and test the model for the data from ```charleston_ask.csv```, I set the target as the price variable and the features as the number of beds, baths, and square feet of the property. When testing and training a model using KFold, I split the data into a number of different folds, ranging from 7 to 25. All had similar results:

| number of folds | testing score | training score |
| --------------- | ------------- | -------------- |
| 7 | 0.019 | -0.051 |
| 10 | 0.019 | -0.049 |
| 15 | 0.019 | -0.123 |
| 20 | 0.019 | -0.106 |
| 25 | 0.019 | -0.042 |

In general, though the training score fluctuated slightly as the number of folds changed, there was no significant improvement of training or testing scores as the number of folds increased. In addition, the overall scores were not indicative of a well performing model. 

#### Standardizing Features

The previous results of creating a Linear Regression model were unsuccessful in producing a good model of the data, likely in part due to the range of numbers of area of property in square feet, which was much greater than that of the other two features. In an effort to try to improve testing and training scores, I standardized the features of the model using StandardScalar. After scaling the features, I ran a KFold linear regression loop over the data. 

| number of folds | testing score | training score |
| --------------- | ------------- | -------------- |
| 7 | 0.020 | -0.008 |
| 10 | 0.020 | -0.011 |
| 15 | 0.019 | -0.034 |
| 20 | 0.019 | -0.075 |
| 25 | 0.019 | -0.184 |

Though the results improved slightly, standardizing the features of the model did not significantly improve the testing and training scores. Thus, another type of regression or the use of more variables may help improve the model.

#### Ridge Regression Model

Rather than use a Linear Regression Model, I tried a Ridge Regression, which would find the optimal alpha value for the model. 

| number of folds | testing score | training score | testing score (S) | training score (S) |
| --------------- | ------------- | -------------- | ---| --- |
| 7 | 0.019 | 0.005 | 0.020 | 0.000 |
| 10 | 0.020 | -0.065 | 0.019 | -0.018 |
| 15 | 0.019 | -0.072 | 0.019 | -0.043 |
| 20 | 0.019 | -0.159 | 0.019 | -0.126 |
| 25 | 0.019 | -0.115 | 0.019 | 0.171 |
FIX chart above irrelevant



