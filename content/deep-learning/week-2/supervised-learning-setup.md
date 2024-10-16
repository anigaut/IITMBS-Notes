---
title: Supervised Machine Learning Setup
---
A typical supervised learning environment would consist of the following components:
- **Data**: the inputs and outputs we use to create a model.
- **Model**: An approximation of the relationship between $x$ and $y$. One such approximation could be the logistic function.
- **Parameters**: Weights assigned to various inputs that need to be learnt from the data.
- **Learning Model**: An algorithm for learning the parameters $w$ of the model using the data. 
- **Objective/loss function**: A guide to the learning algorithm.

The learning algorithm tries to minimise the loss function. 

Let's apply to these to the example of whether we want to watch a movie. In such a context:
- **Data**: $x_i$: the input vector and $y_i$ = {yes/no}
- **Model**: An approximation of the relationship between the input and output. Let's say we decide to use the logistic function:

$$
\hat{y} = \frac{1}{1+e^{-w^{T}x}}
$$

- **Parameters**: $w$.
- **Learning algorithm**: Gradient Descent (will be covered soon)
- **Objective function**: $l(w) = \sum_{i=1}^{n} (\hat{y}_i - y_i)^2$

Note:
- $\hat{y}$ is used instead of $y$ since the model is an approximation. 
- The loss function takes the squared difference between the predicted output and the real output instead of the modulus since we want the function to be differentiable.

The learning algorithm seeks to find the weight vector $w$ that minimises the objective function.