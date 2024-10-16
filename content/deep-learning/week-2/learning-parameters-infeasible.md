---
title: Learning Parameters - Brute Force
---
Having established an [environment](supervised-learning-setup.md) for conducting supervised ML, let's assume a simple case where there's only one input whose weight is $w$ and bias $w_0$ which will be referred to as $b$ from here on. If we continue using the sigmoid function to approximate the relationship between the input and output of the training data, we have the following setup:

$$
f(x) = \frac{1}{1+e^{-(wx+b)}}
$$

If we have $N$ input-output pairs in the training data, find $w$ and $b$ such that the loss is minimal. The loss function, in turn, is:

$$
L(w,b) = \frac{1}{N} \sum_{i=1}^{N} (y_i-f(x_i))^{2}
$$

The brute-force way to go about doing this would be to randomly guess several different combination of $w$ and $b$ and see which one returns the least loss. If we have 2 input-output pairs $(0.5,0.2)$ and $(2.5,0.9)$, here are some possible values for $w$ and $b$ along with their respectives losses:

![[learning-params-brute-force.png]]

Another possible way is to conduct a random search on the error surface, which is a visual way of going about this task:

![[error-surface-search.png]]

Needless to say, neither of these methods is optimal since they are completely based on guess work.

