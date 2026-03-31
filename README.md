# Customer-Segmentation-using-K-Means

# Customer Segmentation using K-Means

## Overview

This project focuses on solving the customer segmentation problem using an unsupervised machine learning approach. The goal is to identify natural groupings in customer data based on behavioral and demographic features, without relying on labeled outputs.

The solution uses the K-Means clustering algorithm to group customers into meaningful segments that can later be used for business decision-making such as targeted marketing, personalization, and customer retention strategies.

---

## Problem Approach

The problem was approached as a standard unsupervised learning pipeline:

1. Understand the dataset and features
2. Clean and preprocess the data
3. Select meaningful features
4. Normalize the data for fair distance computation
5. Determine the optimal number of clusters
6. Train the clustering model
7. Analyze and interpret the clusters

The focus was on building a simple but complete pipeline that goes from raw data to interpretable insights.

---

## Dataset

The dataset contains customer information with the following features:

- Age
- Annual Income
- Spending Score

The `CustomerID` field was removed since it does not contribute to clustering.

---

## Data Preprocessing

Before applying K-Means, the following steps were performed:

- Removed irrelevant columns
- Selected only numerical features
- Checked for missing values (none found)
- Converted data into a numerical matrix

---

## Feature Scaling

K-Means relies on distance (Euclidean distance), so feature scaling is essential.

StandardScaler was used to normalize the data:

- Mean = 0
- Standard Deviation = 1

This ensures that features like income and age contribute equally to clustering.

---

## Choosing the Number of Clusters (k)

Selecting the right number of clusters is a key step.

### 1. Elbow Method
- Plotted inertia (WCSS) against number of clusters
- Looked for the "elbow point" where improvement slows down

### 2. Silhouette Score
- Evaluated how well clusters are separated
- Higher score indicates better-defined clusters

Based on both methods, the optimal value was:

**k = 5**

---

## K-Means Implementation

K-Means works by iteratively grouping data points into clusters.

### Steps followed:

1. Initialize k centroids (using k-means++)
2. Assign each data point to the nearest centroid
3. Recalculate centroids as the mean of assigned points
4. Repeat until convergence

### Parameters used:

- n_clusters = 5
- init = "k-means++"
- random_state = 42

---

## Results

The algorithm successfully grouped customers into 5 distinct segments.

These clusters showed clear separation when visualized using:

- Income vs Spending Score plots
- Cluster centroids
- Decision boundaries

---

## Key Observations

- Some customers have high income and high spending → high-value group
- Some have high income but low spending → potential targets
- Some have low income but high spending → impulsive behavior
- Some fall in low income + low spending → low-value group
- Others lie in the middle → average customers

This shows that K-Means can uncover meaningful behavioral patterns without labels.

---

## Why K-Means?

K-Means was chosen because:

- Simple and efficient
- Works well on numerical data
- Scales easily
- Produces interpretable clusters

---

## Limitations

- Assumes clusters are spherical
- Sensitive to initial centroid placement
- Requires predefined k
- Not ideal for non-linear or complex cluster shapes

---

## Future Improvements

- Try DBSCAN or GMM for better flexibility
- Add more features (gender, transaction history)
- Use PCA for dimensionality reduction
- Build a real-time prediction system
- Deploy as a web app/dashboard

---

## Conclusion

This project demonstrates a complete unsupervised learning workflow using K-Means. Starting from raw data, the pipeline successfully identifies meaningful customer segments that can be directly used for business strategies.

The key takeaway is that even simple algorithms like K-Means can produce powerful insights when combined with proper preprocessing and evaluation.
