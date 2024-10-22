---
title: Nesterov Accelerated Gradient Descent
---
While [Momentum-Based Gradient Descent (MGD)](momentum-based-gradient-descent) does well to speed up the process of convergence in the flatter regions of the error surface, it tends to overshoot the destination and could oscillate back and forth in the regions near the point of convergence. Nesterov Accelerated Gradient Descent (NAG) provides a solution to control these oscillations. 

Recall from MGD that:

$$
u_t = \beta u_{t-1} + \nabla w_t
$$

From this, we see that that $u$ for the current iteration is first updated by the $u$ of the previous iteration (i.e., $\beta u_{t-1}$) and then the gradient is added to it. NAG proposes that we first add the previous updates and then calculate the gradient of the loss function with respect the new quantity and then add the weights accordingly. Look before you leap. We first check whether we're moving in the right direction after adding the previous updates and then move in the required direction towards convergence based on this based on this. This is a more measured approach where we can course-correct. Using NAG, we update the weights in the following manner:

$$
u_t = \beta u_{t-1} + \nabla (w_t - \beta u_{t-1})
$$
- Notice how we don't add the entire gradient of the weight vector in the current iteration to the update. Instead we moderate it according to where the momentum takes us.

$$
w_{t+1} = w_t - \eta u_t
$$

[This](https://s3.amazonaws.com/media-p.slid.es/videos/1839032/NN2bN8P3/nag_sigmoid__1_.mp4) demo illustrates how NAG prevents the aforementioned oscillations from happening. 


