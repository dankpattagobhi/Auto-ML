# Hyperparameter-Optimisation
## What is Hyperparameter?
Anything in machine learning and deep learning that you decide their values or choose their configuration before training begins and whose values or configuration will remain the same when training ends is a hyperparameter.
## What is Hyperparameter Tuning?
When you’re training machine learning models, each dataset and model needs a different set of hyperparameters, which are a kind of variable. The only way to determine these is through multiple experiments, where you pick a set of hyperparameters and run them through your model. This is called hyperparameter tuning. In essence, you're training your model sequentially with different sets of hyperparameters. This process can be manual, or you can pick one of several automated hyperparameter tuning methods.
## How to do Hyperparameter Tuning
There are many different techniques through which hyperparameter optimisation can be achieved, most commonly used are Bayesian Optimisation, Grid Search, Random Search, Tree Parzen Estimator.
Here,we have used Tree-Parzen Estimator (TPE) to optimize the hyperparameter an make it compatible with various models.
## TREE-PARZEN ESTIMATOR (TPE)
![image](https://github.com/dankpattagobhi/Hyperparameter-Optimisation/assets/132737586/07fb2f17-50e8-47d7-8497-36d95df81d2d)

TPE is a Bayesian optimization algorithm. This means it allows us to start with some initial beliefs about what our best model hyperparameters are, and update these beliefs in a principled way as we learn how different hyperparameters impact model performance. This is already a significant improvement over Grid Search and Random Search! Instead of determining the best hyperparameter set through trial and error, over time we can try more combinations of hyperparameters which lead to good models and fewer that do not.
Generally, the algorithm consists of the following steps:
1.	Define a domain of hyperparameter search space,
2.	Create an objective function which takes in hyperparameters and outputs a score (e.g., loss, root mean squared error, cross-entropy) that we want to minimize,
3.	Get couple of observations (score) using randomly selected set of hyperparameters,
4.	Sort the collected observations by score and divide them into two groups based on some quantile. The first group (x1) contains observations that gave the best scores and the second one (x2) - all other observations,
5.	Two densities l(x1) and g(x2) are modeled using Parzen Estimators (also known as kernel density estimators) which are a simple average of kernels centered on existing data points,
6.	Draw sample hyperparameters from l(x1), evaluating them in terms of l(x1)/g(x2), and returning the set that yields the minimum value under l(x1)/g(x1) corresponding to the greatest expected improvement. These hyperparameters are then evaluated on the objective function.
7.	Update the observation list from step 3
8.	Repeat step 4-7 with a fixed number of trials or until time limit is reached

#### System has been optimized for three models i.e. Random Forest Classifier, Gradient Boost Classifier and Logistic Regression. Basic structure of the system remains same in all three models with some minor changes in system for Logistic Regression.


## Compare Learning Rate Distribution Curves
1.	Random Forest Classifier
   
   ![image](https://github.com/dankpattagobhi/Hyperparameter-Optimisation/assets/132737586/0c64d0a9-9a80-49f5-9e7d-9e9ff98e62c6)
   
2.	Gradient Boosting Classifier
   
   ![image](https://github.com/dankpattagobhi/Hyperparameter-Optimisation/assets/132737586/1e0368f4-7dcc-45d7-b584-ea7c9771e04c)
  	
3.	Logistic Regression
   
   ![image](https://github.com/dankpattagobhi/Hyperparameter-Optimisation/assets/132737586/dfd8a5e9-85bd-49cc-a162-519806c059cb)
