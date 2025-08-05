# 🌸 Iris Classification using Random Forest

This project uses the classic **Iris flower dataset** and applies a **Random Forest Classifier** with varying numbers of trees (`n_estimators`) to find the best model configuration for classification accuracy.

## 📁 Dataset

The built-in `load_iris()` dataset from `sklearn.datasets` is used. It contains 150 samples from three species of Iris:
- Setosa
- Versicolor
- Virginica

Each sample includes 4 features:
- Sepal length (cm)
- Sepal width (cm)
- Petal length (cm)
- Petal width (cm)

## 📊 Objective

To compare the model accuracy for different values of `n_estimators` in a Random Forest Classifier and determine the optimal number of trees.

## 🧰 Libraries Used

- `pandas`
- `sklearn.datasets`
- `sklearn.model_selection`
- `sklearn.ensemble`

## 🧪 Methodology

1. Load and explore the Iris dataset.
2. Split the data into training and testing sets (50% each).
3. Train `RandomForestClassifier` with different `n_estimators`:
   - 10, 20, 50, 100, 150
4. Evaluate and record the accuracy for each model.
5. Identify and display the best performing configuration.
