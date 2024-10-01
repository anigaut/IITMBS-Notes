---
title: Errors and Error Surfaces
draft: false
tags:
---

Revisiting the AND function, for certain values of $w_1, w_2$, the perceptron may not give us the correct output for a fixed bias $w_0$. For example, if we have two inputs $x_1, x_2$, such that $w_1 = -1$ and $w_2=-1$ with $w_0$ fixed at $-1$, the point $(1,1)$ will be in the negative half-space, since $w_0 + w_1*x_1 + w_2*x_2 < 0$ for this input.

![[Pasted image 20240924173406.png]]

Notice that the positive half-space this time is to the left of the separator. Similarly, for various other combinations of $w_1, w_2$, some points may be classified incorrectly. Hence, we are interested in finding a combination of weights such that the error is minimum. 