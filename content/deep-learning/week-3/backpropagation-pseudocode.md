---
title: Pseudocode and Procedure for Backpropagation
---
Now that we have looked how to calculate the gradient of the loss function with respect to the [output layer][talking-to-output-layer], [hidden layers][talking-to-hidden-layers] and the [parameters](talking-to-parameters), we can perform the [backpropagation](backpropagation-intuition) algorithm. 

Since we're using gradient descent to optimise the weights and biases, we first initialize them randomly and set a maximum number of iterations. For each iteration, we take the outputs for each hidden layer ($a_k$ and $h_k$) and the output layer ($\hat{y}$) obtained from the forward propagation process. Then, we take the gradients of the parameters that were obtained from the backward propagation process. Finally, we adjust the weights by moving them in the opposite direction of the gradient.

![[gradient-descent-backpropagation-pseudocode.png]]


In the forward propagation bit, we calculate outputs for each layer in the neural network based on the weights and biases. For a network with $L$ layers, the pseudocode for forward propagation is:

![[forward-propagation-pseudocode.png]]

For the backward propagation process, for each layer, we first calculate the gradient of the loss function with respect to the output, then the parameters, the activation part of the layer below and finally the pre-activation part of the layer below:

![[backward-propagation-pseudocode.png]]

