---
title: Sigmoid Neuron
---
Till now, we've dealt only with Boolean functions. How can we deal with real functions where $y=f(x)$, $x \in R, y \in R$ instead of ${0,1}$? 

Recall that a perceptron fires (i.e., returns 1) if the sum of its weighted inputs is greater than a threshold $-w_0$. Looking at the example of whether we will watch a movie or not, let's say there's only one input, which the movie's average rating given by critics. If the threshold is 0.5 and $w_1 = 1$, we would conclude that we would indeed watch the movie if the average rating was $0.51$ but wouldn't watch it if the rating was $0.49$, since they fall on either side of the threshold. This seems harsh, since our decision sways completely to other side when we cross the threshold. A rating of $0.99$ is the same as $0.51$ in this context. This is a characteristic of the perceptron function, which is a step function.

![[perceptron_step_function.png]]

A function which would shift gradually from 0 to 1 would be better than one which takes only either extreme. The sigmoid function is one such example. It is expressed as:

$$
y = \frac{1}{1+e^{-(w_0+\sum_{i=1}^n w_ix_i)}}
$$
We don't see a sharp shift from one side to another when we cross the threshold. 

![[sigmoid_function.png]]

The output y here is not binary, but is a real value between 0 and 1. Naturally, this can be interpreted as a probability too. Further, the sigmoid function is continuous and differentiable.