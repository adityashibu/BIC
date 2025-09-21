---
{"dg-publish":true,"permalink":"/artificial-intelligence/deep-learning/perceptron/"}
---

#area/DL/concept

## Concept  
---  

The **Perceptron** is a fundamental building block of neural networks and one of the earliest types of artificial neurons. It is a **binary classifier** that predicts whether an input belongs to one of two classes based on a set of weights and a threshold.

---

### Components of a Perceptron  
---  

1. **Input Features** ($x_1, x_2, \dots, x_n$):  
   Represent the attributes of the data point being classified.

2. **Weights** ($w_1, w_2, \dots, w_n$):  
   Associated with each input feature, they determine the importance of each feature.

3. **Bias** ($b$):  
   A constant added to the weighted sum of inputs to adjust the decision boundary.

4. **Activation Function**:  
   Applies a threshold to the weighted sum of inputs, outputting either 0 or 1.  
   - Commonly used function:  
     $$
     y = 
     \begin{cases} 
     1 & \text{if } \sum_{i=1}^n w_i x_i + b \geq 0 \\
     0 & \text{otherwise} 
     \end{cases}
     $$  

---

### Working of a Perceptron  
---  

1. **Weighted Sum**:  
   Compute the weighted sum of inputs:  
   $$
   z = \sum_{i=1}^n w_i x_i + b
   $$  

2. **Thresholding**:  
   Apply the activation function to decide the output. If $z \geq 0$, output is 1; otherwise, it is 0.

3. **Training**:  
   Adjust the weights and bias based on errors to minimize misclassifications.  

---

### Perceptron Learning Algorithm  
---  

1. Initialize weights and bias to small random values.  
2. For each training example $(\mathbf{x}, y)$:  
   - Predict the output $\hat{y}$ using the current weights.  
   - Update weights if the prediction is incorrect:  
     $$
     w_i \gets w_i + \Delta w_i \quad \text{where } \Delta w_i = \eta (y - \hat{y}) x_i
     $$  
     $$
     b \gets b + \eta (y - \hat{y})
     $$  
     Here, $\eta$ is the learning rate, and $y$ is the true label.  

3. Repeat until the weights converge or for a set number of iterations.  

---

### Limitations  
---  

1. **Linearly Separable Data**:  
   The perceptron can only classify data that is linearly separable. For non-linearly separable data, it fails to converge.  

2. **No Multi-class Support**:  
   A single perceptron cannot handle multi-class classification problems directly.  

3. **Lack of Complex Decision Boundaries**:  
   It cannot model complex functions like XOR.  

---

### Extensions  
---  

- The limitations of the perceptron were overcome with the introduction of the [[Artificial Intelligence/Deep Learning/Multilayer Perceptron (MLP)\|Multilayer Perceptron (MLP)]], which uses multiple layers and nonlinear activation functions to handle complex problems.  

---

### Example  
---  

>[!EXAMPLE]  
Suppose you have two input features, $x_1$ and $x_2$, and the weights $w_1 = 0.5$, $w_2 = -0.5$, with a bias $b = 0.2$. For an input $(x_1, x_2) = (1, 1)$:  

$$
z = (0.5 \cdot 1) + (-0.5 \cdot 1) + 0.2 = 0.2
$$  

Since $z \geq 0$, the output is 1.  

---

### Related Concepts  
---  

- [[Linear Separability\|Linear Separability]]  
- [[Artificial Intelligence/Deep Learning/Gradient Descent\|Gradient Descent]]  
- [[Artificial Intelligence/Deep Learning/Multilayer Perceptron (MLP)\|Multilayer Perceptron (MLP)]]  
- [[Artificial Intelligence/Deep Learning/Activation Functions\|Activation Functions]]  