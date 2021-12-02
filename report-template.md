# Report: Predict Bike Sharing Demand with AutoGluon Solution
Deepthi M

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
TODO: Add your explanation

When I tried to submit my prediction, I realised that Kaggle doesn't accept predictions < 0. Therefore, the output of the predictor needs to be analysed and the number of negative values should be found out. Further these should be removed from the prediction series.
Once this is done, the prediction has to be converted to a CSV file and can be submitted to Kaggle.

### What was the top ranked model that performed?
TODO: Add your explanation

Both my new_features_ model (0.44969) and my new_hpo_model (0.44844) performed pretty good, with just a 0.001 difference between them.

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?
TODO: Add your explanation

The Exploratory Data Analysis helped me get an idea about the dataset, what features it contains and in what form. Visualizing the dataset using histograms really helped to find and know the important features.
To improve the model, additional features were added. I decided to separate out the datetime into hour, day, or month parts.

### How much better did your model preform after adding additional features and why do you think that is?
TODO: Add your explanation

Initially my model got a Kaggle score of 1.39370, but after adding the additional feature, my model improved to a score of 0.44969. It brought it down by 32%.
In machine learning models, the preprocessing of the features make up about 70% of the accuracy of the model. Therefore, the addition of the feature helped the model to produce a much better score as more features help the model to learn more and thus predict the target value more accurately.

## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
TODO: Add your explanation

My model did not change much after the addition of new features, even after hyperparameter optimization was performed. It improved the score only by 0.001.

### If you were given more time with this dataset, where do you think you would spend more time?
TODO: Add your explanation

I would spend more time, performing more feature engineering and adding more features like 'Feature that categorizes hot/cold/mild temps from temp.' or 'Feature that categories very windy/mild wind.'.
I would also explore about hyperparamenter optimization, trying out different techniques and choosing the optimal one.

### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.
|model|hpo1|hpo2|hpo3|score|
|--|--|--|--|--|
|initial|-118.456660|117.640689|-160.413078|1.39370|
|add_features|-33.094410|-32.738870|-115.070481|0.44969|
|hpo|'RF': [{'criterion': 'gini', 'ag_args': {'name_suffix': 'Gini', 'problem_types': ['binary', 'multiclass']}}, {'criterion': 'entropy', 'ag_args': {'name_suffix': 'Entr', 'problem_types': ['binary', 'multiclass']}}, {'criterion': 'mse', 'ag_args': {'name_suffix': 'MSE', 'problem_types': ['regression']}},]|'XT': [{'criterion': 'gini', 'ag_args': {'name_suffix': 'Gini', 'problem_types': ['binary', 'multiclass']}}, {'criterion': 'entropy', 'ag_args': {'name_suffix': 'Entr', 'problem_types': ['binary', 'multiclass']}}, {'criterion': 'mse', 'ag_args': {'name_suffix': 'MSE', 'problem_types': ['regression']}},]|'KNN': [{'weights': 'uniform', 'ag_args': {'name_suffix': 'Unif'}}, {'weights': 'distance', 'ag_args': {'name_suffix': 'Dist'}},]|0.44844|

### Create a line plot showing the top model score for the three (or more) training runs during the project.

TODO: Replace the image below with your own.

![model_train_score](/model_train_score.png)


### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.

TODO: Replace the image below with your own.

![model_test_score_custom_hpo](/model_test_score_custom_hpo.png)


## Summary
TODO: Add your explanation

For the Bike Sharing Demand dataset, we came up with a solution using regression with the help of AutoGluon. Exploratory Data Analysis was done first to understand the structure of the dataset and get an idea of all the features. Histograms were plotted to visualize.
Training the data with just the inital features fetched us a score of 1.39370 on Kaggle.

Second, feature engineering was done by introducing a new feature. Separating the datetime feature helped us achieve this. The second model was trained with these additional features and achieved a score of 0.44969 on Kaggle.

Third, we tried to improve our score by using hyperparameter optimization. The three hyperparameter models I decided to try out are: Random Forest (RF), ExtraTree (XT), and K-Nearest Neighbours (KNN).
Although the XT Model brought on a very minute improvement, it did not help us to significantly improve our scores.

Lastly,  we analysed all of our results using histograms and line plots.
