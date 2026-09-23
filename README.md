# 🦠 Malaria Detection Using CNN

A **deep learning project** that uses a **Convolutional Neural Network (CNN)** built with the **Keras Functional API** to classify microscopic blood cell images as **Parasitized** or **Uninfected**.

This project is part of my journey into **Deep Learning and Medical AI**, exploring how neural networks can be applied to medical image classification.

---

## 📌 Project Overview

Malaria is a parasitic disease caused by *Plasmodium* species. Microscopic examination of stained blood films is commonly used to identify malaria parasites.

In this project, I built and trained a **CNN from scratch** to classify blood cell images into two categories:

- 🦠 **Parasitized** — cells containing malaria parasites
- 🔬 **Uninfected** — cells without visible malaria parasites

The main goal was to practice the complete deep learning workflow:

**Data Preparation → Image Preprocessing → CNN Design → Training → Validation → Evaluation**

> [!NOTE]
> This is an **educational deep learning project**. My main goal was to understand and implement the fundamentals of CNN-based image classification rather than build a fully optimized clinical system.

---

## 📊 Dataset

The project uses the **Cell Images for Detecting Malaria** dataset available on **Kaggle**.

🔗 **Dataset:** [Cell Images for Detecting Malaria](https://www.kaggle.com/datasets/iarunava/cell-images-for-detecting-malaria)

The dataset contains **27,558 cell images**:

| Class | Images |
|---|---:|
| **Parasitized** | 13,778 |
| **Uninfected** | 13,780 |
| **Total** | **27,558** |

The dataset is downloaded using the **Kaggle API** within the notebook.

---

## 🧠 Model Architecture

The CNN was built from scratch using the **Keras Functional API**.

### **Input Shape**

```python
(64, 64, 3)
```

### **CNN Architecture**

```text
Input (64 × 64 × 3)
        │
        ▼
Conv2D (32 filters, 3×3, ReLU)
        │
MaxPooling2D (2×2)
        │
BatchNormalization
        │
Dropout (0.25)
        │
        ▼
Conv2D (32 filters, 3×3, ReLU)
        │
MaxPooling2D (2×2)
        │
BatchNormalization
        │
Dropout (0.25)
        │
        ▼
Flatten
        │
Dense (512, ReLU)
        │
BatchNormalization
        │
Dropout (0.25)
        │
        ▼
Dense (512, ReLU)
        │
BatchNormalization
        │
Dropout (0.25)
        │
        ▼
Dense (2, Sigmoid)
```

The complete network contains approximately **4.47 million parameters**.

---

## ⚙️ Training Configuration

| Parameter | Value |
|---|---|
| **Optimizer** | Adam |
| **Loss Function** | Binary Cross-Entropy |
| **Metric** | Accuracy |
| **Batch Size** | 64 |
| **Epochs** | 3 |
| **Validation Split** | 10% |
| **Test Split** | 20% |
| **Random State** | 42 |

### **Dataset Split**

```text
Training samples: 22,046
Testing samples:   5,512
```

---

## 📈 Results

After training for **3 epochs**, the model achieved:

# 🎯 Test Accuracy: **95.45%**

### **Training History**

| Epoch | Training Accuracy | Validation Accuracy |
|:---:|---:|---:|
| **1** | **99.67%** | **95.69%** |
| **2** | **99.77%** | **95.92%** |
| **3** | **99.85%** | **95.46%** |

The notebook also visualizes the **training and validation accuracy and loss curves** to examine the model's learning behavior.

The gap between training and validation performance suggests some **overfitting**.

Further optimization was intentionally left for future projects because the primary objective here was to **learn and implement the complete CNN workflow**.

---

## 🛠️ Technologies Used

- **Python**
- **TensorFlow**
- **Keras**
- **Keras Functional API**
- **NumPy**
- **OpenCV**
- **Pillow**
- **Matplotlib**
- **Scikit-learn**
- **Kaggle API**
- **Jupyter Notebook / Google Colab**

---

## 🔄 Project Workflow

```text
Kaggle Dataset
      ↓
Load Cell Images
      ↓
Resize Images to 64 × 64
      ↓
Convert Images to NumPy Arrays
      ↓
Encode Labels
      ↓
Train / Test Split
      ↓
Build CNN with Keras Functional API
      ↓
Train Model
      ↓
Evaluate on Test Data
      ↓
Visualize Performance
```

---

## 🚀 Future Improvements

This project represents one of my **first steps into deep learning and medical image analysis**.

As I continue working on more advanced projects, possible improvements include:

- [ ] **Image normalization**
- [ ] **Data augmentation**
- [ ] Deeper CNN architectures
- [ ] Hyperparameter tuning
- [ ] Early stopping
- [ ] Learning-rate scheduling
- [ ] Confusion matrix
- [ ] Precision, Recall and F1-score
- [ ] Sensitivity and Specificity
- [ ] ROC-AUC analysis
- [ ] Transfer learning
- [ ] Grad-CAM visualization
- [ ] Error analysis of misclassified images

---

## ⚠️ Medical Disclaimer

> [!WARNING]
> **This project is for educational and research-learning purposes only.**
>
> The model has **not been clinically validated** and should **not be used for diagnosis or patient-care decisions**. Performance on this dataset does not establish performance on real-world clinical samples.

---

## 👨‍💻 Author

**Alia Al Qadri**

Medical student exploring the intersection of **Medicine**, **Artificial Intelligence**, **Machine Learning**, and **Data Science**.

---

## 🌱 About This Project

This project documents an early stage of my journey into **deep learning**.

Rather than focusing only on maximizing accuracy, my goal was to understand the fundamentals behind:

**CNNs → Image Preprocessing → Keras Functional API → Training → Validation → Evaluation**

More advanced models, optimization techniques, and **Medical AI** applications will be explored in future projects.

---

### ⭐ If you found this project interesting, feel free to explore the notebook and follow my progress as I continue learning **Deep Learning and Medical AI**.
