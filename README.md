# 🌿 Plant Disease Detection using Deep Learning

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![TensorFlow](https://img.shields.io/badge/TensorFlow-2.0+-orange.svg)](https://www.tensorflow.org/)
[![ResNet50](https://img.shields.io/badge/Architecture-ResNet50-red.svg)](https://arxiv.org/abs/1512.03385)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

> **AI-powered system for early and accurate detection of plant diseases from leaf images using ResNet50 convolutional neural network**

---

## 📋 Table of Contents
- [Overview](#-overview)
- [Why This Matters](#-why-this-matters)
- [Key Features](#-key-features)
- [System Architecture](#-system-architecture)
- [Dataset](#-dataset)
- [Methodology](#-methodology)
- [Installation](#-installation)
- [Usage](#-usage)
- [Results](#-results)
- [Future Work](#-future-work)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🌾 Overview

Agriculture is the backbone of many economies and a critical pillar of global food security. However, plant diseases threaten crop quality and yield, leading to significant economic losses and reduced food production.

**Traditional methods** rely on manual expert inspection – which is:
- ⏱️ Time-consuming
- 💰 Costly
- 📉 Often inaccurate when done by non-specialists

**Our solution** leverages **Deep Learning** and **ResNet50 CNN architecture** to automatically identify and classify plant diseases from leaf images with high accuracy, speed, and reliability.

---

## 🎯 Why This Matters

| Problem | Impact | Our Solution |
|---------|--------|---------------|
| Late disease detection | 20-40% crop loss | Early, real-time diagnosis |
| Expert dependency | High costs & delays | Fully automated system |
| Manual errors | Misdiagnosis | Consistent AI-powered classification |
| Limited reach | Rural farmers left behind | Simple image upload interface |

✅ **Fast** – Results in seconds  
✅ **Reliable** – High accuracy using pre-trained ResNet50  
✅ **Cost-effective** – No expert required  
✅ **User-friendly** – Simple web/mobile interface  

---

## ✨ Key Features

- 🔍 **Automatic Disease Detection** – Upload a leaf image, get instant diagnosis  
- 🧠 **Deep Learning Powered** – ResNet50 with transfer learning  
- 📸 **Supports Multiple Diseases** – Learns from color changes, spots, lesions & texture patterns  
- 🌱 **Healthy vs. Diseased Classification** – Binary and multi-class support  
- 📊 **Data Augmentation** – Improves generalization and robustness  
- 🖥️ **Easy Integration** – REST API / Web interface ready  

---

## 🏗️ System Architecture

```mermaid
graph LR
    A[Input Leaf Image] --> B[Preprocessing]
    B --> C{Resize & Normalize}
    C --> D[Data Augmentation]
    D --> E[ResNet50 Base Model]
    E --> F[Custom Classification Head]
    F --> G[Disease Prediction]
    G --> H[Output: Disease Name / Healthy]
