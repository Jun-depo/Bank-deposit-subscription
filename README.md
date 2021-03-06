# Bank-deposit-subscription
Predict whether customers subscribe a term deposit based on 20 attributes (categorical and numerical data). 

## The data
The source of the data was from http://archive.ics.uci.edu/ml/datasets/Bank+Marketing.  I used the data in "bank-additional-full.csv" file. The description of attributes is in "bank-additional-names.txt". 

The data was cleaned and scaled as described in "Bank deposit subscription--data-processing.ipynb"

## Balanced and unbalanced data
There are 30488 instances in the data set.  Customers didn't sign up term deposit in 26629 instances (class 0). Customers signed up term deposit in 3859 instances (class 1, 12.65%). The data is very unbalanced.  To make the data more balanced, I randomly selected 3859 instances of class 0 and mixed with all class 1 instances.  That changed class 0/class 1 ratio from 6.9 to 1.     

## The Classification of deposit subscription: 
#### Classification methods used:
	(1) SVM.SVC; 
	(2) random forest;
	(3) logistic regression;
	(4) neaural network MLPClassifier 

#### Model training, selection and target prediction: 
	(1) For each classification method, models were trainded with different parameter settings with 
	the traiing data. 
	(2) Roc_auc_scores of model predictions on cross-validation data were used to select the best 
	model for each classification method.  
	(3) Roc_auc_scores of model predictions from selected models on test data were compared. 
	(4) Both the balanced and original unbalanced data were used to train models. Prediction results
	from these models were compared.
	The roc_auc_score is an objective measurement of classification models. So, I used it for model 
	performance evaluation. More information is available from online resources: 
	http://scikit-learn.org/stable/modules/generated/sklearn.metrics.roc_auc_score.html 
	https://en.wikipedia.org/wiki/Receiver_operating_characteristic

## Conclusion: 
The models, trained with the balanced data, performed better on the test data than the ones trained with unbalanced data (top 2 panels of the figure below). Since the test data trained with balanced data is not identical to the test data trained with unbalance data.  I also compared model auc scores on the entire data set (2 bottom panels). The conclusion remains the same. Overall, the best roc_auc_score on the test data is 0.878 (neural network trained with the balanced data). The best roc_auc_score on the entire data is 0.887 (random forest trained with the balanced data). 

Overall, all models trained with the balanced data outperformed the models trained with the original unbalanced data by (0.095-0.165 roc_auc scores) on test data, suggesting the usage of more balanced data truly enhanced the performance of all the models.

The neural network and random forest model (trained with balanced data) have better roc_auc_scores than other models on the test data.
![bank deposit roc_auc_score_summary](https://user-images.githubusercontent.com/35440469/42416281-787b1ad4-8238-11e8-9f6d-62b81ba2074c.png)​
### The files:
	(1)Bank deposit subscription--data-processing.ipynb
	(2)Bank deposit--unbalanced-data.ipynb
	(3)bank_deposit_balanced_data-1 to 1ratio.ipynb
