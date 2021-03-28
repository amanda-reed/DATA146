## Midterm Corrections

#### Question 15

After loading the dataset and defining my DoKFold function (see [question 18](#Question-18)), I created a dataframe containing the features and target of the data. To find the correlation 
coefficients of each features variable as it was related to the target, I used the ```corr()``` function and found that Median Income (MedInc) had the highest correlation.

#### Question 16

To standardize the features of the dataset, I imported StandardScalar and used the ```fit_transform()``` function to standardize the features. Then I created a dataframe with the 
transformed data and added the target values to the dataframe. After calculating the correlations on the scaled set, I found that the correlations from the previous question
do not change. 

#### Question 17

To calculate the coefficient of determination, I used ```corrcoef()``` function from the NumPy library with the scaled feature variable identified in question 15, MedInc, as the 
feature and the original target from the dataset. I squared the correlation coefficient and rounded the value to 2 decimals places which resulted in a coefficient of determination
of 0.47.
```
np.round(np.corrcoef(x_scaled['MedInc'],y)[0][1]**2, decimals=2)
```

#### Question 18

Starting with a linear regression model, I ran my DoKFold function with the linear regression model as my specified model, with the parameters set as indicated in the question.

#### Question 19

#### Question 20

#### Question 21

#### Question 22

#### Question 23

#### Question 24
