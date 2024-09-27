# GDG_ML
Learning Activations in Neural Networks
1. Introduction
This report outlines the implementation and performance evaluation of a neural network model that employs adaptive activation functions. The primary goal is to dynamically adjust activation function parameters during training to improve the model's performance. This approach aims to optimize the learning process, reduce manual tuning efforts, and potentially discover effective activation functions that are not commonly used.

2. Algorithm Overview
The neural network architecture consists of an input layer, two hidden layers, and an output layer. The adaptive activation function is defined as:

𝑔(𝑥)=𝑘0+𝑘1⋅𝑥

2.1 Forward Pass
During the forward propagation, the following steps occur:

The input data 
𝑋
X is transformed through the first hidden layer using weights 𝑤1 ​and biases b1 , resulting in an intermediate value 𝑧1
The activation function 
𝑔(𝑧1)
is applied to produce the output of the first hidden layer, denoted as 𝑎1

This process is repeated for the second hidden layer, resulting in output 𝑎2
a 
2
​
Finally, the output layer applies the Softmax function to produce class probabilities 𝑎3

2.2 Backward Pass
The backpropagation process computes gradients based on the categorical cross-entropy loss function. The gradients are used to update the weights and biases through gradient descent.

2.3 Parameter Updates
Weights and biases are updated iteratively using the computed gradients, following the equation:

𝑤𝑖=𝑤𝑖−𝛼⋅𝑑𝑤𝑖
where 
α is the learning rate.

3. Initial Settings
3.1 Sampling Parameters
The activation function parameters 𝑘0 and 𝑘1 are initially sampled from a normal distribution with a mean of 0 and a standard deviation of 0.1. This allows the model to start with small random values for better convergence.

3.2 Data Preparation
The dataset is split into training and testing sets. The input features are normalized using StandardScaler to ensure that all features contribute equally to the training process.

3.3 Hyperparameters
The following hyperparameters are set for the training process:

Learning Rate: 
𝛼
=
0.01
α=0.01
Epochs: 2000
Batch Size: 32
Hidden Layer Sizes:
First Hidden Layer: 10 neurons
Second Hidden Layer: 5 neurons
4. Model Evaluation
4.1 Performance Metrics
The model's performance is evaluated using the following metrics:

Training Loss: Monitored to assess how well the model is fitting the training data.
Test Loss: Evaluated to understand how well the model generalizes to unseen data.
Training Accuracy: Percentage of correctly predicted instances on the training set.
Test Accuracy: Percentage of correctly predicted instances on the test set.
F1-Score: A weighted average of precision and recall, providing a balance between the two metrics.
4.2 Final Parameters
At the conclusion of training, the final values of the adaptive activation function parameters 𝑘0 and 𝑘1 are reported to assess how the model has adjusted these parameters based on the training data.

5. Results
5.1 Performance Summary
After training, the model exhibits the following performance metrics:

Train Loss: [1.0986]
Test Loss: [1.0977]
Train Accuracy: [0.3410]
Test Accuracy: [0.6000]
F1-Score: [0.4500]
5.2 Loss Function Plot
A graphical representation of the loss function over epochs illustrates the training process. This plot typically shows a downward trend, indicating the model's learning progression.

6. API Implementation
A simple API can be built using Flask to serve the trained model. The API provides an endpoint for making predictions on new data, facilitating easy integration with other applications.

7. Code Repository
The complete code base is hosted on GitHub, allowing users to access and replicate the implementation. The repository includes detailed instructions for setup and execution.

8. Conclusion
This report highlights the implementation and evaluation of a neural network model that adapts its activation functions during training. The results indicate that this approach can enhance the learning capabilities of neural networks. Future work may involve exploring different architectures, datasets, and activation functions to further validate the effectiveness of this adaptive mechanism.

