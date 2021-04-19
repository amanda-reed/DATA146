## Project 5 Part 1

### Regression over Dataset with WealthC as Target

In the preprocessing stage, I checked for and removed nan values in the data, which appeared in approximately 80 observations. Because the dataset consists of about 48000 observations, the removal of 80 did not significantly impact the data modeling.

#### Linear Regression

To perform a linear regression, I set up my DoKFold function ([described here](midterm.md)) ([described here](#question-18)) ([described here](midterm.md#question-18)) and set the number of folds to 20. It is important to note that I changed the k value several times but did not see a significant change in the MSE and R^2 values. To continue, I ran the linear regression with 20 folds for the standardized and unstandardized dataset. The unstandarized set had a minimum testing MSE value of 0.41745 and an average testing MSE value of 0.44376. Likewise, the standardized data had a minimum testing MSE value of 0.42096 and an average of 0.44378. Even after standardizing the data, both regression performed relatively similarly. 

Upon calculating the correlation matrix for the data, I found that that of the original dataset and the standardized set were the same.

#### Ridge Regression



#### Lasso Regression

### Regression over Dataset with WealthI as Target

#### Linear Regression

Similarly to the Linear Regression when WealthC was the target, I ran the linear regression over the original dataset and standardized data with 20 folds. After running the regression, I found that the minimum testing MSE was 1.6x10^9 and the average was 1.7x10^9. Likewise for the standaridized set, the minimum was 1.6x10^9 and the average was 1.7x10^9. The significant shift in MSE values is likely due to the change in range of numbers of the target variable. Where WealthC had a range of (1,5), WealthI had a range of approximately (-150000, 475000). 

As with WealthC as the target, the correlation coefficients did not change after standardizing the data.

#### Ridge Regression

#### Lasso Regression

images
1: lasso reg wealthc 0.001 0.734441362468904 0.7337891277301398 0.4451243595089821 0.44583162965134593 (0.001, .4, 50)
2: rid wealth c 13.848484848484848 0.7357905749695652 0.7352802601759661 0.4428637774829151 0.44366867017988804 (13, 15, 100)

