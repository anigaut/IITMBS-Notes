---
title: "Feed Forward Neural: Learning Parameters Intuition"
---
How can we go about learning the parameters of a feedforward neural network? Remember that the gradient descent algorithm for a simple neural network was as follows:

![[gradient-descent-pseudocode.png]]

Now, instead of $W$ and $b$, we have $[W_1, W_2,  ... , W_L]$ and $[b_1, b_2, ..., b_L]$. We can put both of these into one vector called $\theta$, modifying the algorithm to:

![[feed-forward-nn-grad-desc-pseudocode.png]]

Where:

$$
\theta = [W_1, W_2,  ... , W_L, b_1, b_2, ..., b_L]
$$

$$
\nabla \theta_t = [\frac{\partial \mathcal{L}(\theta)}{\partial W_{1,t}}, ..., \frac{\partial \mathcal{L}(\theta)}{\partial W_{L,t}}, 
\frac{\partial \mathcal{L}(\theta)}{\partial b_{1,t}}, ...,
\frac{\partial \mathcal{L}(\theta)}{\partial b_{L,t}}]
$$

$\nabla{\theta}$ is composed of the gradients of the weight and bias of each layer in the network. So, how can we calculate the loss function and how can we calculate the gradient?

