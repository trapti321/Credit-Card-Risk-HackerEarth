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
        
```python
param_grid = {'n_estimators': range(0,1000,50),
               'max_depth': [1, 3, 5],
               'min_child_weight': [1, 3, 6],
               'gamma': [0, 1, 5],
               'learning_rate': [0.0001, 0.001, 0.01, 0.1]}
```



* LightGBM
## Now, turning to the LightGBM model, another tree-based learning algorithm, we are going to tune the following hyperparameters, referring to the documentation:
        
            max_depth - Maximum depth of a tree
            learning_rate - Shrinkage rate
            num_leaves - Max number of leaves in one tree
            min_data_in_leaf - Minimal number of data in one leaf
            
```python
param_grid = {'max_depth': np.arange(5, 75, 10),
              'learning_rate' : [0.001, 0.01, 0.1],
              'num_leaves': np.arange(20, 220, 50),
              'min_data_in_leaf': np.arange(100, 1000, 100)}
```



* CatBoost
## Lastly, we’re going to search over hyperparameter values for CatBoost, our third gradient boosting algorithm. The following hyperparameters will be tuned, according to the documentation:

               depth - Depth of the tree
               learning_rate - As we already know, the learning rate
               l2_leaf_reg - Coefficient at the L2 regularization term of the cost function

```python
param_grid = {'depth': [6, 8, 10],
              'learning_rate': [0.03, 0.1],
              'l2_leaf_reg': [1, 5, 10]}
```



### Evaluation Metrics
With regards to the evaluation of the models, it’s worth mentioning that we should consider Precision, Recall and F1 Score as evaluation metrics, for the following reasons:

* Precision will give us the proportion of positive identifications that were indeed correct. It can be defined as:

* Recall will determine the proportion of real positives that were correctly identified, and it can be defined as:

* F1 Score is a metric that is useful when we need to seek a balance between precision and recall. The formula is defined as:

### Since our objective is to minimize company loss, predicting the risk of client default, a good recall rate is desirable because we want to identify the maximum amount of clients that are indeed prone to stop paying their debts, thus, we are pursuing a small number of False Negatives.
