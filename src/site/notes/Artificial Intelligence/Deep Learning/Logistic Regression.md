---
{"dg-publish":true,"permalink":"/artificial-intelligence/deep-learning/logistic-regression/"}
---

 #area/DL/concept
## Concept  
---  

**Logistic Regression** is a supervised machine learning algorithm used for **binary classification** tasks. It predicts the probability of a data point belonging to one of two classes and uses a **logistic (sigmoid) function** to map predictions to a range between $[0, 1]$. Despite its name, it is primarily a **classification** algorithm, not regression.  

---

### Key Idea  
---  

Logistic Regression models the probability of the positive class ($y=1$) based on a linear combination of input features. The output is interpreted as the likelihood that a given input belongs to that class.  

---

### Mathematical Formulation  
---  

1. **Linear Combination**:  
   Compute the weighted sum of inputs:  
   $$
   z = \mathbf{w}^T \mathbf{x} + b = w_1 x_1 + w_2 x_2 + \dots + w_n x_n + b
   $$  

2. **Logistic (Sigmoid) Function**:  
   Convert $z$ into a probability:  
   $$
   \sigma(z) = \frac{1}{1 + e^{-z}}
   $$  
   where $\sigma(z)$ is the probability that the output belongs to class $1$.  

3. **Prediction**:  
   - **Positive Class**: If $\sigma(z) \geq 0.5$, predict $y = 1$.  
   - **Negative Class**: If $\sigma(z) < 0.5$, predict $y = 0$.  

---

### Cost Function  
---  

Logistic Regression minimizes the **log-loss (cross-entropy loss)** to improve predictions:  
$$
\text{Cost} = - \frac{1}{m} \sum_{i=1}^{m} \left[ y_i \log(\hat{y}_i) + (1 - y_i) \log(1 - \hat{y}_i) \right]
$$  
where:  
- $m$: Number of training examples.  
- $y_i$: True label for the $i$th example.  
- $\hat{y}_i$: Predicted probability for the $i$th example.  

The cost function is optimized using [[Artificial Intelligence/Deep Learning/Gradient Descent\|Gradient Descent]].  

---

### Properties of Logistic Regression  
---  

- **Output**: A probability in $[0, 1]$.  
- **Decision Boundary**: A linear hyperplane separates the classes in the feature space.  
- **Interpretability**: Weights ($w_i$) indicate the influence of each feature on the outcome.  

---

### Assumptions of Logistic Regression  
---  

1. **Linearly Separable Data**:  
   Logistic Regression assumes that the classes can be separated by a linear boundary.  

2. **Independent Features**:  
   Features are assumed to be independent, though the model can handle moderate correlations.  

---

### Example  
---  

>[!EXAMPLE]  
Suppose we are predicting whether a customer will purchase a product ($y=1$) based on their income ($x_1$) and age ($x_2$). Given weights $w_1=0.4$, $w_2=-0.2$, and bias $b=-3$, for a customer with income $x_1=50$ and age $x_2=30$:  

1. Compute $z$:  
   $$
   z = (0.4 \cdot 50) + (-0.2 \cdot 30) - 3 = 11
   $$  

2. Apply the sigmoid function:  
   $$
   \sigma(z) = \frac{1}{1 + e^{-11}} \approx 0.999
   $$  

3. Since $\sigma(z) \geq 0.5$, the model predicts $y=1$ (customer will purchase).  

---

### Applications  
---  

- **Medical Diagnosis**: Predicting disease presence or absence.  
- **Spam Detection**: Classifying emails as spam or not spam.  
- **Credit Scoring**: Assessing loan approval based on financial data.  

---

### Limitations  
---  

1. **Linear Decision Boundary**:  
   Logistic Regression cannot model non-linear relationships between features and the target.  

2. **Sensitivity to Outliers**:  
   Outliers can distort the model's predictions.  

3. **Feature Scaling**:  
   May require normalization for optimal performance.  

---

### Related Concepts  
---  

- [[Sigmoid Function\|Sigmoid Function]]  
- [[Artificial Intelligence/Deep Learning/Gradient Descent\|Gradient Descent]]  
- [[Cross-Entropy Loss\|Cross-Entropy Loss]]  
- [[Regularization in Machine Learning\|Regularization in Machine Learning]]  