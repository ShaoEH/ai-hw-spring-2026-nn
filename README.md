# Assignment #4.1: MNIST Recognition - Model Architecture Comparison 🧠

## 🎯 1. Project Objective
The goal of this expanded project is to train and compare the performance of three distinct neural network architectures on the MNIST dataset. By evaluating a Shallow MLP, a Convolutional Neural Network (CNN), and a Vision-based Transformer Encoder, we can analyze their convergence speed and final accuracy.

---

## ⚙️ 2. Data Preprocessing & Setup
To ensure the models are robust against handwriting variations, **Data Augmentation** was applied during the training phase.
* **Augmentation**: Random rotation of up to 20 degrees.
* **Global Parameters**: 
  * Loss Function: Cross-Entropy Loss.
  * Training Epochs (Rounds): 5.
  * Batch Size: 64.
  * Hardware: Trained on GPU (CUDA).

---

## 🏗️ 3. Model Architectures & Hyperparameters
We designed three separate models with architecture-specific learning rates using the Adam optimizer:

### 🔸 Model 1: Shallow MLP (Multi-Layer Perceptron)
* **Structure**: Flatten layer -> Linear layer (128 units) -> ReLU -> Linear output (10 classes).
* **Optimizer Setting**: Adam with Learning Rate = 0.001.

### 🔸 Model 2: CNN (Convolutional Neural Network)
* **Structure**: 2 Conv2D layers -> MaxPooling2D -> Dropout (0.3) -> Flatten -> Linear (256 units) -> Dropout (0.4) -> Linear output.
* **Optimizer Setting**: Adam with Learning Rate = 0.0001.

### 🔸 Model 3: Transformer (Encoder-Only)
* **Structure**: Linear Input Projection -> Positional Encoding -> Transformer Encoder (2 layers, 4 heads, dropout 0.1) -> Mean Pooling -> Linear output.
* **Optimizer Setting**: Adam with Learning Rate = 0.0005.

---

## 📊 4. Training Results & Comparison
All three models were trained under the exact same conditions (5 epochs). The results clearly show how different architectures handle spatial image data.

| Model Architecture | Final Test Accuracy |
| :--- | :--- |
| **Shallow MLP** | **97.80%** |
| **CNN** | **99.12%** |
| **Transformer (Encoder)** | **97.43%** |

### Loss & Accuracy Progression
<img width="846" height="547" alt="image" src="https://github.com/user-attachments/assets/ff4ecc2a-c34a-44fd-b26f-826e87e5a071" />


---

## 💡 5. Conclusion
* The **Shallow MLP** provides a strong baseline, converging quickly but lacking spatial awareness of the image.
* The **CNN** achieved the highest accuracy (**99.12%**), proving that convolutional filters are highly effective at capturing local pixel features (edges, curves) in image data.
* The **Transformer Encoder** introduces a sequence-based attention mechanism to images, demonstrating how modern attention architectures can be adapted for traditional computer vision tasks.
