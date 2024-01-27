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
