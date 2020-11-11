# machine-learning-challenge

Since the dataset provides answers of classes, supervised learning is a better suite.

<strong> 1. Random Forest</strong>
Initial Model:<br>
We started with a Random Forest Model which got a score of 0.8753 with n_estimator=200. Next we used feature_importances_ on the first random forest model we built and to see if there are any features we can remove that will improve our model score. Feature Importance is best for tree models. 

Adjusting Features:<br>
Removed the features with importance less than 1%. The score of the second Random Forest with less features was not improved. Thus, we decided to keep all the features.

Grid Search:<br>
Using Grid search to fine tune max_features and n_estimators, the score is not better than initial choice auto and 200. Thus, we keep model rf (n_estimator=200,max_features=auto) as the best Random Forest Model.

<strong> 2. Natural Language Processing-Deep Learning Model</strong>
Initial Model: <br>
We started the model with 2 hidden layers and 100 neurons on each hidden layer, with epochs = 100 and . This first NPL model was scored 0.8896. This is a higher score than the best Random Forest by 0.0143. This is an improvement. However, this model is much more time consuming and requires more computational power. 

Grid Search:<br>
For the Grid Search part, we had to create a class for the model. Batch_size and number of epochs were the parameters we were trying to fine tune. The best combinations were batch_size = 20 and epochs = 200. The score for the tuned NLP model was 0.889756, which is very close to the initial NLP model. Thus, we keep the initial NLP model.


<strong> 3. Support Vector Machine </strong>

Initial Model:<br>
We started with the SVC linear model (default C = 1and gamma=’scale’). This initial model was scored 0.8415. It was the lowest of all 3 models.

Grid Search:<br>
Since the initial model didn’t get a good score, tuning the hyper-parameters was essential. The computing time for 80 different permutations was the fastest compared to Grid Searches for the Random Forest and NLP methods. After tuning, the SVC linear model with C = 50 and gamma = 0.0001 got a high score of 0.8823.

<br><br>In conclusion, combining the two most important factors of picking a model for our data: high accuracy (model score) and low computational power, SVC linear model is the best model out of the 3 models we practiced. Also the Grid Search tuning runs fast so we can tweak the hyper-parameters anytime we want without concerning too much about the computational power and time of running all permutations. 
