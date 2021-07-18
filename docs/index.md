# Machine Learning Algorithms

The algorithms and explanations listed here are intended to give a quick overview of how each algorithm works along with code examples to show how you can implement them. Library versions are provided along with the from-scratch implementations. Links to further resources are also given.

The following algorithms are given:

- [ ] Linear Regression
<!-- - [ ] Logistic Regression
- [ ] Decision Trees
- [ ] Random Forests
- [ ] Support Vector Machines (SVM's)
- [ ] Naïve Bayes
- [ ] k-Nearest Neighbors
- [ ] k-means
- [ ] Principal Component Analysis
- [ ] Neural Networks -->

## Linear Regression

### Overview

$$
y = \theta_0 + \theta_1 x_1 + \theta_2 x_2 + ... + \theta_n x_n
$$

To train the regression model, we can use the Mean Square Error performance metric to find the parameters which minimise the error:

$$
\mathrm{MSE}(\boldsymbol{\theta}) = \frac{1}{m}\sum^m_{i=1}(\boldsymbol{\theta}^{\mathrm{T}} \mathbf{x}^{(i)} - y^{(i)})^2
$$

We can use the Normal Equation (closed-form solution) to find $\boldsymbol{\theta}$ (i.e. the parameters which minimise the MSE):

$$
\boldsymbol{\hat{\theta}} = (\boldsymbol{\mathrm{X}}^{\mathrm{T}} \boldsymbol{\mathrm{X}})^{-1} \boldsymbol{\mathrm{X}}^{\mathrm{T}} \boldsymbol{\mathrm{y}}
$$

### Implementation

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/googlecolab/colabtools/blob/master/notebooks/colab-github-demo.ipynb)

```python
import pandas as pd
import numpy as np

def concat_ones(X):
    # Adds a column of 1's to the matrix X
    n_items = X.shape[0]
    X_b = np.c_[np.ones((n_items, 1)), X]  # add x0 = 1 to each instance
    return X_b 

def lr_normal_train(X, y):
    # Uses the Normal Equation to compute parameters for Linear Regression
    n_items = X.shape[0]
    X_b = concat_ones(X)
    theta_best = np.linalg.inv(X_b.T.dot(X_b)).dot(X_b.T).dot(y)
    return theta_best
```
!!! note "Normal Equation Complexity"
    In practice, it is best to avoid using the Normal Equation due to the computational complexity ($\mathrm{O}(\mathrm{n}^3)$) of inverting the matrix $\boldsymbol{\mathrm{X}}$. This means doubling the number of features increases computation time by $2^3 = 8$ times.

<!-- Give table overview comparison of pros and cons for normal equation etc. -->
<!-- Custom diagrams and gifs -->
<!-- !!! note "From scratch implementation"
!!! note "Library implementation"
!!! note "Example dataset"
!!! note "TL;DR"
!!! note "Further resources"



### Logistic Regression

### Decision Trees

### Random Forests

### Support Vector Machines (SVM's)

### Naïve Bayes

### k-Nearest Neighbors

### k-means

### Principal Component Analysis

### Neural Networks -->
