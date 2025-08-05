
### ✅ Steps

1. **Data Generation**  
   Created 40 random points in [-1, 1], using a 2nd-degree polynomial with Gaussian noise.
   
2. **Polynomial Feature Expansion**  
   Expanded data to up to **200-degree polynomial** using `sklearn.preprocessing.PolynomialFeatures`.

3. **Train/Test Split**  
   80% training, 20% testing using `train_test_split`.

4. **Model Training & Evaluation**
   - **No Regularization**: `LinearRegression`
   - **L1 Regularization**: `Lasso`
   - **L2 Regularization**: `Ridge`

Each model reports:
- RMSE on train and test data
- Plot showing fit curve vs actual data
- Coefficients learned

---

### 🧾 Key Observations

- **No Regularization**: Severely overfits, wild coefficients.
- **Lasso (L1)**: Performs feature selection by zeroing out many coefficients.
- **Ridge (L2)**: Shrinks coefficients, but doesn’t eliminate them.
- Regularization significantly improves generalization performance.

---

## 📉 Part 2: Real-World Dataset - Auto MPG

### 🔍 Dataset

- **Source**: [UCI Auto MPG Dataset](http://archive.ics.uci.edu/ml/machine-learning-databases/auto-mpg/auto-mpg.data)
- **Target**: `MPG` (miles per gallon)
- **Features used**: `Horsepower` (with 50-degree polynomial expansion)

### 🧼 Data Preprocessing

- Removed missing values (`Horsepower`)
- Converted `Origin` column to dummy variables
- Standardized polynomial features using `StandardScaler`

---

### 🧠 Modeling

- Polynomial degree: **50**
- Compared:
  - `LinearRegression` (No regularization)
  - `Lasso` with `alpha=0.5`
  - `Ridge` with `alpha=0.5`
- Evaluated using RMSE on the test set

---

### 📊 Results

| Model        | RMSE on Test Set        |
|--------------|-------------------------|
| No Reg       | High (overfitting observed) |
| Lasso (L1)   | Lower RMSE, sparse model     |
| Ridge (L2)   | Balanced performance         |

- Regularization **greatly reduces overfitting**, especially with high-degree polynomials.
- **Lasso** performs feature selection, which is helpful when dealing with irrelevant or noisy features.

---

## 🛠️ Technologies Used

- Python
- NumPy, Pandas
- Scikit-learn (PolynomialFeatures, Lasso, Ridge, LinearRegression)
- Matplotlib for plotting

---

## 📌 Lessons Learned

- High-degree polynomial regression can easily overfit without regularization.
- L1 and L2 help control model complexity and improve generalization.
- Real-world problems often benefit from regularization, especially when the feature set is over-engineered.

---
