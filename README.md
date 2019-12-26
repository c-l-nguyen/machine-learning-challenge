# machine-learning-challenge

Over a period of nine years in deep space, the NASA Kepler space telescope has been out on a planet-hunting mission to discover hidden planets outside of our solar system. This measurement data has been collected along with what the classification of the observation is. We will use machine learning models to learn how to classify candidate exoplanets based off of their measurement data (3 categories: candidate, false positive, confirmed). The following supervised learning models were used to train the data:

* Decision Tree
* Random Forest
* Naive Bayes
* K-Nearest Neighbors

## Decision Tree

It was found that the training score for the Decision Tree was 1.0 while the test score was usually around .85. This training score is very high (perfect in fact) so it indicates the overfitting tendency of Decision Trees. This is seen as the test score is 15 percentage points lower. The model predicts Confirmed exoplanets well according to the classification report but does poorly in other categories so it is not ready to predict new exoplanets. Dropping the column with the lowest weight doesn't do much to the score but perhaps dropping more could up to a point if we had continued.

## Random Forest

This model has a lower score than the Decision Tree model but the training and testing scores were very close to each other so this indicates that the training is better than that model. The classification report also indicates better overall scores than the Decision Tree model. The grid search indicates that the n_estimators should be around 50-200 (the best parameter/score tends to bounce around this area during testing). Removing the column with the lowest weight increases the score but makes the model incapable of predicting confirmed exoplanets so it is probably best not to do this. 

This is the best overall model for predicting exoplanets.

## Naive Bayes

The Naive Bayes model has low scores but good precision for Confirmed exoplanets and good recall for False Positives. It likely violates the Naive Bayes' assumption that all columns are independent of each other and that there is some dependence amongst some of the columns. Finding and removing these dependencies could improve the model.

## K-Nearest Neighbors

A better score than Naive Bayes but not great and the classification report gives middling scores. It is known that there are only 3 categories but the model with the highest score has n = 11 so that is off the mark. KNN is likely a poor model for this type of data.