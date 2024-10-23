---
title: Stochastic Gradient Descent
---
In the [Gradient Descent Algorithm](gradient-descent-weight-update-rule), our calculation of the weights takes the derivatives of all points and then averages them out to update the weight for a particular iteration, as illustrated by its code:

![[gradient-descent-code.png]]
If we have a million points in the training data, it follows that we would make a million calculations before updating the parameters in each epoch/iteration. Needless to say, this is a rather expensive and slow process. Stochastic Gradient Descent (SGD) is a way of countering this problem. 

![[stochastic-gradient-descent-code.png]]

Notice how the weights and biases are updated for each point in the training data when we calculate its derivative. Rather than updating the parameters after each full epoch, we update them while processing each point. So, if we have a million data points and choose to perform 1000 epochs, vanilla GD would 1000 updates to the parameters while SGD would make 1000 x 1,000,000 updates. 

In SGD, we calculate the weights based on each individual point, almost like estimating the probability of an event based on a sample size of 1. Look at this [this](https://s3.amazonaws.com/media-p.slid.es/videos/1839032/4Ty2oukE/sgd_gd_convergence_ctr_fx_plot.mp4) comparison between GD and SGD and notice how SGD is far more volatile than GD is. This is because the weights are updated for each point, meaning that all points push the weights in a direction that it favourable to it, while the next point could push it back in the old direction. GD, on the other hand, only makes updates after taking all points into consideration. 

These oscillations that we see in SGD can addressed using mini-batch Gradient Descent. Here, instead of updating the parameters after processing each point, it updates them after it process a certain number of points, which is the batch size. If the batch size is 25, the weights would update every 25 points, as opposed to after each point or after all the points have been seen. 

![[mini-batch-gradient-descent-code.png]]

We can compare mini-batch GD, SGD and vanilla GD in [this](https://s3.amazonaws.com/media-p.slid.es/videos/1839032/X6ib_yf2/sgd_gd_bgd_convergence_ctr_fx_plot__1_.mp4) demo. Notice how mini-batch GD oscillates less than SGD. 

If we have a dataset of $N$ points, with a batch size of $B$, we note the following:

| Algorithm     | # of updates in 1 epoch |
| ------------- | ----------------------- |
| Vanilla GD    | $1$                     |
| SGD           | $N$                     |
| Mini-Batch GD | $\frac{N}{B}$           |

We can also use SGD and mini-batch GD on [Momentum-based GD](momentum-based-gradient-descent) and [Nesterov Accelerated GD](nesterov-accelerated-gradient-descent):

- [SGD with momentum](https://s3.amazonaws.com/media-p.slid.es/videos/1839032/tEYUypGG/sgd_momentumsgd_functionplot.mp4)
- [SGD vs NAG vs Momentum](https://s3.amazonaws.com/media-p.slid.es/videos/1839032/1UQFvt5k/sgd_mom_na_functionplot_gentleslope_gamma_high.mp4)
