# Welcome to tensorflow study Jam: day 2 !

1. Representation
2. Data Cleaning
3. Feature cross
4. Regularisation
5. Classification

## Representation

### Feature engineering
It means transforming raw data into a feature vector. 

Consider this dataset,

| Super hero     | Age   | Capabilities                     | Avengers cofounder|Snapified|
|----------------|-------|----------------------------------|-------------------|---------|        
| Iron man       | 48    | Flying, weapon making, tech.     |     Yes           |    No   |
| Dr. Strange    | 42    | Teleporting,weapon making, magic |     No            |    Yes  |
| Spiderman      | 18    | Webbing, spidersense,strength    |     No            |    Yes  |
| Captain America| 100   | Strength, fighting skills,fast   |     Yes           |    No   |  
| Black Panther  | 42    | Rich, fighting skills, tech,fast |     No            |    Yes  |
| Bruce Banner   | 49    | (in)ability to turn into hulk    |     Yes           |    No   |

Many machine learning models must represent the features as real-numbered vectors since the feature values must be multiplied by the model weights.


- **Integer and floating-point data** don't need a special encoding because they can be multiplied by a numeric weight.

- **Categorical values** have a discrete set of possible values. For example, there might be a feature called **Capabilities** with options that include:

[fast, fighting skills, flying, inability to turn into hulk, magic, Rich, Strength, Spidersense, tech, teleporting, webbing, weapon making]

One hot encoding for ironman : [0,0,1,0,0,1,0,0,1,0,0,1]


| Super hero     | Age   | Capabilities                     | Avengers cofounder|Snapified|
|----------------|-------|----------------------------------|-------------------|---------|        
| Iron man       | 48    | [0,0,1,0,0,1,0,0,1,0,0,1]        |     1             |   0     |
| Dr. Strange    | 42    | [0,0,0,0,1,0,0,0,0,1,0,1]        |     0             |   1     |
| Spiderman      | 18    | [0,0,0,0,0,0,1,1,0,0,1,0]        |     0             |   1     |
| Captain America| 100   | [1,1,0,0,0,0,1,0,0,0,1,0]        |     1             |   0     |
| Black Panther  | 42    | [1,0,1,0,0,1,0,0,1,0,0,0]        |     0             |   1     |
| Bruce Banner   | 49    | [0,0,0,1,0,0,0,0,0,0,0,0]        |     1             |   0     |

In **Sparse representation** only nonzero values are stored. In sparse representations, an independent model weight is still learned for each feature value, as described above.


### Qualities of Good features

- Avoid rarely used discrete feature values (power of Banner).
- Prefer clear and obvious meanings (Age of Thor).
- Don't mix "magic" values with actual data (the case of hawkeye).
- Account for upstream instability (different names of powers, for eg: "get help").

## Data Cleaning
- Scaling.
- Handling extreme outliers.
- Binning
- Scrubbing

## Feature Crossing

A feature cross is a synthetic feature that encodes nonlinearity in the feature space by multiplying two or more input features together.

### Validation Set

* Till now,we talked about the test set and the training set
* However,there is one more set,called the Validation set 
* Earlier,we talked about test set,which we use to test how well the model generalises to new examples
* But,it is also important that we don't use the test set to fine tune our Hyperparameters
* Therefore,we need a new set,this is the validation set.It is always constructed from the training set,by splitting it into two
* We use the validation set to estimate the generalisation error and update our hyperparameters accordingly 


## Regularisation

### Underfitting and Overfitting 
* Last session we talked about two sets,the training and test set
* Training set is used in the creation of the model
* We can run the model on the training set to determine the correct weights and biases 
* We then use a seperate test,to see how the model performs on new examples 
* The central challenge in machine learning is to make our model perform well on previously unseen inputs
* Typically,when training a machine learning model,we compute the "loss" on the training set and try to minmimise it using Gradient Descent
* This is simply Optimisation,but in Machine Learning,we are also interested in minimising the test error 
* When we use a ML model,we do not set the parameteres ahead of time ,we first train it on the training set,then se the parameters to test it on the test set
* Under this process,the expected test set error is greater than or equal to the expected value of the training error
* So,there are mainly two factors which determine how well a ML model will perform 
* The first one is, the training error should be small
* Secondly, the gap between the training and test error should be small
* These two factors are the reason for the two biggest challenges in ML, Overfitting and Underfitting  

<p>
  <img src="https://github.com/akshaydevml/Intro-to-Machine-Learning-Workshop/blob/master/uofitting_1.jpg" height="200" width="400" alt="Over and Under fitting"/>
</p>

* Undeffitting occurs,when the model is not able to obtain a sufficiently low error value
* Overfitting occurs, when the gap between the training and test error is too large


### Regularisation 

<p>
  <img src="https://github.com/akshaydevml/Intro-to-Machine-Learning-Workshop/blob/master/regularisation_1.jpg" height="200" width="400" alt="Regularisation"/>
</p>

* To alleviate the problem of underfitting and overfitting,we implement Regularisation
* Last lecture, we talked about features,and how each feature contributes differently to the loss function 
* Sometimes, we have to express preference for one feature over the other 
* For example, we might express a preference for linear features over non-linear features 
* There are many ways of expressing preferences, together they are called "Regularisation"


## Classification

A logistic regression model that returns 0.9995 for a particular email message is predicting that it is very likely to be spam. Conversely, another email message with a prediction score of 0.0003 on that same logistic regression model is very likely not spam.

**True positive** is an outcome where the model correctly predicts the positive class.
**True negative** is an outcome where the model correctly predicts the negative class.

**False positive** is an outcome where the model incorrectly predicts the positive class. 
**False negative** is an outcome where the model incorrectly predicts the negative class.

### Accuracy
```
Accuracy = Correct predictions/total predictions
         = (TP+TN)/(TP+TN+FP+FN)
```
### Precision
```
precision = TP/(TP+FP)

```

### Recall

```
Recall = TP/(TP+FN)
```

https://goo.gl/zwGRuX
