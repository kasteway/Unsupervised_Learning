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

---

# Manhattan & Euclidean Distance Measurments of Dissimilarity for Numberical


Manhattan distance and Euclidean distance are two common metrics used in unsupervised learning for measuring the similarity or dissimilarity between data points. Both Manhattan and Euclidean distances play crucial roles in unsupervised learning, particularly in clustering tasks, with their applicability depending on the data characteristics and the problem context.

- Manhattan and Euclidean distances are primarily used for numerical data in unsupervised learning.

*** The data points must be standardized before calculating 
- Standardization is generally recommended when the scales of features are different, especially in distance-based algorithms, to ensure that all features contribute equally to the results.

## 1. Manhattan Distance (L1 norm):

- Definition: Manhattan distance calculates the sum of the absolute differences between the coordinates of a pair of points. It is also known as L1 norm, taxicab or city block distance.

### Usage in Unsupervised Learning:

- Clustering: Particularly useful in clustering algorithms like K-Means, where it can be used to calculate the dissimilarity between data points and cluster centers.

- High-Dimensional Data: Often preferred in high-dimensional data spaces as Euclidean distance can become inflated in such scenarios.

- Robustness: More robust to outliers compared to Euclidean distance.

- Feature Space: Effective when the algorithm needs to capture differences across dimensions (features) independently, as it treats axis-aligned differences individually.


## 2. Euclidean Distance (L2 norm):

- Definition: Euclidean distance is the straight-line distance between two points in Euclidean space. It is calculated as the square root of the sum of the squared differences between the coordinates of the points (L2 norm).

### Usage in Unsupervised Learning:

- Clustering: Widely used in clustering algorithms, including K-Means, for measuring the distance between data points and cluster centroids.

- Natural Interpretation: As it reflects the straight-line distance, it is more intuitive and natural in many applications, especially those involving physical distances.

- Dimensionality Sensitivity: More sensitive to changes in higher dimensions, which can be a disadvantage in high-dimensional data spaces.

- Feature Correlations: It takes into account the relationships between various features, as it measures the composite difference along all dimensions simultaneously.

--- 

# Selecting which measurment to use:

The choice between Manhattan and Euclidean distances in unsupervised learning depends on the specific characteristics of the data and the requirements of the particular application or algorithm.



## 1. Nature of Data:

- Choose Manhattan distance if the data is high-dimensional or has many outliers.

- Opt for Euclidean distance when the straight-line distance is more relevant and meaningful.

## 2. Specific Requirements of the Algorithm/Application:

 - In algorithms where axis-aligned differences are important, Manhattan distance might be more suitable.

- For scenarios where the composite difference along all dimensions is crucial, Euclidean distance is preferred.

## 3. Outliers Sensitivity:

- Manhattan distance is more robust to outliers compared to Euclidean distance.

## 4. Dimensionality of Data:

- In high-dimensional spaces, Manhattan distance often performs better as Euclidean distance can become inflated.

## 5. Intuitive Understanding:

- Euclidean distance might be more intuitive in physical space or in applications where the concept of 'straight-line' distance is essential.

---
## Standardizing data points: 

Standardizing data points in unsupervised learning, particularly when using distance-based methods like clustering or dimensionality reduction, is often very important, but not always mandatory. Whether or not to standardize data points in unsupervised learning depends on the nature of your data and the specific algorithm you are using. 

- Scale Sensitivity: Many unsupervised learning algorithms, such as K-means clustering and Principal Component Analysis (PCA), are sensitive to the scale of the data. If the features are on different scales, algorithms that rely on distance measurements can be biased towards the features with larger scales.

- Standardization Purpose: Standardization (or Z-score normalization) transforms the data to have a mean of zero and a standard deviation of one. This process puts different variables on the same scale, ensuring that each feature contributes equally to the distance calculations.

## When It's Crucial:

- Diverse Feature Scales: If your dataset has features measured in different units (e.g., height in centimeters and weight in kilograms), standardization is crucial.

- Algorithms Requiring Distance Measures: In algorithms like K-means or hierarchical clustering, where the distance between data points is a key factor, standardization helps in preventing the dominance of certain features over others.

## When It Might Not Be Necessary:

- Homogenous Feature Scales: If all features are already on a similar scale or have similar ranges of values, standardization might not be as critical.

- Certain Algorithms: Some algorithms, like DBSCAN (Density-Based Spatial Clustering of Applications with Noise), may not require standardization depending on the context and the nature of the data.

- Data Distribution Considerations: Standardization assumes that the features follow a normal distribution. If this is not the case, other methods of scaling like Min-Max scaling might be more appropriate.

- Impact on Interpretability: Standardization can sometimes reduce the interpretability of the results, as the transformed data does not have the original units or scale. This aspect is important to consider, especially when explaining results to a non-technical audience.

---
