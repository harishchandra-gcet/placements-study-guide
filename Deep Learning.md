© 2026 Geethanjali Group of Institutions. All Rights Reserved. Unauthorized use or distribution is prohibited.

# Deep Learning

## 1. Artificial Neural Networks (ANN) & Backpropagation

An ANN is a computational model inspired by the biological brain. It consists of an **Input Layer**, **Hidden Layers**, and an **Output Layer**.

### Core Components

* **Weights ():** Determine the strength of the connection between neurons.
* **Bias ():** Allows the activation function to shift, helping the model fit the data better.
* **Forward Propagation:** The process where input data is passed through the network to get an output: , followed by an activation .

### How Backpropagation Works (Interview Gold)

Backpropagation is the mathematical engine used to update weights to minimize the **Loss Function**. It uses the **Chain Rule** from calculus.

1. **Calculate Error:** The difference between the predicted output and the actual target.
2. **Gradient Calculation:** Calculate the gradient of the loss function with respect to each weight by working backward from the output layer to the input layer.
3. **Update Weights:** Adjust weights using the formula: , where  is the learning rate.



## 2. Convolutional Neural Networks (CNN) - Image Data

CNNs are designed to process pixel data by capturing spatial hierarchies (edges  shapes  objects).

### Key Layers

* **Convolutional Layer:** Uses **Filters (Kernels)** to scan the image. A filter performs a dot product with the input to create a **Feature Map**.
* **Stride:** The number of pixels the filter moves at a time.
* **Padding:** Adding zeros around the image border to ensure the output size remains the same or to capture edge information.
* **Pooling Layer:** Reduces the spatial dimensions (downsampling).
* **Max Pooling:** Takes the maximum value from a window (captures the most prominent feature).
* **Average Pooling:** Takes the average.


* **Fully Connected (FC) Layer:** At the end, features are flattened and passed to a standard ANN for final classification.



## 3. Sequential Models: RNN, LSTM, and GRU

Used for data where order matters (Text, Time-Series, Audio).

### Recurrent Neural Networks (RNN)

RNNs have "memory"—the output of a previous step is fed as input to the current step.

* **The Flaw:** They suffer from the **Vanishing Gradient Problem**, making it hard for them to remember long-term dependencies.

### LSTM (Long Short-Term Memory)

LSTMs solve the vanishing gradient problem using a **Cell State** (the "long-term memory") and **Gates**:

1. **Forget Gate:** Decides what information to discard from the cell state.
2. **Input Gate:** Decides which new information to store in the cell state.
3. **Output Gate:** Decides what the next hidden state should be.

### GRU (Gated Recurrent Unit)

A simplified version of LSTM.

* It combines the Forget and Input gates into a single **Update Gate**.
* It has no separate Cell State (uses only the Hidden State).
* **Advantage:** Faster to train and requires less memory than LSTM.



## 4. Activation Functions

Activation functions introduce **Non-linearity**, allowing the network to learn complex patterns.

| Function | Best Use Case | Pros/Cons |
| --- |  --- | --- |
| **Sigmoid** | Binary Classification (Output Layer) | Range (0 to 1). Suffers from Vanishing Gradient. |
| **Tanh** | Hidden Layers | Range (-1 to 1). Zero-centered, but still has vanishing gradients. |
| **ReLU** | **Hidden Layers (Standard)** | Range (0 to ). Solves vanishing gradient; computationally efficient. |



## 5. Optimizers

Optimizers adjust the weights and learning rate to reduce the loss.

* **Stochastic Gradient Descent (SGD):** Updates weights for every single training example. It is noisy but helps escape local minima.
* **Adam (Adaptive Moment Estimation):** The most popular choice. It computes individual adaptive learning rates for different parameters by using estimates of first and second moments of the gradients. It combines the benefits of **Momentum** and **RMSProp**.



## 6. Overfitting Prevention

Overfitting occurs when a model learns the "noise" in the training data rather than the actual signal, leading to poor performance on test data.

* **Dropout:** During training, randomly "drop out" (set to zero) a percentage of neurons in a layer. This prevents neurons from becoming overly dependent on each other and forces the network to learn more robust features.
* **Early Stopping:** Monitor the validation loss during training. As soon as the validation loss starts increasing (even if training loss is still decreasing), stop the training.



## 7. Example Interview Q&A

**Q: Why do we use ReLU instead of Sigmoid in hidden layers?**
**A:** ReLU is computationally faster because it only involves a threshold at zero. More importantly, it solves the **Vanishing Gradient Problem**. For large positive inputs, the gradient of Sigmoid becomes almost zero, which stops the network from learning. ReLU has a constant gradient of 1 for all positive inputs.

**Q: What is the main difference between CNN and RNN?**
**A:** * **CNN** is designed for **spatial data** (images). It uses filters to capture patterns in different parts of an image simultaneously.

* **RNN** is designed for **sequential data** (time-series/text). It processes data one step at a time and maintains a hidden state to "remember" previous inputs.

**Q: When would you choose GRU over LSTM?**
**A:** Choose **GRU** when you have a smaller dataset or limited computational power. Because GRUs have fewer parameters (two gates instead of three), they train faster and are less prone to overfitting on small data.

**Q: How does Dropout work during the Test phase?**
**A:** Dropout is **only active during training**. During the test (inference) phase, all neurons are used, but their outputs are scaled down by the dropout rate to ensure the total input to the next layer is consistent with what the model saw during training.
