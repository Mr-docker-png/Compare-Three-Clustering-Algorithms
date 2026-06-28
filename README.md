# 🌙 Clustering Algorithms Comparison

A machine learning practice project comparing three popular clustering algorithms on the **Two Moons** dataset.

This project demonstrates how different clustering algorithms behave on a non-linear dataset and highlights their strengths, weaknesses, and ideal use cases through visualizations and experiments.

---

# 📌 Project Objectives

- Understand the fundamentals of clustering.
- Compare K-Means, Agglomerative Clustering, and DBSCAN.
- Explore hierarchical clustering using dendrograms.
- Study the effect of different linkage methods.
- Investigate how the `eps` parameter affects DBSCAN.
- Identify which algorithm works best for non-linear datasets.

---

# 📂 Dataset

**Dataset:** Two Moons (Scikit-Learn)

The Two Moons dataset is a synthetic dataset consisting of two interleaving crescent-shaped clusters.

Unlike simple blob datasets, the clusters are **non-linear**, making this dataset an excellent benchmark for evaluating clustering algorithms.

Dataset generation:

```python
from sklearn.datasets import make_moons

X, y = make_moons(
    n_samples=300,
    noise=0.08,
    random_state=42
)
```

Dataset Information

- Samples: **300**
- Features: **2**
- Cluster Shape: **Non-linear**

---

# 🖼 Original Dataset

The original Two Moons dataset.

<p align="center">
<img src="images/original_dataset.png" width="650">
</p>

---

# 📊 K-Means Clustering

K-Means partitions the dataset into **K clusters** by assigning each point to its nearest centroid.

### Characteristics

- Fast and efficient
- Requires the number of clusters beforehand
- Works best on compact and spherical clusters
- Struggles with curved cluster structures

<p align="center">
<img src="images/kmeans_result.png" width="650">
</p>

---

# 🌳 Agglomerative Clustering

Agglomerative Clustering is a hierarchical clustering algorithm that starts with every data point as an individual cluster and repeatedly merges the closest clusters.

### Characteristics

- Hierarchical clustering
- Produces a dendrogram
- Does not rely on centroids
- Performance depends on the linkage method

<p align="center">
<img src="images/agglomerative_result.png" width="650">
</p>

---

# 🔗 Linkage Methods Comparison

Agglomerative Clustering supports multiple linkage methods.

- Single Linkage
- Complete Linkage
- Average Linkage
- Ward Linkage

Each linkage method measures the distance between clusters differently, leading to different clustering results.

<p align="center">
<img src="images/linkage_comparison.png" width="750">
</p>

---

# 🌲 Dendrogram

The dendrogram visualizes the complete hierarchical clustering process.

It shows:

- How clusters merge
- The order of merging
- The distance between merged clusters

<p align="center">
<img src="images/dendrogram.png" width="800">
</p>

---

# 🔍 DBSCAN

DBSCAN (Density-Based Spatial Clustering of Applications with Noise) groups data points based on density rather than distance to centroids.

Unlike K-Means, DBSCAN automatically discovers the number of clusters and can detect noise (outliers).

### Characteristics

- Density-based clustering
- Automatically determines clusters
- Detects noise
- Excellent for arbitrary-shaped datasets

<p align="center">
<img src="images/dbscan_result.png" width="650">
</p>

---

# ⚙️ Effect of eps

The `eps` parameter controls the search radius used by DBSCAN.

Small values:

- More noise points
- Harder to form clusters

Large values:

- Larger neighborhoods
- May merge multiple clusters into one

<p align="center">
<img src="images/eps_comparison.png" width="750">
</p>

---

# 📊 Final Comparison

Comparison of all clustering algorithms on the same dataset.

<p align="center">
<img src="images/comparison.png" width="800">
</p>

---

# 📖 Key Observations

## K-Means

- Fast and simple.
- Performs well on compact datasets.
- Cannot capture curved clusters because it relies on centroid distances.

---

## Agglomerative Clustering

- Builds clusters hierarchically.
- Produces interpretable dendrograms.
- More flexible than K-Means.
- Performance changes with different linkage methods.

---

## DBSCAN

- Best performer on the Two Moons dataset.
- Correctly follows the curved cluster shapes.
- Automatically detects noise.
- Does not require specifying the number of clusters.

---

# 📊 Algorithm Comparison

| Algorithm | Requires Number of Clusters | Detects Noise | Best For |
|------------|----------------------------|---------------|----------|
| K-Means | ✅ Yes | ❌ No | Compact and spherical clusters |
| Agglomerative | ✅ Yes | ❌ No | Hierarchical clustering |
| DBSCAN | ❌ No | ✅ Yes | Arbitrary-shaped clusters and noisy datasets |

---

# 🛠 Technologies Used

- Python
- NumPy
- Matplotlib
- Scikit-Learn
- SciPy

---

# 📚 What I Learned

Through this project I learned:

- How K-Means partitions data using centroids.
- Why K-Means struggles with non-linear datasets.
- How Agglomerative Clustering builds hierarchical clusters.
- The difference between Single, Complete, Average, and Ward linkage.
- How dendrograms represent the clustering process.
- How DBSCAN discovers clusters using density.
- How the `eps` parameter changes DBSCAN's behavior.
- Why choosing the right clustering algorithm depends on the structure of the dataset.

---

# 🚀 Future Improvements

- Compare clustering performance on additional datasets such as:
  - Make Blobs
  - Make Circles
  - Iris Dataset
- Evaluate clustering quality using Silhouette Score.
- Compare computational performance on larger datasets.
- Explore additional clustering algorithms such as Spectral Clustering and OPTICS.

---

# 📜 License

This project is created for educational purposes using the datasets provided by Scikit-Learn.
