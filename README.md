# Bank-deposit-subscription
Predict whether customers subscribe a term deposit based on 20 attributes (categorical and numerical data). 

## The data
The source of the data was from http://archive.ics.uci.edu/ml/datasets/Bank+Marketing.  I used the data in "bank-additional-full.csv" file. The description of attributes are in "bank-additional-names.txt". 

The data was cleaned and scaled as described in "Bank deposit subscription--data-processing.ipynb"

## Balanced and unbalanced data
There are 30488 instances in the data set.  Customers didn't sign up term deposit in 26629 instances as class 0. Customers signed up term deposit in 3859 instances as class 1 (12.65%). The data is unbalanced.  To make the data more balanced, I randomly selected 10000 instances of class 0 and all class 1 instances.  That changed class 0/class 1 ratio from 6.9 to 2.6.     

## The Classification Models

I used (1) SVM.SVC, (2) random forest, (3) logistic regression and (4) neaural network for the classification. I used different parameter settings to train the model with the traiing data. The model performances on cross-validation data was used to select settings for each classification methods.  Each model with their best settings was used on the test data.  The results from different models on test data were compared.   
