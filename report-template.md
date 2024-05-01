# Report: Predict Bike Sharing Demand with AutoGluon Solution
#### Wessam Salah Walid

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
- I realized that some of the predictions contained negative values, which were not acceptable for submission to Kaggle.
- To address this issue, I implemented two changes:
  1. Rounded negative count values to zero.
  2. Rounded all the numbers in the count column to zero to ensure that no negative values were present in the predictions.


### What was the top ranked model that performed?
- The top-ranked model was the `WeightedEnsemble_L3` model, which delivered the best performance on unseen test dataset with a validation RMSE score of 37.9800 and the best Kaggle score of 0.44798.

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?
- The exploratory analysis revealed insights into the hourly, daily, and seasonal variations in bike rental demand, leading to the creation of additional features to improve model performance.
- Features were categorized based on frequency of bike rides on an hourly basis, and continuous features like temperature, humidity, and wind were transformed into categorical variables.
- Additional features were added by defining functions to transform existing features in the dataset, generating new features and providing more granular insights into the data.

### How much better did your model preform after adding additional features and why do you think that is?
- After adding the additional features, the model performance improved significantly by approximately 25%.
- This improvement can be attributed to the incorporation of relevant features based on domain knowledge, which provided the model with more information to make accurate predictions.

## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
- Hyperparameter tuning was attempted but did not result in significant improvements in model performance.
- Given the nature of the data, the default hyperparameters or initial configurations were sufficient to achieve competitive results.
- It appears that hyperparameter tuning may not have been necessary or significantly impactful for this particular dataset.

### If you were given more time with this dataset, where do you think you would spend more time?
- With more time, focus would be on further refining modeling techniques to achieve higher accuracy and collecting more data to augment the existing dataset.

### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.
| Model          | HPO1                                              | HPO2                           | HPO3                                              | Score     |
|----------------|---------------------------------------------------|--------------------------------|---------------------------------------------------|-----------|
| Initial        | Default                                           | Default                        | Default                                           | 1.84906   |
| Add_features   | Default                                           | Default                        | Default                                           | 0.61314   |
| HPO            | 'CAT': {'iterations': 10000},'RF': {'n_estimators': 300},'XT': {'n_estimators': 300} | GB: num_boost_round=100, num_leaves(lower=26, upper=66, default=36) | scheduler: local, searcher: bayesopt | 0.64836   |

### Create a line plot showing the top model score for the three (or more) training runs during the project.

![model_train_score.png](https://github.com/wessamsw/Bike-Sharing-Demand/blob/main/model_train_score.png?raw=true)

### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.

![model_test_score.png](https://github.com/wessamsw/Bike-Sharing-Demand/blob/main/model_test_score.png?raw=true)

## Summary
- The project aimed to predict bike sharing demand using AutoGluon solution.
- During the initial training phase, adjustments were made to handle negative count values in predictions, and the top-performing model was identified as the `WeightedEnsemble_L3` model.
- Exploratory data analysis revealed insights into the hourly, daily, and seasonal variations in bike rental demand, leading to the creation of additional features to improve model performance.
- Model performance improved significantly by approximately 25% after adding relevant features based on domain knowledge.
- Hyperparameter tuning was attempted but did not result in significant improvements, indicating that default hyperparameters were sufficient for achieving competitive results.
- Given more time with the dataset, focus would be on further refining modeling techniques to achieve higher accuracy and collecting more data to augment the existing dataset.
- A table was created to summarize the models run, hyperparameters modified, and Kaggle scores obtained.
- Line plots were included to visualize the top model scores and Kaggle scores during the training and prediction submissions, respectively.
