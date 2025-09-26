---
{"dg-publish":true,"permalink":"/artificial-intelligence/deep-learning/convolutional-neural-networks-cn-ns/"}
---

#area/DL/concept
## Concept  
---  

**Convolutional Neural Networks (CNNs)** are specialized types of neural networks designed for processing structured data like images. They excel at tasks like image recognition, object detection, and other tasks that involve spatial or temporal hierarchies. CNNs use **convolutional layers** to detect patterns such as edges, textures, or more complex features.

---

### Key Components  
---  

1. **Input Layer**:  
   Accepts structured data, often a multi-dimensional array (e.g., an image as a tensor with dimensions height × width × channels).

2. **Convolutional Layer**:  
   Applies convolutional operations using filters (kernels) to extract features from the input.  
   - **Filter**: A small matrix that slides over the input and performs dot products to create a feature map.  
   - **Stride**: The step size of the filter's movement.  
   - **Padding**: Adding extra pixels around the input to control the size of the output.  

3. **Activation Function**:  
   Introduces non-linearity, typically using **ReLU**:  
   $$
   \text{ReLU}(x) = \max(0, x)
   $$  

4. **Pooling Layer**:  
   Reduces the spatial dimensions of the feature map while retaining the most important information.  
   - **Max Pooling**: Retains the maximum value from a region.  
   - **Average Pooling**: Computes the average value of a region.  

5. **Fully Connected Layer**:  
   Connects the high-level features extracted by convolutional layers to the output layer for classification or regression tasks.  

6. **Output Layer**:  
   Produces the final predictions using an appropriate activation function:  
   - **Softmax** for multi-class classification.  
   - **Sigmoid** for binary classification.  

---

### Architecture  
---  

A typical CNN consists of:  
- **Stacked Convolutional Layers**: To extract hierarchical features.  
- **Pooling Layers**: To down-sample the feature maps.  
- **Dropout Layers**: To prevent overfitting by randomly disabling neurons during training.  
- **Dense Layers**: For high-level reasoning and final predictions.  

---

### Advantages of CNNs  
---  

1. **Parameter Sharing**:  
   Filters are shared across the input, reducing the number of parameters.  

2. **Sparse Interactions**:  
   Each filter interacts with a small region (receptive field) of the input, allowing local feature extraction.  

3. **Translation Invariance**:  
   CNNs can recognize patterns regardless of their location in the input.  

---

### Applications  
---  

1. **Image and Video Recognition**:  
   Tasks such as object detection, face recognition, and scene understanding.  

2. **Medical Imaging**:  
   Diagnosing diseases from X-rays, MRIs, or CT scans.  

3. **Natural Language Processing**:  
   Text classification, sentence modeling, and document categorization.  

4. **Reinforcement Learning**:  
   Processing visual input in environments like games or robotics.  

---

### Example  
---  

>[!EXAMPLE]  
Suppose we input a grayscale image of size $28 \times 28$ into a CNN:  
1. **Convolution**: Apply a $3 \times 3$ filter with stride 1 and no padding, producing a feature map of size $26 \times 26$.  
2. **Pooling**: Use $2 \times 2$ max pooling with stride 2, reducing the size to $13 \times 13$.  
3. **Fully Connected Layer**: Flatten the feature map and connect it to a dense layer for classification.  

---

### Limitations  
---  

1. **Data Intensity**:  
   CNNs require large datasets for effective training.  

2. **Computational Requirements**:  
   High computational power and memory are needed, especially for deeper networks.  

3. **Overfitting**:  
   Without sufficient data or regularization, CNNs can overfit.  

---

### Related Concepts  
---  

- [[Convolution Operation\|Convolution Operation]]  
- [[Pooling Layers\|Pooling Layers]]  
- [[ReLU Activation Function\|ReLU Activation Function]]  
- [[Transfer Learning\|Transfer Learning]]  
- [[Areas/Deep Learning\|Deep Learning]]  