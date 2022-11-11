---
title: Hi
---

## Linear Regression

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


###

Goodness of fit (sum of squares of deviations of fit from the data):

$$
\chi^2 = \sum_i r_i^2 = \sum_i (y_i - mx_i - c)^2
$$

Want to minimise $\chi^2$, so differentiate and set to 0:

$$
\begin{equation}
\nabla \chi^2=\left[\begin{array}{l}
\frac{\partial \chi^2}{\partial m} \\
\frac{\partial \chi^2}{\partial c}
\end{array}\right]=\left[\begin{array}{l}
-2 \sum_i x_i\left(y_i-m x_i-c\right) \\
-2 \sum_i\left(y_i-m x_i-c\right)
\end{array}\right]=\left[\begin{array}{l}
0 \\
0
\end{array}\right]
\end{equation}
$$

After some algebra we get:

$$
\begin{equation}
\begin{array}{ll}
m=\frac{\sum(x-\bar{x}) y}{\sum(x-\bar{x})^2} & \sigma_m^2 \simeq \frac{\chi^2}{\sum_i(x_i-\bar{x})^2(n-2)} \\
c=\bar{y}-m \bar{x} & \sigma_c \simeq \sigma_m \sqrt{\bar{x}^2+\frac{1}{n} \sum_i(x_i-\bar{x})^2}
\end{array}
\end{equation}
$$




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
