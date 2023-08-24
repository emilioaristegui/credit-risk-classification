# Module 20 Report 

## Overview of the Analysis

In this section, describe the analysis you completed for the machine learning models used in this Challenge. This might include:

* Explain the purpose of the analysis.
The objective of the analyis is to use diverse methods to train and assess a model focused on predicting loan risk by using a dataset containing historical records of lending
transactions from a peer-to-peer lending platform, the goal is to create a model capable of determining the creditworthiness of borrowers.

* Explain what financial information the data was on, and what you needed to predict.
The financial information was on loan sizes, interest rates, borrower income, debt to income, number of accounts, derogatory marks, total debt and loan status to predict
creditworthiness. 

* Provide basic information about the variables you were trying to predict (e.g., `value_counts`).
The analysis is a binary classification problem related to loan risk prediction and the target variable is loan_status. By using the value_counts() function, we can get the basic
information of the variables to count the occurrences of each  value in the loan_status column. 

* Describe the stages of the machine learning process you went through as part of this analysis.
- Data Loading and Exploration:
Loaded the lending data from a CSV file and exploring its structure. Examine variables, data types, and basic statistics to understand of the dataset.
- Data Preprocessing:
Separated the data into labels and features, assigning the target variable to y (loan_status) and the remaining variables to X (features). Then split the data into training and testing
sets using train_test_split function.
- Model Evaluation (Original Data):
Evaluated the model's performance using various metrics by calculating the accuracy score, a confusion matrix, and printing the classification report. The steps predicted both healthy
(0) and high-risk (1) loans.

* Briefly touch on any methods you used (e.g., `LogisticRegression`, or any resampling method).
- Model Building (Logistic Regression):
Instantiated and trained a Logistic Regression model using the original training data by fitting the model with the X_train and y_train datasets to make predictions on the testing data
(X_test).
- Resampling for Class Imbalance:
For class imbalance, we used the RandomOverSampler to resample training data, to assure equal number of instances for both classes, which improved the model's ability to predict
high-risk loans accurately.
- Model Building and Evaluation (Resampled Data):
Repeated the process of model building and evaluation using the resampled training data. Instantiated and trained a Logistic Regression model, made predictions on the testing data, and
evaluated the model's performance using the balanced accuracy score, confusion matrix, and classification report.

## Results

Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all machine learning models.

* Machine Learning Model 1:
  * Description of Model 1 Accuracy, Precision, and Recall scores.
Classification Report:
               precision    recall  f1-score   support

           0       1.00      1.00      1.00     15001
           1       0.86      0.91      0.88       507

    accuracy                           0.99     15508
   macro avg       0.93      0.95      0.94     15508
weighted avg       0.99      0.99      0.99     15508

* Machine Learning Model 2:
  * Description of Model 2 Accuracy, Precision, and Recall scores.
Classification Report (Resampled):
               precision    recall  f1-score   support

           0       1.00      0.99      1.00     15001
           1       0.85      0.99      0.92       507

    accuracy                           0.99     15508
   macro avg       0.93      0.99      0.96     15508
weighted avg       1.00      0.99      0.99     15508

## Summary

Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. For example:
* Which one seems to perform best? 
The second model seems to perform best for high-risk loans and the first one performs better for healthy loans
* How do you know it performs best?
Well, each serves better for a specific purpose, there isn't one that meets the whole criteria by a wide margin
* Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s? )
Yes, we are seeking for two different things, which are high-risk loans and healthy loans.
If you do not recommend any of the models, please justify your reasoning.
I recommend the first one for healthy loans and the second one for high-risk loans.
