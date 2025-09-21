---
{"dg-publish":true,"permalink":"/artificial-intelligence/deep-learning/activation-functions/"}
---

### Monotonic Activation Function
---

A monotonic activation function is a function that is either entirely **non-increasing or non-decreasing.**

Given that the weight of a factor represents the **importance**, if the activation function is **not monotonic** then **increasing the neuron's weight might cause he opposite effect** (i.e., to have less influence) which can lead to chaotic behavior while training.

---

### Sigmoid Activation Function
---

![Pasted image 20250921180320.png](/img/user/Artificial%20Intelligence/Natural%20Language%20Processing/Assets/Pasted%20image%2020250921180320.png)

**Pros:** The sigmoid function is continuous, derivable, and monotonous.
**Cons:**
1. May cause the neural network to get stick at training time, due to the fact that if a **strongly negative input is given to the sigmoid function, the outputs it gives tend to zero**. This is called **vanishing gradients.**
2. Due to this, since neural networks use gradients to learn, this could result in model parameters being updated less regularly than usual, slowing down the learning process.

---

### Tanh or Hyperbolic Tangent Activation Function
---

![Pasted image 20250921180515.png](/img/user/Artificial%20Intelligence/Natural%20Language%20Processing/Assets/Pasted%20image%2020250921180515.png)

The tanh function is mainly used for binary classification. Essentially just a shifted version of the sigmoid.

**Pros:** The function is differentiable and monotonic, and the means of the activation function is close to zero: this makes the learning easier for forward layers.
**Cons:**
1. Tanh also suffers from **vanishing gradient** problem

---

### Linear Activation Function
---

A linear activation function simply outputs the input value itself, i.e., for an input of x, the output is x itself.

>[!Note]
>Having multiple layers with only linear activations does not increase the model's complexity, which means that using n layers with linear activations is mathematically equivalent to only having a single linear layer. This is because combining linear functions together just results in another linear function, no matter how many times they're stacked

If only linear functions are used in all layers, a neural network loses its ability to model complex, non-linear data patterns. Practically, a deep neural network built only from linear activation functions is no more powerful than a basic linear regression model. Non-linear activation functions are necessary for deep networks to learn complex structures in data.

---



