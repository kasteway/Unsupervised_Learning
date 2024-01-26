##


Manhattan distance and Euclidean distance are two common metrics used in unsupervised learning for measuring the similarity or dissimilarity between data points. Here's a summary of their use:

Manhattan Distance (L1 norm):

Definition: Manhattan distance calculates the sum of the absolute differences between the coordinates of a pair of points. It is also known as L1 norm, taxicab or city block distance.
Usage in Unsupervised Learning:
Clustering: Particularly useful in clustering algorithms like K-Means, where it can be used to calculate the dissimilarity between data points and cluster centers.
High-Dimensional Data: Often preferred in high-dimensional data spaces as Euclidean distance can become inflated in such scenarios.
Robustness: More robust to outliers compared to Euclidean distance.
Feature Space: Effective when the algorithm needs to capture differences across dimensions (features) independently, as it treats axis-aligned differences individually.
Euclidean Distance (L2 norm):

Definition: Euclidean distance is the straight-line distance between two points in Euclidean space. It is calculated as the square root of the sum of the squared differences between the coordinates of the points (L2 norm).
Usage in Unsupervised Learning:
Clustering: Widely used in clustering algorithms, including K-Means, for measuring the distance between data points and cluster centroids.
Natural Interpretation: As it reflects the straight-line distance, it is more intuitive and natural in many applications, especially those involving physical distances.
Dimensionality Sensitivity: More sensitive to changes in higher dimensions, which can be a disadvantage in high-dimensional data spaces.
Feature Correlations: It takes into account the relationships between various features, as it measures the composite difference along all dimensions simultaneously.
