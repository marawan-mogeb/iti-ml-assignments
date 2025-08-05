# Heart Disease Classification with PCA

This project demonstrates the process of building and evaluating multiple classification models on a heart disease dataset. It also explores the impact of dimensionality reduction using Principal Component Analysis (PCA) on model performance.

## Dataset

The dataset used in this project is `heart.csv`, which contains information about patients such as:

- Age
- Sex
- Chest Pain Type
- Resting Blood Pressure
- Cholesterol
- Fasting Blood Sugar
- Resting ECG Results
- Max Heart Rate Achieved
- Exercise-Induced Angina
- Oldpeak
- ST Slope
- Target variable: `HeartDisease` (1 = disease, 0 = no disease)

## Objectives

- Preprocess the data (standardization, encoding).
- Train classification models:
  - Logistic Regression
  - Support Vector Machine (SVM)
  - Random Forest
- Evaluate accuracy of models before and after applying PCA.
- Compare performance to understand the effect of dimensionality reduction.

## Libraries Used

- pandas
- scikit-learn

## Preprocessing Steps

1. Separate features (`X`) and target (`y`).
2. Identify categorical and numerical columns.
3. Standardize numerical features.
4. One-hot encode categorical features (dropping the first category to avoid multicollinearity).
5. Split the dataset into training and testing sets (80% / 20%).

## Classification Models Used

- **Logistic Regression**
- **Support Vector Machine (SVM)**
- **Random Forest Classifier**

Each model is trained on the preprocessed dataset, and accuracy is evaluated on the test set.

## Results (Before PCA)

The classification models were evaluated based on accuracy:

```

Logistic Regression: 0.8689
SVM: 0.8689
Random Forest: 0.8852

```

## Applying PCA

PCA (Principal Component Analysis) is applied to reduce the dimensionality of the feature space while retaining 95% of the variance. Models are retrained on the PCA-transformed data.

## Results (After PCA)

```

Logistic Regression: 0.8525
SVM: 0.8525
Random Forest: 0.8525

```

## Observations

- Before PCA, the Random Forest model gave the highest accuracy (≈ 88.5%).
- After PCA, all models' performance slightly dropped, indicating that PCA may remove features important for classification.
- However, PCA reduced dimensionality and can be useful in scenarios where model speed or overfitting is a concern.
