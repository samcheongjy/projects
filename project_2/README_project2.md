# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 2: Ames Housing Data and Kaggle Challenge

### Project Overview

The purpose of this project is to predict the sales price for each house. For each Id in the test set, we will predict the value of the SalePrice variable.

### Evaluation

Kaggle leaderboard standings will be determined by root mean squared error (RMSE).

### Data Set Used

There are three files:

- **train.csv** -- this data contains all of the training data for your model.
  - The target variable (`SalePrice`) is removed from the test set! 
- **test.csv** -- this data contains the test data for your model. You will feed this data into your regression model to make predictions.
- **sample_sub_reg.csv** -- An example of a correctly formatted submission for this challenge (with a random number provided as predictions for `SalePrice`. Please ensure that your submission to Kaggle matches this format.

## **Summary**

My submission was made on Kaggle. My best model has a Root Mean Squared Error of 30,145.12 against the Kaggle test data.

The following are scores obtained from my training and holdout data:

| Metric                                      | Score      |
| ------------------------------------------- | ---------- |
| **R2 Score (Train Data)**                   | 91.92%     |
| **R2 Score (Holdout Data)**                 | 91.63%     |
| **Cross Value Score, 5 Folds (Train Data)** | 84.76%     |
| **Root Mean Squared Error**                 | $22,473.26 |
| **Mean Absolute Error**                     | $16,249.43 |
| **Mean of Residuals**                       | -$450.86   |

[![img](https://github.com/.png)](https://github.com/aejsong/psv-ameshousing/blob/master/assets/Project2_README-2941dddd.png)

## Contact

**Team Lead (Contact) : [Samuel Cheong](https://github.com/samcheongjy)(@SamuelCheong)**



