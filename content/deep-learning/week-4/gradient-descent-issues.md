---
title: Problems with Gradient Descent
---
The [Gradient Descent Algorithm](gradient-descent) algorithm initializes the parameters of a neural network ($w$ and $b$) randomly and then updates the parameters in the opposite direction to the gradient of the loss function taken with respect to the parameters.  

The derivative of a function is essentially its sensitivity to small changes in the variable it's computed in reference to. For any function $f(x)$, the steeper the curve is, the higher its derivative will be. $3x^2$, for example is steeper than $2x^2$, and it's derivative too, unsurprisingly, is higher for any $x$. 

Recall the [weight-update rule](gradient-descent-weight-update-rule) for the Gradient Descent Algorithm:

$$
w_{t+1} = w_{t} - \eta \nabla w_{t}
$$

$$
b_{t+1}=b_{t}-\eta \nabla b_{t}
$$

We can see that the magnitude of change to the parameters depends on the gradient. A high gradient would mean that the weights and bias would move towards convergence faster. Since we initialise the parameters randomly, it's possible that they are initialised at a point where the loss function's curve is rather flat, which would mean that the updates would also be small and the algorithm would take a long time to converge, since more iterations would be required to reach the convergence point. So, how do we speed up the process of updating the weights if the parameters are initialised at an unfavourable place in the curve?
