# Credit-Card-Risk-HackerEarth
To identify the Credit card fraud , Company or person did not return money on time.


### Credit risk is associated with the possibility of a client failing to meet contractual obligations, such as mortgages, credit card debts, and other types of loans.

###Minimizing the risk of default is a major concern for financial institutions. For this reason, commercial and investment banks, venture capital funds, asset management companies and insurance firms, to name a few, are increasingly relying on technology to predict which clients are more prone to stop honoring their debts.

* Machine Learning models have been helping these companies to improve the accuracy of their credit risk analysis, providing a scientific method to identify potential debtors in advance.

### Data can be found here - https://www.hackerearth.com/challenges/competitive/amexpert-code-lab/machine-learning/credit-card-default-risk-5-95cbc85f/


### Machine Learning Models
We are experimenting with the following 3 gradient boosting algorithms to determine which one yields better results:
* XGBoost
     ## For the XGBoost model, we’ll tune the following hyperparameters, according to the official documentation:
        n_estimators - The number of trees in the model
        max_depth - Maximum depth of a tree
        min_child_weight - Minimum sum of instance weight needed in a child
        gamma - Minimum loss reduction required to make a further partition on a leaf node of the tree
        learning_rate - Step size shrinkage used in the update to prevents overfitting 



* LightGBM
* CatBoost

### Evaluation Metrics
With regards to the evaluation of the models, it’s worth mentioning that we should consider Precision, Recall and F1 Score as evaluation metrics, for the following reasons:

* Precision will give us the proportion of positive identifications that were indeed correct. It can be defined as:

* Recall will determine the proportion of real positives that were correctly identified, and it can be defined as:

* F1 Score is a metric that is useful when we need to seek a balance between precision and recall. The formula is defined as:

### Since our objective is to minimize company loss, predicting the risk of client default, a good recall rate is desirable because we want to identify the maximum amount of clients that are indeed prone to stop paying their debts, thus, we are pursuing a small number of False Negatives.
