# 🧠 EEG Brain Tumor Detection using Hybrid 1D-CNN–BiLSTM

[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![TensorFlow 2.x](https://img.shields.io/badge/TensorFlow-2.x-orange.svg)](https://www.tensorflow.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A deep learning framework for **non-invasive brain tumor detection from EEG signals**, combining **1D-CNN** for spatial feature extraction and **BiLSTM** for temporal sequence modeling. Designed for **AI-enabled healthcare monitoring systems** and future IoT deployment.

> 📌 **Key Result:** Hybrid model achieves **72.46% accuracy** and **0.8185 ROC-AUC** for EEG-based binary classification (tumor vs normal).

---

## 📖 Overview

Brain tumors are critical neurological conditions where early detection significantly improves survival rates. Conventional imaging techniques (MRI, CT scans) are accurate but expensive, non-continuous, and infrastructure-dependent.

⚡ **EEG (Electroencephalography)** provides a low-cost, real-time alternative by capturing brain electrical activity.

Tumor-related EEG patterns often include:
- ⚠️ Focal slowing in delta (0.5–4 Hz) and theta (4–8 Hz) bands  
- ⚡ Abnormal neural oscillations  
- 🔄 Disrupted brain synchronization patterns  

This project investigates deep learning-based EEG classification using:

- 🧠 **1D-CNN** → spatial feature extraction  
- 🔁 **BiLSTM** → temporal dependency learning  
- 🔗 **Hybrid CNN–BiLSTM** → proposed architecture  

---

## 📊 Dataset

📁 Source: UCI Epileptic Seizure Recognition Dataset (Kaggle version)

| 📌 Property | 📊 Value |
|------------|--------|
| Total Samples | 11,500 |
| Sampling Rate | 178 Hz |
| Duration | 1 second per sample |
| Channels | Single-channel EEG |
| Original Classes | 5 EEG categories |

### 🔄 Binary Conversion (This Study)

- 🧠 Class 2 → Tumor (1)  
- 🙂 Class 3 → Normal (0)  
- ⚖️ Final dataset: **4,600 balanced samples**

---

## 🏗️ Model Architecture

```
Input (178 time steps)
        ↓
🧠 Conv1D (64 filters) + ReLU + MaxPooling
        ↓
🧠 Conv1D (128 filters) + ReLU + MaxPooling
        ↓
🧠 Conv1D (256 filters) + ReLU + GlobalMaxPooling
        ↓
🔁 Bidirectional LSTM (64 units)
        ↓
🎯 Dropout (0.5)
        ↓
🧠 Dense (64, ReLU)
        ↓
🎯 Dropout (0.5)
        ↓
🎯 Dense (1, Sigmoid)
```

### ⚙️ Hyperparameters

- ⚡ Optimizer: Adam (lr = 0.001)  
- 📉 Loss: Binary Cross-Entropy  
- 📦 Batch Size: 32  
- 🔁 Epochs: 50  
- 🛑 Early Stopping: patience = 10  
- 🔄 Validation: 5-Fold Stratified Cross-Validation  

---

## 📈 Results

| 🧠 Model   | 🎯 Accuracy | 📌 Precision | 🔁 Recall | 📊 F1-score | 📉 ROC-AUC |
|-----------|------------|-------------|----------|------------|-----------|
| CNN       | 0.6913     | 0.7025      | 0.6638   | 0.6826     | 0.7557    |
| BiLSTM    | 0.5391     | 0.5860      | 0.2667   | 0.3665     | 0.5689    |
| 🔗 Hybrid | **0.7246** | **0.7141**  | **0.7493** | **0.7313** | **0.8185** |

---

## 🧠 Discussion

### ✅ Strengths
- Hybrid spatial + temporal EEG learning  
- Explainable AI (Grad-CAM support)  
- Reproducible pipeline  
- Strong baseline for EEG tumor detection  

### ⚠️ Limitations
- Moderate accuracy (~72%)  
- Dataset not tumor-specific  
- No multi-channel EEG  
- Binary classification only  

### 🚀 Future Work
- Multi-channel EEG datasets (TUH EEG Corpus)  
- Multi-class neurological classification  
- Real-time IoT deployment  
- Attention-based architectures  
- Clinical validation  

---

## 👨‍💻 Author

**Aqib Hanif**  
🧠 Researcher | 🤖 Machine Learning Engineer | 📊 EEG Signal Processing  

---

## 📧 Contact

📩 Email: Aqibhanifofficail1@gmail.com  

---

## 📄 License

MIT License  

---

## 🙏 Acknowledgements

- 🏛️ UCI Machine Learning Repository  
- 📊 Kaggle dataset contributors  
- 🔥 TensorFlow & Keras team  
- 🌍 Open-source scientific Python community  
