# Report: Predict Bike Sharing Demand with AutoGluon Solution
Rodrigo Torres Castillo

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
It is known that Kaggle doesn't allow negative values in the submission, therefore the values must be converted to zeros. The first time that I tried to submit my results, I didn´t have any kind of problem because all my results were greater than zero. Nevertheless, in the subsequent results. I had to covert the values into zero, in order to avoid issues with the submissions.

### What was the top ranked model that performed?
The model that performed the best was the ``WeightedEnsemble_L3``, having a score value of **-112.96**.

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?
Because the type of problem was a regression one, a key variable was the time column. This variable wasn't in the appropiate format, therefore I converted in a ``datetime`` format and finally, separate this variable into month, day, day of the week and time.

### How much better did your model preform after adding additional features and why do you think that is?
Adding new features allowed the to perform much better than the initial training. Here, the model that performed the best was the ``WeightedEnsemble_L3``, having a score value of **-31.86**. The final score was **0.48327**.

## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
The model's performance improved significantly reaching a value of **0.46514**. Although the model improvement was small compared to the ``add_features`` model, any improvement is extremely positive in competitions.

### If you were given more time with this dataset, where do you think you would spend more time?
Perhaps, I would spend more time doing EDA. There might be lot of hidden information among our dataset that would allow us to have a better performance model.

### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.
|model|GBM|RF|score|
|--|--|--|--|
|initial|default|default|1.42210|
|add_features|default|default|0.48327|
|hpo|	{'num_boost_round': 100, 'num_leaves': Int: lower=26, upper=66}|{'max_depth': Int: lower=3, upper=30, 'max_features': Real: lower=0.1, upper=1.0, 'max_samples': Real: lower=0.1, upper=1.0}	|0.46514|

### Create a line plot showing the top model score for the three (or more) training runs during the project.

![alt text](model_train_score-1.png)

### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.

![alt text](model_test_score-1.png)

## Summary
Overall, I realized how powerfull and easy-to-use Autoglon is. In just a few lines of code, it allows to find good models eficientely, so we could focus more on the quality data.

In further steps, I would focus more doing EDA, in order to have a better understanding of the data. Next, I would focus only on the model that performed better, and finally optimize hyperparameters.