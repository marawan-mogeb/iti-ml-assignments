You're right — the response above **shows the Markdown content** with triple backticks (` ```markdown `), which is useful when **viewing it as code**, but if you want to **see the actual rendered Markdown content**, it should not be inside code blocks.

Below is the **entire `README.md` file in rendered Markdown**, exactly as it should appear:

---

# 📊 Clustering Analysis with Hierarchical Clustering and DBSCAN

This repository contains two unsupervised learning tasks using clustering techniques:

* **Task 1:** Hierarchical Clustering on the Countries of the World dataset.
* **Task 2:** DBSCAN Clustering on a synthetic concentric circles dataset.

---

## 📁 Task 1: Hierarchical Clustering - Countries of the World

### 📌 Dataset

You can download the dataset from Kaggle:
🔗 [Countries of the World Dataset](https://www.kaggle.com/fernandol/countries-of-the-world)

After downloading, load it into the notebook using `pandas`.

```python
import pandas as pd

df = pd.read_csv("countries of the world.csv")
print('Dataset shape:', df.shape)
```

---

### 🔍 Step 1: Data Investigation

We explored the data to find the following issues:

* Missing values in numerical and categorical columns
* Commas instead of decimal points in numeric fields
* Extra whitespace in text fields
* Incorrect data types
* Potential outliers and skewness in distributions

---

### 🧹 Step 2: Data Preprocessing

* **Handled missing values** using median for numerical columns and mode for categorical columns.
* **Converted comma decimals** to standard `float` format.
* **Stripped whitespace** from text fields like `Country` and `Region`.

```python
# Example: Fix comma-decimal issue
df['Literacy (%)'] = df['Literacy (%)'].str.replace(',', '.').astype(float)
```

---

### 🔄 Step 3: Feature Transformation

We scaled selected features using **StandardScaler** to normalize them before clustering.

```python
from sklearn.preprocessing import StandardScaler

features = ['Population', 'Area (sq. mi.)', 'Pop. Density (per sq. mi.)', 
            'GDP ($ per capita)', 'Literacy (%)']

scaler = StandardScaler()
X_scaled = scaler.fit_transform(df[features])
```

---

### 🔗 Step 4: Hierarchical Clustering

We explored different linkage methods and distance metrics using **dendrograms** and **silhouette scores**.

* Optimal number of clusters selected using silhouette scores.
* Final model used **Ward linkage** with **Euclidean distance** and **6 clusters**.

```python
from sklearn.cluster import AgglomerativeClustering
from sklearn.metrics import silhouette_score

clusterer = AgglomerativeClustering(n_clusters=6, linkage='ward', metric='euclidean')
df['Cluster'] = clusterer.fit_predict(X_scaled)
```

---

### 📊 Cluster Visualization

We visualized clusters by plotting `GDP per capita` vs `Literacy (%)`.

```python
plt.scatter(df['GDP ($ per capita)'], df['Literacy (%)'], c=df['Cluster'], cmap='viridis')
```

---

### 📈 Cluster Summary

We examined the average feature values in each cluster.

```python
df.groupby('Cluster')[features].mean()
```

---

## 🌐 Task 2: DBSCAN Clustering on Synthetic Data

### 📍 Objective

Apply **DBSCAN** (Density-Based Spatial Clustering of Applications with Noise) to a non-linearly separable dataset of concentric circles.

---

### 🧪 Dataset

Generated using `make_circles()` from `sklearn.datasets`:

```python
from sklearn.datasets import make_circles

X, _ = make_circles(n_samples=500, factor=0.5, noise=0.03, random_state=4)
```

---

### ⚙️ Clustering with DBSCAN

Used `eps=0.2` and `min_samples=3` with **Euclidean** distance metric:

```python
from sklearn.cluster import DBSCAN

dbscan = DBSCAN(eps=0.2, min_samples=3, metric='euclidean')
labels = dbscan.fit_predict(X)
```

---

### 🖼️ Visualization

Plotted the clustered circles using `matplotlib`:

```python
plt.scatter(X[:, 0], X[:, 1], c=labels, cmap='viridis')
```

---

## 📌 Summary

| Task         | Method                                     | Highlights                                      |
| ------------ | ------------------------------------------ | ----------------------------------------------- |
| Hierarchical | Agglomerative Clustering with Dendrograms  | Real-world data, data cleaning, feature scaling |
| DBSCAN       | Density-Based Clustering on synthetic data | Handles non-linear structures and noise         |

---

## 🛠️ Dependencies

* `pandas`
* `numpy`
* `matplotlib`
* `scikit-learn`
* `scipy`
