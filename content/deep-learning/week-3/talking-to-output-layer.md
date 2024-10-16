---
title: Computing Gradient of Loss Function With Respect to Output Layer
---
In the process of [investigating](backpropagation-intuition) who is responsible for a model's poor functioning, the first step is to inspect the output layer and compute the derivative of the loss function with respect to it. 

Before that, let's consider the partial derivative of the loss function with respect to one of the output layer neuron's output. 

$$
\mathcal{L}(\theta)= -log \; \hat{y}_l
$$
- Where $l$ refers to the one among the $k$ neurons that is the true class label.

$$
\frac{\partial}{\partial \hat{y_i}} \mathcal{L}(\theta) = \frac{\partial}{\partial \hat{y_i}} (-log \; \hat{y}_l)
$$

$$
= - \frac{1}{\hat{y_l}} \; \textnormal{if} \; i=l
$$
$$
=0 \; \textnormal{otherwise}
$$

This can be rewritten using the indicator notation:

$$
\frac{\partial}{\partial \hat{y_i}} \mathcal{L}(\theta) = -\frac{1_{i=l}}{\hat{y_l}}
$$

If we simply apply this to all the neurons in the output, we get the gradient vector with respect to $\hat{y}$.

$$
\nabla_{\hat{y}} \mathcal{L}(\theta) = 
\begin{bmatrix} \frac{\partial \mathcal{L}(\theta)}{\partial \hat{y_1}} \\ ... \\ \frac{\partial \mathcal{L}(\theta)}{\partial \hat{y_k}} \end{bmatrix}
= - \frac{1}{\hat{y_l}} \begin{bmatrix} 1_{l=1} \\ ... \\ 1_{l=k}\end{bmatrix}
$$

$$
=- \frac{1}{\hat{y_l}} e_l
$$

- Where $e(l)$ is a k-dimensional vector, whose $l^{th}$ element is 1 and the rest are 0.

What we're actually interested is in the gradient of the loss function with respect to the pre-activation part of the output layer $a_L$, since the final output simply takes $a_L$ and applies the softmax function on it.

$$
\frac{\partial}{\partial a_{Li}} \mathcal{L}(\theta) = \frac{\partial}{\partial a_{Li}} (-log \; \hat{y}_l)
$$

$$
\frac{\partial}{\partial a_{Li}} -log \; \hat{y}_l = -\frac{1}{\hat{y_l}} \frac{\partial}{\partial a_{Li}} \hat{y_l}
$$

This ultimately works out to:

$$
\frac{\partial}{\partial a_{Li}} \mathcal{L}(\theta)=-(1_{l=i} - \hat{y_i})
$$
- The derivation for this is explained in lecture 3.5 of week 3.

This gives us the partial derivative of the loss function with respect to the $i^{th}$ element of $a_L$. Using this, we can write the gradient vector of the loss function with respect to the output layer:

$$
\nabla_{a_{L}} \mathcal{L}(\theta)
= \begin{bmatrix} \frac{\partial \mathcal{L}(\theta)}{\partial a_{Li}} \\ ... \\ \frac{\partial \mathcal{L}(\theta)}{\partial a_{Lk}}
\end{bmatrix}
= \begin{bmatrix} -(1_{l=i} - \hat{y_2}) \\ ... \\ -(1_{l=k} - \hat{y_k}) \end{bmatrix}
$$

$$
= -(e(l) - \hat{y})
$$











