# 🛍️ Customer Segmentation Using K-Means Clustering

This project demonstrates customer segmentation based on spending behavior and demographics using **K-Means clustering** on the Mall Customer dataset. Two separate notebooks were used: one for applied segmentation and one for custom implementation of the K-Means algorithm from scratch.

---

## 📁 Dataset

**Mall_Customers.csv**  
- Includes demographic information:
  - `CustomerID`, `Gender`, `Age`, `Annual Income (k$)`, and `Spending Score (1-100)`

---

## 📘 Part 1: customer_segmentation.ipynb

### 📊 EDA Highlights

- **Spending Score Distribution**:
  - Customers with a **spending score > 50** are generally **younger**.
- **Gender Distribution**:
  - Slightly more **female** customers overall.
  - Similar split among high-spending customers.
- **Feature Histograms**:
  - Age, income, and spending scores are relatively normally distributed.

### 📌 Feature Selection
Used only the numerical columns for clustering:
- `Annual Income (k$)`
- `Spending Score (1-100)`

---

### 🔍 Elbow Method

- The **SSE (inertia)** was plotted for `k=1` to `k=10`.
- Optimal value of **k = 5** identified at the "elbow" point.

---

### 🧠 K-Means Clustering (Sklearn)

- Applied `KMeans` with `n_clusters=5`.
- Visualized 5 distinct customer clusters.
- Cluster centroids plotted in yellow (marker `X`).

**Interpretation:**
- Clusters grouped customers by low/high income and low/high spending.
- Useful for marketing segmentation: loyal customers, high-spenders, low-spenders, etc.

---

## 🧪 Part 2: kmeans.ipynb (K-Means From Scratch)

This notebook implements K-Means manually using NumPy.

### ✅ Custom Functions:
- `initialize_centroids()`: Random initialization
- `assign_clusters()`: Euclidean distance
- `compute_centroids()`: Cluster-wise mean
- `compute_inertia()`: Sum of squared distances

### 🧪 Testing on Synthetic Data:
- Used `make_blobs()` to validate algorithm logic.
- Achieved good clustering and visual centroids.

### 🔄 Application to Real Data:
- Applied to `['Age', 'Annual Income (k$)']`
- Ran K-Means with `k=3`
- Produced clean, separable clusters similar to Sklearn's implementation.

---

## 📈 Sample Output: Cluster Visualization

### Income vs Spending Score (k=5)
![Customer Segments](![alt text](image.png))

### Age vs Income (k=3, custom K-Means)
![Age-Income Segmentation](![alt text](image-1.png))

---
