# Module 12 Report Template

## Overview of the Analysis

In this section, describe the analysis you completed for the machine learning models used in this Challenge.

**Explain the purpose of the analysis.**

The objective of this analysis was to develop a machine learning model to assess loan risk, to accurately identify low-risk and high-risk borrowers.

**Explain what financial information the data was on, and what you needed to predict.**

The data was provided on a .csv file which included information such as loan size, interest rate, borrower income, debt-to-income ratio, number of accounts, derogatory marks, and total debt.

**Provide basic information about the variables you were trying to predict (e.g., `value_counts`).**

The variable we were trying to predict was loan_status. Whether a loan was predicticted to be low risk(0) or high risk(1)

**Describe the stages of the machine learning process you went through as part of this analysis.**

`(1)Data processing:`- Checking for missing or null values using and removing them.Ensuring data types are correctly formatted while checking for duplicate or inconsistent entries.Removal irrelevant features and creating new features as needed.

`(2)Splitting datainto training and testing sets:`- To assess model performance, the dataset is divided into training and test sets:
*-(80%) of tha  data went to `training set` to train the machine learning model.
*-(20%)of the data went to `testing set`  to evaluate how well the model generalizes to unseen data.

`(3)Training a logistic regression model:`we train a logistic regression model using the logistic regression equation which calculates the probability of risk and makes determination/classsification. It does this by learing the the relationship of the x and y predictor variables.

`(4)Evaluate Accuracy, Precision, Recall and F1-Score:`After training the model, assess its performance using the following classification metrics:
*-Accuracy: Measures overall correctness of predictions.
*-Precision: How many predicted positive cases are actually correct
*-Recall: How many actual positive cases were correctly identified
*-F1-Score: Balances precision and recall—important for imbalanced datasets.

**Briefly touch on any methods you used (e.g., `LogisticRegression`, or any other algorithms).:**

I used `class_weight="balanced"` to ensure the model didnt favor one class over the other. In the dataset there are significantly fewer high-risk loans vs low-risk loans. If left unchecked theis would have heavily favored the the dominant classs(low-risk loans)using `class_weight="balance"` gives equal importance to high-risk and low-risk loans.


## Results

**Using bulleted lists, describe the accuracy scores and the precision and recall scores of all machine learning models.**

* Machine Learning Model 1:

`Logistic Regression Model Performance:`

Accuracy: 99%

Precision:
 Low-Risk Loans (0): 1.00- Almost perfect classification of low-risk loan
 High-Risk Loans (1): 0.85- Some false positives, meaning a few low-risk loans were mistakenly classified as high-risk
- 
Recall:
 Low-Risk Loans (0): 0.99- most low-risk loans were correctly identified 
 High-Risk Loans (1): 0.99- most high-risk loans were correctly identified 
 
F1-Score:
Low-Risk Loans (0):1.00-near perfect balance between precision and recall for low-risk loans
High-Risk Loans (1):0.92-strong balance between precision and recall for high-risk loans 


## Summary

**Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. For example:**

The logistic regression model performed very well, with an accuracy of 99% and high recall for high-risk loans (0.99), meaning very few risky loans were missed.


**Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s? )**

 The performance does depend on the problem we are trying to solve.In this scanario identifying high-risk loans is the priority, the model’s high recall ensures minimal false negatives, which is critical for financial risk management. This can allow financial institutions to minimize defaults and avoid approving loans that borrowers may struggle to repay.


**If you do not recommend any of the models, please justify your reasoning.**

The logistic regression model is suitable for deployment, though fine-tuning precision for high-risk loans could further improve results.
