# K_Means Clustering 


K-means clustering is a widely used unsupervised learning algorithm for partitioning a dataset into a set of distinct, non-overlapping subgroups or clusters. K-means clustering is a fundamental and widely-used algorithm in unsupervised learning for grouping data into clusters. 

It's known for its simplicity and efficiency, though it has limitations, such as sensitivity to initial centroid placement and difficulty with complex cluster shapes. The choice of K and dealing with its limitations are critical aspects of effectively using K-means in practical applications.


## Applications:

- Versatile: K-means is used in a wide range of applications including market segmentation, document clustering, image segmentation, and pattern recognition.

- Large Datasets: Its efficiency makes it suitable for large datasets, though it may struggle with very high-dimensional data.

---

### Basic Concept:

- Goal: The goal of K-means is to group similar data points together and discover underlying patterns. It aims to partition the dataset into K clusters, where each data point belongs to the cluster with the nearest mean.

- Clusters: Clusters are formed based on the closeness of data points to the centroid (mean) of clusters.

---

### How It Works:

1. Initialization:
   - The process starts by initializing K centroids randomly. These centroids are the initial representatives of the clusters.

2. Assignment Step:
   - Each data point in the dataset is assigned to the nearest centroid based on a distance metric (usually Euclidean distance), effectively partitioning the data into K clusters.

3. Update Step:
   - Once all points are assigned, the centroids of the clusters are recalculated as the mean of all points in the cluster.

4. Iteration:
   - The assignment and update steps are repeated iteratively until the centroids stabilize and don't change significantly between iterations, or a maximum number of iterations is reached.

--- 


## Limitations:

- Sensitivity to Initial Centroids: The final clusters can be sensitive to the initial random choice of centroids.

- Assumes Spherical Clusters: It assumes clusters are spherical and equally sized, which might not be the case in real-world data.

- Outliers Impact: The algorithm can be sensitive to outliers, which can skew the centroids.

- Difficulty with Complex Cluster Shapes: K-means might not work well with non-linearly separable or complex cluster shapes.

---

## Choosing K:

- Key Challenge: One of the key challenges in K-means clustering is deciding the number of clusters (K). There's no definitive way to determine the best K beforehand.

- Methods: Techniques like the Elbow Method, Silhouette Method, or Cross-validation are often used to estimate an appropriate number of clusters.

![Screenshot 2024-01-26 at 12 01 10 PM](https://github.com/kasteway/Unsupervised_Learning/assets/62068733/4f0ba344-e63e-40b8-bdae-db744aba01bd)

![Screenshot 2024-01-26 at 12 01 40 PM](https://github.com/kasteway/Unsupervised_Learning/assets/62068733/15c2997b-8067-42b0-a6fb-81febb7bd8ea)


### The Elbow Method and Silhouette Method are techniques used to determine the optimal number of clusters (K) in K-means clustering. 

Choosing the right number of clusters is crucial for the effectiveness of the K-means algorithm. The Elbow and Silhouette Methods are valuable techniques in K-means clustering for determining the optimal number of clusters. 

They provide different perspectives - the Elbow Method focuses on the variance within clusters, while the Silhouette Method assesses how distinct the clusters are from each other.

## 1. Elbow Method:

- Concept: The Elbow Method involves running the K-means clustering algorithm on the dataset for a range of values of K (number of clusters) and then calculating the sum of squared distances from each point to its assigned center. When these overall distances are plotted against the number of clusters, the "elbow" point, where the rate of decrease sharply changes, represents an appropriate number of clusters.

#### Implementation:

a. Run K-means clustering on the dataset for different values of K (e.g., K = 1 to 10).

b. For each K, calculate the total within-cluster sum of square (WSS).

c. Plot the curve of WSS according to the number of clusters K.

d. The "elbow" in the plot is generally considered as an indicator of the appropriate number of clusters.

- Limitation: The Elbow Method can sometimes be ambiguous and subjective, as the elbow may not always be clear or well-defined.

## 2. Silhouette Method:

- Concept: The Silhouette Method measures how similar an object is to its own cluster compared to other clusters. The silhouette score ranges from -1 to 1, where a high value indicates that the object is well matched to its own cluster and poorly matched to neighboring clusters.

### Implementation:

a. For each point, calculate the average distance from all other points in the same cluster (a) and the average distance from all points in the nearest cluster that the point is not a part of (b).

b. The silhouette score for each point is then given by (b - a) / max(a, b).

c. Calculate the mean silhouette score for all points for different values of K.

d. The value of K that gives the highest mean silhouette score is considered as the optimal number of clusters.

- Advantage: The Silhouette Method provides a more objective measure of the quality of clustering and can help identify the value of K that best separates the clusters.
Using These Methods:

#### Summary:

Often, both methods are used in tandem to cross-validate the choice of K. The Elbow Method can provide a quick visual cue, while the Silhouette Method offers a more detailed analysis.
The choice of K should also consider domain knowledge and the specific context of the data, as sometimes the mathematical optimal number of clusters might not align with practical or interpretational considerations.

--- 





## Variants and Improvements:

- K-means++: This variant offers an improved method for initializing the centroids to enhance the algorithm's performance.

- Mini-batch K-means: A variant that uses small random batches of data points to reduce the computational cost, particularly useful for very large datasets.
