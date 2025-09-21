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


