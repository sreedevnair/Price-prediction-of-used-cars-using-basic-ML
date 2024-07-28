# Price Prediction of Used Car using ML

In this project, we will predict a resonable price of used cars based on their features. 

This is a regression problem for which we will be using 2 models to predict the price, simple Linear regression model and Lasso regression model.

**Linear** regression is the most basic form, where the model is not penalized for its choice of weights. 

**Lasso** is a modification of linear regression, where the model is penalized for the sum of absolute values of the weights.

## Notes :-

### 1. Dateset Features :-
1. Car Brand
2. Year
3. Selling Price (Target Value)
4. Present Price
5. KMS Driven
6. Fuel Type
7. Seller Type
8. Transmission Type
9. Owner

### 2. `.isnull()` Function

This is function will return the complete DataFrame with True or False values. If the value is not present (i.e. a Null value), it will show True, otherwise False.

To check the total number of Null values present in the DataFrame, we use `.isnull().sum()`. This will return Series with the number of Null values in each column (feature).

### 3. `.value_counts()` Function

We use this function to check the occurences of unique values of a particular column.

### 4. Label Encoding

Label encoding is the process of converting categorial values (mostly string values) into numerical value.

In this DataFrame, the features with categorical values are :-
| Features | Possible Values |
| -------- | --------------- |
| Fuel_Type | Petrol, Diesel, CNG |
| Seller_Type | Dealer, Individual |
| Transmission | Manual, Automatic |

To this, we will use `.replace()` function of Pandas library.

### 5. Creating the Feature DataFrame and Target Series

To do this, we are simply dropping the ***Selling_Price*** (since that's our Target) and the ***Car_Name*** (since it's not useful for making any predictions.....for this basic project 😓) columns from the dataset to get the Feature DF and just selecting the ***Selling_Price*** column for our Target Series.

To drop the columns, we use the function `.drop()` and pass the list of columns that we want to drop as the parameter. We also have to mention the axis parameter. For removing a column we use ***axis=1***, and for removing a row we use ***axis=0***.

### 6. Splitting the data

Before we train the model, we need to split the data into 2 sets :-

1. Training set
2. Test or validating set.

To split the data, we are using the function `train_test_split()`.

We are passing 4 parameters in this function :-

1. The feature dataset
2. The target dataset
3. `test_size` : By default it's .25, which means 25% of the dataset will be used for testing and the other 75% for the training.
4. `random_state` : This is to make sure that our data split remains same during every execution.

### 7. Training the model

Here, we will train our model through Linear Regression and Lasso Regression. 

Linear Regression Model works better when there's a direct correlation between the feature and the target value.

We train and predict the model in the same way we train Decision Tree model or Random Forest model.

For evaluating the model, we have used the error metrics known as **R squared error**. The value of R-square lies between 0 to 1. 

When we get R-square equals 1 when the model perfectly fits the data and there is no difference between the predicted value and actual value.  

However, when we get R-square equals 0 when the model does not predict any variability in the model and it does not learn any relationship between the dependent and independent variables.


### 8. Conclusion

After training, predicting and evalutating both the models, the Lasso model did a better job at predicting the target compared to the Linear regression model. 

(But from an overall percpective, both of the model didn't scored much.....Bad Models 👎)

<br><br>

> This project was a complete walkthrough of this [tutorial](https://youtu.be/L3OtLaCbJC8?si=6w85H196xcsQnJgJ) by Siddhardhan.
