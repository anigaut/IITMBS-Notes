---
title: Derivative of Activation Functions
---
We saw [earlier](talking-to-hidden-layers) that in order to calculate the derivative of the loss function with respect to the hidden layers, we needed the derivative of the activation function being used in the hidden layers.

$$
\nabla_{a_{i}} \mathcal{L}(\theta) = \nabla_{h_i} \mathcal{L}(\theta)  \odot [...,g'(a_{ik}),...]
$$

If the logistic function is used as $g$, the derivative is:

$$
g(z) = \frac{1}{1+e^{-z}}
$$

$$
g'(z) = g(z)(1-g(z))
$$

For the $tanh$ function, the derivative will be:

$$
g(z) = tanh(z)
$$

$$
g'(z) = 1-(g(z))^{2}
$$
