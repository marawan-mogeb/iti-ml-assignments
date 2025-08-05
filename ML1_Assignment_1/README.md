
# 📘 Machine Learning Assignment – Day 3

This directory contains two key notebooks focused on binary classification evaluation and heart attack prediction using machine learning.

---

## 🔬 Notebook 1: `assignment_ml1_day3.ipynb`

### 🎯 Objective
Implement **binary classification evaluation metrics from scratch** using only **NumPy** and **Matplotlib**. No external ML libraries like scikit-learn were used.

### 🛠 Implemented Metrics:
- **Accuracy**
- **Confusion Matrix**
- **Precision**
- **Recall**
- **F1 Score**
- **ROC-AUC (Area Under Curve)**

### 📈 Visualization:
- Confusion Matrix Plot
- Precision vs Recall Curve
- ROC Curve

### 📦 Dataset
Simulated binary classification data with:
- `y_true`: True labels (0 or 1)
- `y_scores`: Predicted probabilities
- `y_pred`: Predicted labels using threshold 0.5

### ✅ Results:
All metrics and curves are correctly calculated and visualized, demonstrating a solid understanding of classification performance evaluation.

---

## ❤️ Notebook 2: `heart attack.ipynb`

### 🎯 Objective
Build and evaluate ML classification models to predict **heart attack outcomes** using real patient medical data.

### 📊 Dataset:
Medical dataset with features such as:
- Age, Gender
- Blood Pressure (Systolic/Diastolic)
- Heart Rate, Blood Sugar
- CK-MB, Troponin
- Output label: `Result` (0 = No Heart Attack, 1 = Heart Attack)

### 🔍 Exploratory Data Analysis (EDA)
- Distribution plots for continuous features
- Gender and result class imbalance analysis
- Outlier detection and removal using IQR
- Feature correlation heatmap

### 🧼 Preprocessing
- Label Encoding (`Result`, `Gender`)
- Feature Scaling (`StandardScaler`)
- Train/Test split using `train_test_split`

### 🤖 Classification Models Evaluated:
- Logistic Regression
- Random Forest
- Decision Tree
- K-Nearest Neighbors
- Support Vector Machine (SVM)

### 📈 Evaluation Metrics:
- Confusion Matrix
- ROC AUC Score
- Classification Report (Precision, Recall, F1)

### ✅ Results Summary:
All models were evaluated, and metrics were printed for comparison. ROC-AUC scores provide insights into each model’s discriminative ability.

---

## 🧰 Tools & Libraries Used:
- `NumPy`, `Matplotlib` (for manual implementation)
- `Pandas`, `Seaborn` (for data handling and visualization)
- `scikit-learn` (only in `heart attack.ipynb`)

---

