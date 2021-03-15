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

#### Modeling Charleston Home Actual Price

| number of folds | testing score | training score | testing score (S) | training score (S) |
| --------------- | ------------- | -------------- | ---| --- |
| 7 | 0.004 | -0.009 | 0.004 | -0.013 |
| 10 | 0.004 | -0.023 | 0.004 | -0.023 |
| 15 | 0.004 | -0.022 | 0.004 | -0.032 |
| 20 | 0.004 | -0.041 | 0.004 | -0.019 |
| 25 | 0.004 | -0.052 | 0.004 | -0.051 |


additional var for act charleston
7
Training: 0.343
Testing: 0.245
7 Standardized
Training: 0.343
Testing: -77814180999270972260352.000
10
Training: 0.339
Testing: 0.267
10 Standardized
Training: 0.339
Testing: -206576642891184313729024.000
15
Training: 0.338
Testing: 0.240
15 Standardized
Training: 0.338
Testing: -32054759452135441563648.000
20
Training: 0.338
Testing: 0.215
20 Standardized
Training: 0.338
Testing: -34976869210638289731584.000
25
Training: 0.337
Testing: 0.223
25 Standardized
Training: 0.337
Testing: -320826115460251214938112.000

add var for ask charleston
7
Training: 0.282
Testing: 0.233
7 Standardized
Training: 0.282
Testing: 0.222
10
Training: 0.281
Testing: 0.224
10 Standardized
Training: 0.281
Testing: 0.194
15
Training: 0.280
Testing: 0.186
15 Standardized
Training: 0.280
Testing: 0.062
20
Training: 0.280
Testing: 0.111
20 Standardized
Training: 0.280
Testing: 0.066
25
Training: 0.279
Testing: -0.117
25 Standardized
Training: 0.279
Testing: -0.116

difference in model predictability likely due to variability/negotiations that can occur when selling a house while asking prices are likely based off of what other local homes have sold for or are currently on the market for
