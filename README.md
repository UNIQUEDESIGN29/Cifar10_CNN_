# Cifar10_CNN_
CIFAR-10 Image Classification — From Basic CNN to ResNet-style CNN (TensorFlow)
# 🧠 CIFAR-10 Image Classification — CNN vs ResNet

This repository contains two deep-learning models built **from scratch using TensorFlow** to classify images from the **CIFAR-10 dataset**.  
The goal is to compare a **basic Convolutional Neural Network (CNN)** with a **ResNet-style CNN** that uses **skip connections** to improve accuracy and training stability.

---

## 📸 Dataset — CIFAR-10

- **Images:** 60,000 color images (32×32 pixels)  
- **Classes (10):** airplane, automobile, bird, cat, deer, dog, frog, horse, ship, truck  
- **Split:** 50,000 training images / 10,000 test images  

CIFAR-10 is automatically downloaded using TensorFlow/Keras.

---

## 🧱 Architectures

### 🔹 CNN (Baseline)
Implemented with TensorFlow **Sequential API**.

**Layers Overview**
- 3× (Conv2D → ReLU → MaxPooling)
- Flatten → Dense(128, ReLU)
- Output: Dense(10, Softmax)

**Pros:** Simple, fast to train  
**Cons:** May overfit and struggle with complex patterns

---

### 🔸 ResNet-Style CNN
Implemented with TensorFlow **Functional API** and **skip connections** (Residual Blocks).

**Layers Overview**
- Conv2D + BatchNorm + ReLU
- Multiple Residual Blocks (`x + F(x)`)
- GlobalAveragePooling → Dense(10, Softmax)

**Pros:** Handles vanishing gradients, trains deeper networks effectively  
**Cons:** Slightly more computational cost

| Metric               | CNN (Baseline) | ResNet-Style CNN   |
| -------------------- | -------------- | ------------------ |
| Training Accuracy    | ~82%           | ~91%               |
| Test Accuracy        | ~79%           | ~88%               |
| Overfitting Tendency | High           | Low                |
| Training Speed       | ✅ Fast         | ⚠️ Slightly Slower |
