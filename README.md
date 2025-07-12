# 🛍️ Customer Segmentation using KMeans Clustering

## 📌 Project Overview

This project applies **KMeans Clustering** to segment mall customers based on their **Annual Income** and **Spending Score**.  
The goal is to identify customer groups to help businesses with targeted marketing strategies.

---

## 📁 Dataset Information

- **📄 File Name**: `Mall_Customers.csv`  
- **🔢 Key Features Used for Clustering**:
  - `Annual Income (k$)`  
  - `Spending Score (1-100)`  
- Dataset contains customer demographic and behavioral information

---

## 🧹 Data Preprocessing

1. ✅ Loaded dataset using `pandas.read_csv()`  
2. 🧼 Selected relevant columns:
   ```python
   x = data[['Annual Income (k$)', 'Spending Score (1-100)']]
   ```

---

## 🧠 KMeans Clustering

- 📊 Used the **Elbow Method** to determine the optimal number of clusters:
  ```python
  for i in range(1, 11):
      kmeans = KMeans(n_clusters=i, init='k-means++')
      kmeans.fit(x)
      wcss.append(kmeans.inertia_)
  ```
- 📉 Plotted Within-Cluster Sum of Squares (WCSS) to find the "elbow point"

- 🚀 Final model created with `n_clusters=5`, and clustering performed using:
  ```python
  kmeans = KMeans(n_clusters=5, init='k-means++', random_state=0)
  labels = kmeans.fit_predict(x)
  ```

---

## 🎯 Cluster Visualization

- 🟡 Cluster 1  
- 🔵 Cluster 2  
- 🟢 Cluster 3  
- 🔵 Cluster 4  
- 🟣 Cluster 5  
- ❌ Red 'X' markers show **cluster centroids**

- 🖼️ Scatter plot created with `matplotlib` for visual cluster separation

---

## 📌 Key Observations

- The Elbow Method suggests **5 clusters** as optimal  
- Clear segmentation seen among customers based on income and spending habits  
- Useful for customer profiling and targeted marketing  

---

## 🧰 Libraries Used

- `pandas` 🐼  
- `numpy` 🔢  
- `matplotlib.pyplot` 📊  
- `sklearn.cluster.KMeans` 🧠  

---

## 🚀 Future Improvements

- Add more features like Age or Gender to improve clustering  
- Apply **PCA** or **TSNE** for dimensionality reduction and better visualization  
- Compare clustering with other algorithms like **DBSCAN** or **Hierarchical Clustering**  
- Build a dashboard using **Streamlit** to allow interactive exploration  

---

## 🙏 Acknowledgments

- Dataset sourced from a classic mall customer segmentation example  
- Inspired by business strategies for customer relationship management (CRM)

---

## 📜 License

This project is licensed under the **MIT License** ✅
