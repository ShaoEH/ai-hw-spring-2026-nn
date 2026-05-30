# Assignment #4.1: MNIST Recognition by NN 🧠

## 🎯 1. Project Objective
The goal of this project is to build and train a Convolutional Neural Network (CNN) using PyTorch to accurately recognize handwritten digits from the MNIST dataset. 

---

## 🏗️ 2. Model Architecture
The model uses a custom CNN architecture designed to extract spatial features effectively while preventing overfitting using Dropout layers.

| Layer Type | Configuration | Activation Function |
| :--- | :--- | :--- |
| **Conv2D** | Input: 1, Output: 64, Kernel: 3x3, Stride: 1 | ReLU |
| **Conv2D** | Input: 64, Output: 128, Kernel: 3x3, Stride: 1 | ReLU |
| **MaxPooling2D** | Kernel: 2x2 | - |
| **Dropout** | Probability: 0.3 | - |
| **Flatten** | 18432 features | - |
| **Linear (Dense)** | Input: 18432, Output: 256 | ReLU |
| **Dropout** | Probability: 0.4 | - |
| **Linear (Dense)** | Input: 256, Output: 10 (Classes) | - |

---

## ⚙️ 3. Hyperparameters & Setup
To improve model robustness, I applied **Data Augmentation** during the training phase, specifically a random rotation of up to 20 degrees.

* **Optimizer:** Adam
* **Learning Rate:** 0.0001
* **Loss Function:** Cross-Entropy Loss
* **Epochs (Rounds):** 5
* **Batch Size:** 64
* **Hardware:** Trained on GPU (CUDA)

---

## 📊 4. Training Results
The model converged quickly and achieved excellent performance on the unseen validation dataset within just 5 epochs.

* **Final Training Loss:** 0.06449
* **Validation Accuracy:** **99.09%**

### Loss Progression
<img width="576" height="455" alt="image" src="https://github.com/user-attachments/assets/6c6f2f33-15ce-47c5-8b40-70ad9407b10b" />

---

## 💡 5. Conclusion & Challenges
The combination of two Convolutional layers and an aggressive Dropout strategy (0.3 and 0.4) effectively prevented overfitting, allowing the model to achieve over **99% accuracy**. The addition of random rotation during training also ensured the model is robust against slightly tilted handwriting.



