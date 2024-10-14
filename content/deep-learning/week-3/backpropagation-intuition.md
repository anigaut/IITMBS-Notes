---
title: Intuition for Backpropagation
---
Let's say we have a fairly complicated neural network like the one below which performs rather poorly on the data.

![[backpropagation-intuition.png]]

The outputs produced by the model, which unfortunately deviate from the true outputs significantly, are ultimately the result of the weights and biases being used at the various layers of the network. So, how do we go about inspecting the various parameters in use to see who is to blame for the model's poor performance?

We analyse the various parameters through the output layer and the hidden layers, instead of looking at the parameters directly, similar to how the chain rule calculates the derivative of a complex function step-by-step and sifts through the various layers of the function. The same principle will be used here.

![[layer-wise-analysis.png]]