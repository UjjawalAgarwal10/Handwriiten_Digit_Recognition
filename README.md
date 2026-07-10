# Handwritten Digit Recognition (MNIST)
- A neural network project that classifies handwritten digits (0–9) from the **MNIST** dataset using TensorFlow/Keras.
- Two dense (fully-connected) neural networks with different activation functions are built, trained, and compared to select the best-performing model.

## Overview
This project:
- Loads and visualizes the MNIST handwritten digits dataset.
- Builds two feed-forward neural network architectures (ReLU vs Sigmoid activations).
- Trains and evaluates both models.
- Compares them using training/validation accuracy, generation gap, and parameter count.
- Selects the best model and analyzes its predictions using a confusion matrix and sample predictions.

## Dataset
The [MNIST dataset](http://yann.lecun.com/exdb/mnist/) is loaded directly via `tensorflow.keras.datasets.mnist`. It consists of:
- **60,000** training images (28x28 grayscale)
- **10,000** test images (28x28 grayscale)
- 10 classes representing digits 0–9

## Model Architectures:
Below shows that both models share the same structure but differ in their hidden layer activation function:
| Layer | Model 1 | Model 2 |
|---|---|---|
| Input | 28x28 | 28x28 |
| Flatten | 784 | 784 |
| Dense (Hidden 1) | 64 units, **ReLU**, L2 regularization | 64 units, **Sigmoid**, L2 regularization |
| Dense (Hidden 2) | 64 units, **ReLU**, L2 regularization | 64 units, **Sigmoid**, L2 regularization |
| Dense (Output) | 10 units, Softmax | 10 units, Softmax |

**Compilation settings (both models):**
- Optimizer: `adam`
- Loss: `sparse_categorical_crossentropy`
- Metric: `accuracy`

**Training settings:**
- Model 1: 20 epochs, batch size 32, 20% validation split
- Model 2: 18 epochs, batch size 32, 20% validation split
- Random seed fixed at `42` for reproducibility
