---
title: Learning Parameters - Gradient Descent
---
Going back to the original question, we'd like to find a $w$ and $b$ such that the loss is minimal. If we vectorize these 2 quantities and initialize them as $\theta = [w,b]$, how can we change $\theta$ such that the loss function reduces with the new $\theta$? The answer lies in the [Taylor Series](taylor-series.md). Further, since the Taylor Series works only within small intervals, we can moderate the change in $\theta$ using a learning rate $\eta$ such that $\theta_{new} = \theta + \eta * \Delta \theta$.

For ease of notation, if we take $\Delta \theta = u$, we have (from the Taylor Series):

$$\mathcal{L}(\theta + \eta u) = \mathcal{L}(\theta)+\eta*u^T \nabla_{\theta} \mathcal{L}(\theta) + \frac{\eta^2}{2!}u^T \nabla_{\theta}^{2} \mathcal{L}(\theta)u + ... $$

$\nabla_{\theta} \mathcal{L}(\theta)$ is the gradient (derivative) of the function $\mathcal{L}(\theta$ )with respect to $\theta$. The derivative of a vector is the partial derivative of each element in it. For example, if we have a function $y=w^2+b^2$ based on $\theta$, the gradient of this would be:

$$\begin{bmatrix} \frac{\partial y}{\partial w} \\ \frac{\partial y}{\partial b} \end{bmatrix} = \begin{bmatrix} 2w \\ 2b \end{bmatrix}$$

The second order gradient ${2!}u^T \nabla_{\theta}^{2} \mathcal{L}(\theta)$ is the gradient of the gradient. Speaking generally, the derivative of a vector with respect to another vector looks all possible combination of elements between the two vectors and computes the partial derivative for each. So, if we have a vector with $m$ elements and we take it's derivative with respect to another vector with $n$, elements, the result would be a matrix of shape $m \times n$.

Going back to the approximation of $\theta_{new}$ based on a small change to $\theta$, the change made to $\theta$ would be favourable only if the new less were less than the original loss:

$$\mathcal{L}(\theta+\eta u) < \mathcal{L}(\theta)$$

$$\implies \mathcal{L}(\theta+\eta u) - \mathcal{L}(\theta) < 0$$

$$\implies u^T \nabla_{\theta} \mathcal{L}(\theta) < 0$$

For the loss to be minimal, we want the above quantity to be as negative as possible. If $\beta$ is the angle between $u^{T}$ and $u^T \nabla_{\theta} \mathcal{L}(\theta)$:

$$-1 \leq cos(\beta) = \frac{u^T \nabla_{\theta} \mathcal{L}(\theta)}{||u^{T}||*||\nabla_{\theta} \mathcal{L}(\theta)||} \leq 1$$

Multiplying all sides with $k = ||u^{T}|| * ||\nabla_{\theta} \mathcal{L}(\theta)||$:

$$-k \leq k*cos(\beta) = u^T \nabla_{\theta} \mathcal{L}(\theta) \leq k$$

Thus, the difference between the new loss and the old one is the most negative when $cos(\beta) = -1 \implies \beta = 180\degree$.  The angle between the gradient vector and the delta vector, which represents the change in $\theta$ should be $180\degree$, which means that $u$ should move in the direction opposite to the gradient.





