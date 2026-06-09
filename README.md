# 🌿 Plant Disease Detection using Deep Learning

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![TensorFlow](https://img.shields.io/badge/TensorFlow-2.0+-orange.svg)](https://www.tensorflow.org/)
[![ResNet50](https://img.shields.io/badge/Architecture-ResNet50-red.svg)](https://arxiv.org/abs/1512.03385)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

> **Early and accurate detection of plant diseases to prevent crop loss and improve agricultural productivity using AI & Computer Vision.**

---

## 📌 Table of Contents

- [Overview](#-overview)
- [Motivation](#-motivation)
- [Features](#-features)
- [System Architecture](#-system-architecture)
- [Dataset](#-dataset)
- [Model: ResNet50 + Transfer Learning](#-model-resnet50--transfer-learning)
- [Preprocessing & Augmentation](#-preprocessing--augmentation)
- [Installation & Setup](#-installation--setup)
- [Usage](#-usage)
- [Results](#-results)
- [Future Scope](#-future-scope)
- [Contributing](#-contributing)
- [License](#-license)
- [Acknowledgments](#-acknowledgments)

---

## 🌾 Overview

Agriculture is the backbone of many economies, yet plant diseases cause **20–40% of global crop losses** annually. Traditional manual inspection by experts is slow, expensive, and often inaccessible to small-scale farmers.

This project presents an **AI-powered Plant Disease Detection System** using the **ResNet50** deep learning model. By simply uploading a leaf image, the system instantly classifies it as **healthy** or **diseased** and identifies the specific disease type. This tool empowers farmers and agricultural experts to take timely action, reducing losses and improving food security.

---

## ❓ Motivation

- 🧑‍🌾 **Smallholder farmers** lack access to plant pathologists.
- ⏱️ Manual inspection is time-consuming and subjective.
- 🦠 Delayed detection allows diseases to spread rapidly.
- 🤖 **Deep learning** offers a fast, scalable, and accurate alternative.

Our goal is to democratize plant disease diagnosis using just a smartphone or a camera.

---

## ✨ Features

✅ **Automated Disease Classification** – Identifies diseases from leaf images.  
✅ **ResNet50 Backbone** – Leverages a powerful pretrained CNN for high accuracy.  
✅ **Transfer Learning** – Fine-tuned on plant leaf datasets for superior performance.  
✅ **Data Augmentation** – Improves model generalization (rotation, flipping, zoom).  
✅ **User-Friendly Interface** – Upload an image and get instant results.  
✅ **Scalable** – Can be extended to more crops and diseases.

---

## 🏗️ System Architecture

graph LR
    A[Input Leaf Image] --> B[Preprocessing]
    B --> C{Resize & Normalize}
    C --> D[Data Augmentation]
    D --> E[ResNet50 Base Model]
    E --> F[Custom Classification Head]
    F --> G[Disease Prediction]


---

## 📊 Dataset

The model is trained on a comprehensive dataset of **plant leaf images** containing:

- Healthy leaves
- Leaves infected with various diseases (e.g., rust, blight, mildew, spots)

> *Example public datasets used:*  
> - [PlantVillage Dataset](https://www.kaggle.com/datasets/emmarex/plantdisease)  
> - Custom collected images (if applicable)

Each image is labeled and split into **training (80%)**, **validation (10%)**, and **testing (10%)** sets.

---

## 🤖 Model: ResNet50 + Transfer Learning

**ResNet50** is a 50-layer deep CNN that introduced **residual connections**, allowing it to train very deep networks without vanishing gradients. We leverage:

- **Pretrained weights** from ImageNet (1.4M images, 1000 classes).
- **Transfer learning** – Replace the top classification layer with a new dense layer adapted to `N` plant disease classes.
- **Fine-tuning** – Unfreeze the last few layers to learn disease-specific features.

**Why ResNet50?**  
- High accuracy on image classification benchmarks.  
- Extracted features are generalizable (edges, textures, patterns).  
- Faster convergence than training from scratch.

---

## 🛠️ Preprocessing & Augmentation

| Step               | Description                                   |
|--------------------|-----------------------------------------------|
| **Resizing**       | All images resized to `224×224` pixels (ResNet50 input size). |
| **Normalization**  | Pixel values scaled to `[0,1]` or standardized. |
| **Data Augmentation** | Random rotations, width/height shifts, zoom, horizontal flip. |

Augmentation helps prevent overfitting and makes the model robust to real-world leaf photos (different angles, lighting conditions).

---

## 💻 Installation & Setup

### Prerequisites

- Python 3.8+
- pip / conda
- (Optional) GPU with CUDA for faster training

### Clone the Repository

```bash
git clone https://github.com/yourusername/plant-disease-detection.git
cd plant-disease-detection
