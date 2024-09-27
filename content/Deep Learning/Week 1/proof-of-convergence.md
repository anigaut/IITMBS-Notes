---
title: Proof of Convergence
---


- If we have two sets $P$ and $N$ such that the former contains all the positive points in the input space and the latter contains all the negative points, how can we prove that the PLA will converge for a linearly separable dataset?
- In other words, how can we address the concern from the previous section, that the updating of the weight vector could go on forever, without cleanly separating the positive points from the negative points at the end? For the PLA to be valid the number of times the weights are updated needs to be finite.
- Let's consider a new set $P' = P \cup N^{-}$.  In the RHS, $N^{-}$ is the negation of $N$, meaning that we flip the signs of all those points for which $\sum_{i=1}^{n} w_i*x_i < w_0$. Every $p \in P'$ will satisfy $w^{T}p \geq 0$.
- Further we normalise all the p's such that $||p||^2 =1$. $w^*$ will the solution weight vector for this normalised set.
- With that established, the following screenshot has the pseudocode for this slightly modified PLA:
![[9.png]]
- Notice that we have only one `if` loop this time since all points in $P'$ are positive.
- $w^*$ is the optimal solution, but we don't know what it is yet. It gets updated each time $w^{T}p_i \leq 0$. It need not be updated after every iteration. Hence, after $t$ iterations, the total number of updates $k$ will be less than $t$. 
- Now, let's say at the $t^{th}$ iteration, we see a misclassification for point $p_i$. We correct that giving us $w_{t+1} = w_t + p_i$. If $\beta$ is the angle between $w^*$ and $w_{t+1}$: 
$$cos\beta = \frac{w^*w_{t+1}}{||w_{t+1}||}$$
- Upon performing some computations on the numerator and denominator of the above, we get:
![[10.png]]
![[11.png]]
- Combining the 2 results, we get:
$$cos\beta \geq \frac{w^*w_0 + k\delta}{\sqrt{||w_0||^{2}+k}}$$
- This means that $cos\beta$ grows proportionally to $\sqrt{k}$. As $k$ increases, $cos\beta$ could become arbitrarily large. However, $cos\beta$ has to be $\leq 1$, which means that $k$ will be bounded too. This proves that the number of updates made to the weight vector will be a finite and the PLA will converge at some point. 

