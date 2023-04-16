# Credit Risk Classification Report

## Overview of the Analysis
The purpose of this analysis is to develop a logistic regression model to determine whether loans are healthy or high-risk.

The data set contains information on each loan, such as loan size, interest rate, borrower income, loan status etc. There are a total of about 77000 loans in the data set. The logistic regression model needs to predict the loan status of the loans, the result of which will be compared with the actual loan status. The loan status of a loan indicates whether a loan is a healthy loan or a high-risk one.

The following steps are involved:
1. Read in the data set from the CSV file into a Pandas dataframe.
2. Create the labels set (`y`)  from the “loan_status” column, and then create the features (`X`) DataFrame from the remaining columns.
3. Split the data into training and testing datasets by using `train_test_split`.
4. Create a logistic regression model and fit it with the original training data using the LogisticRegression module.
5. Use the model to predict the loan status using the testing data.
6. Evaluate the model’s performance by means of an accuracy score, a confusion matrix and a classification report using the respective modules from sklearn.metrics.
7. Use the `RandomOverSampler` module from the imbalanced-learn library to resample the training data so that the labels have an equal number of data points (equal number of healthy and high-risk loans).
8. Create another logistic regression model and fit it with the resampled training data using the LogisticRegression module.
9. Use the model to predict the loan status using the same original testing data.
10. Evaluate the model’s performance by means of an accuracy score, a confusion matrix and a classification report using the respective modules from sklearn.metrics.

## Results
* Machine Learning Model 1:
  * For high-risk loans
    * The model has a recall of 0.89, which means that for all high-risk loans, 89% of them are classified by the model as high-risk.
    * It also has a precision of 0.87, which means that for all loans classified by the model as high-risk, 87% of them are indeed high-risk.
  * For healthy loans
    * It has a precision of 1, which means that for all loans classified by the model as healthy, almost all are indeed healthy loans.
    * It also has a recall of 1, which means that for all healthy loans, almost all of them are classified by the model as healthy.
  * Overall, the model has a balanced accuracy of 0.94.

* Machine Learning Model 2:
  * For high-risk loans
    * The model has a recall of 1, which means that for all high-risk loans, almost all of them are classified by the model as high-risk.
    * Similar to the previous model, it also has a precision of 0.87, which means that for all loans classified by the model as high-risk, 87% of them are indeed high-risk.
  * For healthy loans
    * Similar to the previous model, it has a precision of 1, which means that for all loans classified by the model as healthy, almost all are indeed healthy loans.
    * Similar to the previous model, it also has a recall of 1, which means that for all healthy loans, almost all of them are classified by the model as healthy.
  * Overall, the model has a balanced accuracy of 0.996.

## Summary
Machine Learning Model 2 has a higher recall for high-risk loan and a higher overall accuracy as compared to the first model. Machine Learning Model 2 is recommended over the first model because it has a much higher recall for high-risk loan and therefore is able to more accurately classify all actual high-risk loans as high-risk. This is really useful if we want to use the model to determine whether a loan is potentially high-risk. However, we should note that regardless of which model we use, about 13% of healthy loans may be wrongly classified as high-risk, which may or may not be acceptable depending on the use case.
