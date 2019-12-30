# Car-Price-Pridiction-Problem
A Chinese automobile company Geely Auto aspires to enter the US market by setting up their manufacturing unit there and producing cars locally to give competition to their US and European counterparts. 
They have contracted an automobile consulting company to understand the factors on which the pricing of cars depends. Specifically, they want to understand the factors affecting the pricing of cars in the American market, since those may be very different from the Chinese market. The company wants to know:
Which variables are significant in predicting the price of a car
How well those variables describe the price of a car

Based on various market surveys, the consulting firm has gathered a large dataset of different types of cars across the Americal market. 
Business Goal 
You are required to model the price of cars with the available independent variables. It will be used by the management to understand how exactly the prices vary with the independent variables. They can accordingly manipulate the design of the cars, the business strategy etc. to meet certain price levels. Further, the model will be a good way for management to understand the pricing dynamics of a new market. 

# Data Prepration:
1. The Dataset consist of 26 columns and 205 rows.
2. It is a supervised learning approach as "Price" is our target variable.
3. Check the info and null values counts in the dataset
4. In the 'CarName' feature we are not interested in Name of the car models but only car companies. So we split the Manufacturers from there models and create a new column "company".
5. Some of the manufacturers name in the new column are spelt wrong which is to be edited.
6. Exploratory Data analysis to find out the pattern in the data. Heatmap is created to check the correlation of the current numerical  variables with the target variable.
7. Outliers analysis is done using boxplots for numerical features. As our we have very small data we cannot remove the outliers as it will result in loss of good chuck of data, instead we will cap the outliers to desired percentile.

# Data Prepration For Modelling:
1. To reduce the final number of variables, we can segregate sub-categories which are in very less percentage in one single category, this  will reduce the number of features we get after we form dummy variables.
2. Label Encoding for features that have two sub-categories and for scaling we've used MinMAx Scaler.
3. In our final dataset we end up with 42 features. Using this much variables with Linear Regression might not lead with desired results and removing a feature one by one will also take time to get good model. To save time we used Recursive Feature Elimination technique which give us some specific important variables for modelling.

# Modelling:
1. Statsmodels api is used for linear regression as it give us complete summary of all the statistical parameters.
2. To counter multicollinearity variance inflation factor of the features are calculated.
3. Features with high P-values greater than 0.05 and VIF (variance inflation factor) greater than 3.0 are dropped
4. Adjusted R2 score for training set 0.83 and for test score adjusted R2 score is 0.80

# Conclusion:
Through linear regression we got around 10 important features which are affecting the price of the cars in United States vehicle market. The data follows the linear relation with the target variables so linear regression was the first choice for modelling. We could also use Lasso Regression but it will take high computational time.
