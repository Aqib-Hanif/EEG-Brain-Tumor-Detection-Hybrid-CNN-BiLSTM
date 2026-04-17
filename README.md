# EEG Brain Tumor Detection using Hybrid 1D-CNN–BiLSTM

[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![TensorFlow 2.x](https://img.shields.io/badge/TensorFlow-2.x-orange.svg)](https://www.tensorflow.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A deep learning framework for **non‑invasive brain tumor detection** from EEG signals, combining **1D‑CNN** for feature extraction and **BiLSTM** for temporal modeling. Designed for IoT‑enabled continuous monitoring.

> 📌 **Key Result**: Hybrid model achieves **72.5% accuracy**, **0.8185 ROC‑AUC** on binary classification (tumor vs. normal) using the UCI Epileptic Seizure dataset.

---

## 📖 Overview

Brain tumors are a leading cause of cancer‑related deaths. Early detection is critical, but traditional imaging (MRI/CT) is expensive and not portable. This project explores **EEG** as a low‑cost, portable alternative.

We implemented and compared three deep learning architectures:
- **1D‑CNN** (baseline)
- **BiLSTM** (bidirectional long short‑term memory)
- **Hybrid 1D‑CNN–BiLSTM** (proposed)

The hybrid model outperforms individual models, demonstrating the benefit of joint spatial‑temporal feature learning.

---

## 📊 Dataset

**Source**: [UCI Epileptic Seizure Recognition Dataset](https://www.kaggle.com/datasets/chaditya95/epileptic-seizures-dataset) (Kaggle)

- **Samples**: 11,500 EEG recordings (1 second each, 178 Hz)
- **Classes**: 5 (1: seizure, 2: tumor, 3: healthy, 4: eyes closed, 5: eyes open)
- **Binary subset**: Tumor (class 2) vs. Normal (class 3) → 4,600 samples, balanced (2,300 each)

---

## 🏗️ Model Architecture

### Hybrid 1D‑CNN–BiLSTM
