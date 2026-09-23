🦠 Malaria Detection Using Convolutional Neural Networks

A deep learning project for classifying microscopic blood cell images as Parasitized or Uninfected using a Convolutional Neural Network (CNN) built with the Keras Functional API.

This project is part of my journey into deep learning and medical artificial intelligence, with the goal of applying machine learning techniques to clinically relevant problems.

📌 Project Overview

Malaria is a parasitic disease caused by Plasmodium species and is commonly diagnosed by examining stained blood films under a microscope.

In this project, I built and trained a CNN to automatically classify cell images into two categories:

- Parasitized — cells containing malaria parasites
- Uninfected — cells without visible malaria parasites

The purpose of the project was to practice the complete workflow of building an image-classification model, including dataset preparation, preprocessing, CNN architecture design, training, validation, and evaluation.

«Note: This project is educational and experimental. The model is not intended for clinical diagnosis or medical decision-making.»

---

📊 Dataset

The project uses the Cell Images for Detecting Malaria dataset available on Kaggle.

Dataset:
"iarunava/cell-images-for-detecting-malaria"

The dataset contains 27,558 cell images divided equally between:

- 13,780 Uninfected cells
- 13,778 Parasitized cells

The dataset is downloaded directly using the Kaggle API within the notebook.

---

🧠 Model Architecture

The neural network was built from scratch using the Keras Functional API.

Input images are resized to:

64 × 64 × 3

The architecture consists of two convolutional blocks followed by fully connected layers:

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

The complete network contains approximately 4.47 million parameters.

---

⚙️ Training Configuration

The model was compiled using:

Parameter| Value
Optimizer| Adam
Loss Function| Binary Cross-Entropy
Metric| Accuracy
Batch Size| 64
Epochs| 3
Validation Split| 10% of training data
Test Split| 20% of total dataset
Random State| 42

The labels were converted to categorical representations before training.

The resulting dataset split was:

Training samples: 22,046
Testing samples:   5,512

---

📈 Results

After three epochs, the model achieved:

Test Accuracy

95.45%

Training performance across the three epochs:

Epoch| Training Accuracy| Validation Accuracy
1| 99.67%| 95.69%
2| 99.77%| 95.92%
3| 99.85%| 95.46%

The notebook also visualizes the training and validation accuracy and loss curves to examine model behavior during training.

The difference between training and validation performance suggests that the model begins to overfit the training data. Since the main objective of this project was to understand and implement the deep-learning workflow, further optimization was intentionally left for future projects.

---

🛠️ Technologies Used

- Python
- TensorFlow / Keras
- Keras Functional API
- NumPy
- OpenCV
- Pillow
- Matplotlib
- Scikit-learn
- Kaggle API
- Jupyter Notebook / Google Colab

---

🔄 Project Workflow

Kaggle Dataset
      ↓
Load Cell Images
      ↓
Resize Images to 64×64
      ↓
Convert Images to NumPy Arrays
      ↓
Encode Labels
      ↓
Train/Test Split
      ↓
Build CNN with Keras Functional API
      ↓
Train Model
      ↓
Evaluate on Test Dataset
      ↓
Visualize Training Performance

---

🚀 Future Improvements

This project represents an early step in my deep-learning journey rather than a fully optimized medical imaging system.

Possible extensions include:

- Image normalization
- Data augmentation
- Additional convolutional layers
- Hyperparameter tuning
- Early stopping
- Learning-rate scheduling
- Confusion matrix analysis
- Precision, recall, F1-score, sensitivity, and specificity
- ROC curve and AUC evaluation
- Transfer learning with pretrained CNN architectures
- Grad-CAM visualization for model interpretability
- Analysis of incorrectly classified images

These improvements will be explored as I continue building more advanced deep-learning and medical-AI projects.

---

⚠️ Medical Disclaimer

This model was created for educational and research-learning purposes only.

It has not undergone clinical validation and should not be used to diagnose malaria or guide patient care. Performance on this dataset does not establish performance on real-world clinical samples.

---

👨‍💻 Author

Alia Al Qadri

Medical student exploring the intersection of medicine, artificial intelligence, machine learning, and data science.

---

⭐ About This Project

This is one of my early deep-learning projects and documents my progress in learning how neural networks can be applied to medical imaging.

Rather than focusing only on maximizing model performance, the project focuses on understanding the fundamentals of:

CNNs → image preprocessing → Keras Functional API → training → validation → evaluation

More advanced models and optimization techniques will be explored in future projects.
