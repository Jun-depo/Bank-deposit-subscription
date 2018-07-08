# Bank-deposit-subscription
Predict whether customers subscribe a term deposit based on 20 attributes (categorical and numerical data). 

## The data
The source of the data was from http://archive.ics.uci.edu/ml/datasets/Bank+Marketing.  I used the data in "bank-additional-full.csv" file. The description of attributes are in "bank-additional-names.txt". 

The data was cleaned and scaled as described in "Bank deposit subscription--data-processing.ipynb"

## Balanced and unbalanced data
There are 30488 instances in the data set.  Customers didn't sign up term deposit in 26629 instances (class 0). Customers signed up term deposit in 3859 instances (class 1, 12.65%). The data is very unbalanced.  To make the data more balanced, I randomly selected 3859 instances of class 0 and all class 1 instances.  That changed class 0/class 1 ratio from 6.9 to 1.     

## The Classification of deposit subscription: 
#### Classification methods used:
	(1) SVM.SVC; 
	(2) random forest;
	(3) logistic regression;
	(4) neaural network MLPClassifier 

#### Model training, selection and prediction: 
	(1) For each classification method, models were trainded with different parameter settings with the traiing data. 
	(2) Roc_auc_scores of the predictions on cross-validation data were used to select the best model for each classification method.  
	(3) Roc_auc_scores of the predictions from selected models on test data were compared. 
	(4) I classified both the balanced and original unbalanced data with step 1 through 3 mentioned above. The results were compared the results. 

## Conclusion: 
All models that trained with balanced data, performed better than the ones trained with unbalanced data.  
