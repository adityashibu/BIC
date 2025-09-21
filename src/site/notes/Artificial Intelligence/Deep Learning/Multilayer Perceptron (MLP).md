---
{"dg-publish":true,"permalink":"/artificial-intelligence/deep-learning/multilayer-perceptron-mlp/"}
---

#area/DL/concept 

## Concept
---

The **Multilayer Perceptron** was introduced to address the shortcomings of using only a single perceptron. The limitations that a perceptron had was addressed by introducing multiple layers of perceptrons. It's also called a **shallow neural network** 

**Dimensionality of a layer** is the number of units in a layer

---

### Architecture of an MLP
---

The hyperparameters determine the network structure and how the network is trained, and should be set before optimizing weights and bias. 

>[!NOTE] 
>There is not a systematic way to choose hyperparameters, it comes from trial and error

The architecture of an MLP consists of:
1. The number of nodes of the hidden layer
2. The number of layers
3. Activation functions

Having more **number of layers** increases the complexity of problems the MLP can handle, **but can also lead to underfitting and overfitting**.

---

### Selecting an Activation Function
---

If we want to train a neural network with backpropogation, the activation function needs to be:
1. Continuous
2. Differentiable

>[!NOTE]
>You can combine different activation functions, for example:
> - In regression or function approximation, since we need real outputs, we can use linear activation in the output layers and other non-linear activation functions in the hidden layers 
> - For classification tasks, sigmoid or tanh functions are used in the hidden layers as they squash the inputs into a limited range and bring out useful non-linear properties

**Remember:** You CANNOT choose sigmoid or tanh activation functions for **multi-class classification** in the output layer

**Activation function has a critical impact on the speed of the training**

---

### Multilayer Perceptron: Effect of weights and bias
---

![Pasted image 20250921184243.png](/img/user/Artificial%20Intelligence/Natural%20Language%20Processing/Assets/Pasted%20image%2020250921184243.png)

In a multilayer perceptron, changing the values of the weights, changes the smoothness of the curve. Lower values of weights produce a smoother slope like curve, while higher values produce a steeper curve.

![Pasted image 20250921184320.png](/img/user/Artificial%20Intelligence/Natural%20Language%20Processing/Assets/Pasted%20image%2020250921184320.png)

Meanwhile, changing the bias shifts where the change starts from. Essentially changes the starting position of the slope.

---

### Generalizing gradient descent to MLPs
---

In MLPs, weights need to be updated at both the input-to-hidden (assume $w_{ih}$) and hidden-to-output (assume $w_{ho}$) connections. 

The above can be done by "assigning credit or blame" to different parts of the network for the error in the final output, meaning **crediting or blaming** each weights role or contribution in producing the overall response.

This can be done by computing the rate of change of the total error ($\delta E$) with respect to each weight ($w_{ih}$ and $w_{ho}$), i.e., ($\frac{\delta E}{w_{ih}}$ and $\frac{\delta E}{w_{ho}}$), which would allow for targeted weight updates. 

---

### Forward pass and Backward pass Algorithm
---

**Forward pass computation:**
1. For each hidden unit $z_j$:
	1. Compute weighted sum of inputs: $u_j$ = $\sum_{i} w_{ih} x_i$ 
	2. Apply activation function: $z_j$ = g($u_j$)
	
2. For each output unit $y_k$:
	1. Sum outputs from hidden layer: $a_k$ = $\sum_{j} w_{ho} z_j$
	2. Apply activation function: $y_k$ = g($a_k$)


**Backward pass computation:**
1. Update each weight using the gradient descent:
	1. $w_{ih}$ = $w_{ih}$ - $\lambda \frac{\partial E}{\partial w_{ih}}$
	2. $w_{ho}$ = $w_{ho} - $\lambda \frac{\partial E}{\partial w_{ho}}$
where:
- $\lambda$ is the learning rate
- $E$ is the overall error (Usually mean squared error)
- The partial derivatives ($\frac{\partial E}{\partial w_{ih}}$ and $\frac{\partial E}{\partial w_{ho}}$) tells us how much each weight contributes to the error

The backpropagation algorithm works in 2 phases:
1. **Forward Phase:** Propagate the input forward through the layers to calculate the "functional signal"
2. **Backward Phase:** Propagate the error backwards through the network starting at the output units to evaluate the "error signal"
3. Update all the weights at the same time





