# Titanic Survivor Prediction using Decision Tree Classifier

This project uses the Titanic dataset to predict whether a passenger survived or not using Decision Tree classifiers. It includes experiments with:
- Label Encoding
- One-Hot Encoding
- Handling missing values (by imputation or dropping)

## 📁 Dataset

The dataset used is the Titanic dataset from Kaggle, specifically: /kaggle/input/titanic/train.csv

## 🧰 Libraries Used

- `pandas`
- `numpy`
- `matplotlib`
- `sklearn`

## 📊 Features Used

- `Pclass`
- `Sex` (encoded)
- `Age`
- `Fare`
- (For one-hot encoding) `SibSp`, `Parch`, `Sex_female`, `Sex_male`

## 🔍 Experiments

### 1. With Mean Imputation for Missing Age

- Fill missing `Age` values with the mean.
- Drop the `Cabin` column due to excessive missing values.
- Apply **Label Encoding** on `Sex`.

**Model:** Decision Tree Classifier (default and with `max_depth=5`)

**Metrics Printed:**
- Accuracy
- Classification Report
- Visualized Decision Tree

---

### 2. Without Filling Missing Values (Dropped)

- Drop rows with missing `Age`.
- Use **Label Encoding** on `Sex`.

**Model:** Decision Tree Classifier (`max_depth=5`)

---

### 3. With One-Hot Encoding

- Drop rows with missing `Age`.
- Use **One-Hot Encoding** on `Sex` column.
- Features expanded to include `Sex_female`, `Sex_male`, `SibSp`, and `Parch`.

**Model:** Decision Tree Classifier (`max_depth=5`)

---

## 📈 Sample Output

Each model prints:
- **Accuracy**
- **Classification Report** (Precision, Recall, F1-Score)
- **Decision Tree Visualization**