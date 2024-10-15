[![Typing SVG](https://readme-typing-svg.herokuapp.com?font=Inter&weight=900&size=40&pause=1000&color=48cae4&center=true&vCenter=true&random=false&width=435&lines=ml-forge!)](https://git.io/typing-svg)

![Repository Visitors](https://komarev.com/ghpvc/?username=prasanna-muppidwar&color=blue&label=Repository+Visitors)

**ml-forge** is an easy-to-use, open-source machine learning library designed to help you build machine learning models from scratch. It currently supports linear regression and evaluation metrics, with an intuitive interface for training and predicting models.

## Features
- Linear Model's implemented with ease of Understanding.
- R-squared score calculation for evaluating models.
- Simple and flexible API for integrating into any project.

## Installation

Clone the repository directly from GitHub:

```bash
git clone "https://github.com/prasanna-muppidwar/ml-forge.git"
```

## Docs 

### Implement Linear Regression 
Linear Regression is a simple machine learning algorithm used to model the relationship between a dependent variable and one or more independent variables. It tries to find the best-fitting straight line (called the regression line) by minimizing the error between predicted and actual values.

The R² score (Coefficient of Determination) measures the proportion of the variance in the dependent variable that is predictable from the independent variables. It ranges from 0 to 1, where 1 indicates perfect prediction, and 0 means the model doesn’t explain the variance at all.

``` python
import numpy as np
from sklearn.model_selection import train_test_split
from sklearn import datasets
from ml-forge.linear_regression import LinearRegression
from ml-forge.metrics import r2_score



X, y = datasets.make_regression(n_samples=100, n_features=1, noise=20, random_state=4) 
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=1234)

regressor = LinearRegression(learning_rate=0.01, n_iters=1000)
regressor.fit(X_train, y_train)
predictions = regressor.predict(X_test)



accu = r2_score(y_test, predictions)
print("Accuracy:", accu)


```
### train test split
Train-test split is a technique used in machine learning to evaluate the performance of a model. It involves dividing the dataset into two parts: the training set and the test set. The model is trained on the training set, where it learns patterns from the data, and then evaluated on the test set to check how well it generalizes to unseen data. This helps in assessing the model’s accuracy and detecting overfitting or underfitting. Typically, 70-80% of the data is used for training, and 20-30% for testing.
```python
import numpy as np
from ml-forge.linear_regression import LinearRegression

from ml-forge.train_test_split import train_test_split
from sklearn import datasets

X, y = datasets.make_regression(n_samples=100, n_features=1, noise=20, random_state=4)


X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=1234)
regressor = LinearRegression(learning_rate=0.01, n_iters=1000)
regressor.fit(X_train, y_train)  

predictions = regressor.predict(X_test)

accu = r2_score(y_test, predictions)
print("Accuracy (R² score):", accu)

```