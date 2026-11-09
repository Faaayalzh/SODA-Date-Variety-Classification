# 🌴 SODA Challenge: Saudi Date Variety Classification

An end-to-end Machine Learning pipeline developed for classifying 13 distinct Saudi date varieties using computer vision and machine learning algorithms. Built as part of the Machine Learning course at Umm Al-Qura University.

> Group project for the Machine Learning course, Data Science Department, Umm Al-Qura University (2026).

---

## 📌 Project at a Glance

| Element | Value / Count |
|---------|---------------|
| **Dataset** | SODA Challenge Dataset (Kaggle) |
| **Total Images** | 2,613 images (1,829 train, 784 test) |
| **Classes** | 13 balanced date varieties[cite: 2] |
| **Model** | K-Nearest Neighbors ($k=3$)[cite: 2] |
| **Baseline Accuracy** | **31.97%** (~4x higher than random guessing at 7.7%)[cite: 2] |
| **Evaluation Metrics** | Accuracy, Precision, Recall, F1-Score, Confusion Matrix[cite: 2] |

---

## 🛠️ What Was Built

| Task | Details |
|------|---------|
| **Exploratory Data Analysis (EDA)** | Inspected class balance (~140 images per class), image resolutions, and verified zero missing/corrupted image paths[cite: 2]. |
| **Data Preprocessing & Normalization** | Loaded images via OpenCV, converted BGR to RGB, resized to $64 \times 64 \times 3$, and normalized pixel values to $[0, 1]$[cite: 2]. |
| **Feature Extraction (Baseline)** | Flattened 3D image arrays into 1D feature vectors of size **12,288** features per image[cite: 2]. |
| **Data Splitting** | Applied 80/20 Stratified Train/Validation split (1,463 training samples, 366 validation samples)[cite: 2]. |
| **Model Training** | Trained a K-Nearest Neighbors classifier ($k=3$, Euclidean Distance) to establish a baseline model[cite: 2]. |
| **Performance Evaluation** | Generated a detailed classification report and confusion matrix to identify misclassified classes[cite: 2]. |
| **Kaggle Submission** | Generated `submission.csv` mapping test predictions to date class labels[cite: 2]. |

---

## ⚠️ Challenges & Technical Discussion

### 1. Low Baseline Accuracy (~31.97%)
While 31.97% is low for production, it is expected and mathematically justified for a baseline model:
- **Raw Pixel Limitations:** KNN calculates simple Euclidean distances between flattened pixel vectors. It cannot capture spatial hierarchies, textures, or shapes[cite: 2].
- **Fine-Grained Classification:** Saudi date varieties share highly similar physical features (color and shape overlaps), which simple distance metrics struggle to separate[cite: 2].

### 2. Proposed Future Improvements
To reach production-level accuracy (>85%), future iterations should implement:
- **Feature Engineering:** Apply PCA (Principal Component Analysis) or HOG (Histogram of Oriented Gradients).
- **Deep Learning (CNNs):** Train a Convolutional Neural Network to extract spatial features automatically.
- **Transfer Learning:** Fine-tune pre-trained vision models such as **ResNet-50** or **MobileNetV2**.

---

## 📁 Files

- `notebooks/SODA_Date_Classification.ipynb`: Jupyter notebook containing the complete machine learning pipeline[cite: 2].
- `src/main.py`: Modular Python script for automated preprocessing, training, and evaluation[cite: 2].
- `submission.csv`: Kaggle competition prediction results[cite: 2].
- `requirements.txt`: Python package dependencies[cite: 2].

---

## 🚀 How to Run

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/YOUR_USERNAME/SODA-Date-Variety-Classification.git](https://github.com/YOUR_USERNAME/SODA-Date-Variety-Classification.git)
   cd SODA-Date-Variety-Classification
