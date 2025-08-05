# 🍄 Mushroom Classification - Machine Learning Project

This project explores a classification problem using the **Mushroom Classification Dataset** from Kaggle. The goal is to determine whether a mushroom is **edible (e)** or **poisonous (p)** based on its physical characteristics using machine learning.

---

## 📊 Exploratory Data Analysis (EDA)

### ✅ Class Distribution:
- **Edible:** 51.8%
- **Poisonous:** 48.2%
- The data is fairly balanced, which helps with model training and evaluation.

### ✅ Feature Distributions:
- **Cap Shape:** Most mushrooms have a **convex** cap, followed by **flat**.
- **Cap Color:** Dominated by **brown**, followed by **gray** and **red**.
- **Odor:** ~40% of mushrooms have **no smell**, but odor is a strong indicator of edibility.
- **Gill Size:** Broad gills are slightly more common than narrow ones.
- **Habitat:** **Woods** are the most common habitat, followed by **grassy areas** and **leaves**.

---

## 🧼 Data Preprocessing

- **Missing Values:** None found.
- **Encoding:** Used `LabelEncoder` to transform all categorical features into numeric values.
- **Correlation Heatmap:** Revealed strong correlations between certain features and the target `class`.

---

## 🤖 Model Training

Two models were trained to classify mushrooms:

1. **Decision Tree Classifier**
2. **Random Forest Classifier**

### 🔍 Model Evaluation Metrics:

#### ✅ Decision Tree
- **Accuracy:** High (~1.0)
- **Confusion Matrix:** Excellent classification with minimal to no errors.
- **Classification Report:** Precision, Recall, and F1-scores all near-perfect.

#### ✅ Random Forest
- **Accuracy:** Also near-perfect (~1.0)
- **Confusion Matrix & Report:** Similar to Decision Tree but slightly more stable due to ensemble learning.

---

## 🔧 Hyperparameter Tuning

### ✅ Grid Search Results:

- **Decision Tree Best Parameters:**
  - `max_depth`: 10
  - `min_samples_split`: 2

- **Random Forest Best Parameters:**
  - `n_estimators`: 100
  - `max_depth`: 15
  - `min_samples_split`: 2

---

## 🧠 Feature Importance (Random Forest)

Top 10 most important features contributing to classification:

1. **odor**
2. **spore-print-color**
3. **gill-color**
4. **gill-size**
5. **ring-type**
6. **gill-spacing**
7. **habitat**
8. **stalk-root**
9. **stalk-color-below-ring**
10. **cap-color**

These features played the most significant roles in distinguishing edible from poisonous mushrooms.

