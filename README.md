# Machine Learning Homework - Exoplanet Exploration

![exoplanets.jpg](exoplanets.jpg)

## Background

Over a period of nine years in deep space, the NASA Kepler space telescope has been out on a planet-hunting mission to discover hidden planets outside of our solar system.

I chose three machine learning models to predict whether or not the bodies discovered by Kepler are exoplanets:

* a logistic regression model

* a random forest model

* normal and deep neural network models

## Findings

### Logistic Regression Model

Before hyperparameter tuning, the logistic regression model performed moderately well. Training and testing scores were close to each other (less than 1% apart), indicating that the model was not overfit on the training data--it performed almost identically on the new testing data. After tuning the model parameters, training and testing scores both increased by an average of 5%, and were still close to each other (less than 2% apart).

**Scores before Hyperparameter Tuning:** 
Training Data Score: 0.8456990272744612
Testing Data Score: 0.8443935926773455

**Scores after Hyperparameter Tuning:**
Training Data Score: 0.8842265878313943
Testing Data Score: 0.8958810068649885

### Random Forest Model

Before hyperparameter tuning, the random forest model actually performed much better than the logistic regression (LR) model, and almost better than the *tuned* LR model. The random forest model's training score was 99.5% and the testing score was actually higher than the LR model's tuned training score, at 88.7%. After hyperparameter tuning, the scored improved even more--the training score improved to 99.9% and the testing score improved to 90.4%. While this is definitely an increase, it may suggest the model was slightly overfit on the training data because there was a difference of almost 10% between the testing and training scores. Even after determining the importance of each feature, and removing the least imporant ones and refitting the model, the score did not improve and all features were added back into full dataset.

**Scores before Hyperparameter Tuning:**
Training Data Score: 0.9952317375548351
Testing Data Score: 0.8867276887871853

**Scores after Hyperparameter Tuning:**
Training Data Score: 0.9998092695021934
Testing Data Score: 0.9038901601830663

### Neural Network Models

The neural network model performed the best out of the gate. Before adding extra layers, the normal neural network performed better than both the logistic regression and random forest models, with 89.7% accuracy. After adding two additional layers, the deep neural network model performed with 91.7% accuracy, the best overall.

**Normal Neural Network Scores:**
Accuracy: 0.8971962332725525
Loss: 0.24563201407587712

**Deep Neural Network Scores:**
Accuracy: 0.9166507720947266
Loss: 0.19392021073143195

## Conclusions

Overall, 91.7% accuracy is a decent performance, but I would not trust it to actually predict new exoplanets. Perhaps the score would improve with more fine tuning using `RMSprop` or fitting it to a larger training dataset. Only then would it be appropriate to use to actually predict whether or not a Kepler observation actually indicates the existence of a new exoplanet.
