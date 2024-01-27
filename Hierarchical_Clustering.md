# Hierarchical Clustering:

Hierarchical clustering is a method of cluster analysis which seeks to build a hierarchy of clusters. 

Hierarchical clustering is a versatile method that provides a detailed insight into the data structure without requiring the number of clusters to be specified beforehand. Its main challenges lie in computational demands and the sensitivity to the choice of linkage criteria.

*** Can be used for Numerical & Categorical Data ***

### Basics of Hierarchical Clustering:

   - Goal: To build a hierarchy of clusters, either by merging smaller clusters into larger ones or splitting larger clusters into smaller ones.

   - Method: It creates a tree-like structure (dendrogram) representing the data points and their hierarchical relationships.

      #### Two Main Approaches:
       - Agglomerative (Bottom-Up): Starts with each data point as a separate cluster and merges them step by step based on some similarity measure.
        - Divisive (Top-Down): Starts with all data points in a single cluster and recursively splits the cluster into smaller clusters.

--- 
### Process:

   - Compute Similarity: Calculate the similarity (or distance) between each pair of data points.

   - Merge or Split: Either merge the closest (most similar) clusters or split the farthest (least similar) cluster.

   - Update Hierarchy: Continuously update the hierarchy until all data points are in a single cluster (agglomerative) or each is in its own cluster (divisive).

--- 
### Characteristics:

   - No Need to Specify Number of Clusters: Unlike K-Means, there's no need to specify the number of clusters in advance.

   - Flexibility in Cluster Shapes: Can capture complex shapes and relationships between data points.
     
   - Dendrogram Representation: The resulting hierarchical structure is typically visualized as a dendrogram.
   - Dendrograms are a crucial tool in unsupervised learning for visualizing the results of hierarchical clustering, aiding in the determination of the optimal number of clusters, understanding the data structure, and comparing different clustering approaches. They provide a unique and intuitive way to explore and interpret complex data relationships.

<img width="705" alt="Screenshot 2024-01-27 at 7 37 32 AM" src="https://github.com/kasteway/Unsupervised_Learning/assets/62068733/03cd1c8a-3f01-46fe-bcd0-dfdbd9031129">

[Data Camp](https://www.datacamp.com/tutorial/introduction-hierarchical-clustering-python)

---
### Advantages:

   - Intuitive Understanding: The dendrogram provides a rich and intuitive representation of the data structure.

   - Versatility: Suitable for various scales and types of data.

   - No Assumption of Spherical Clusters: Unlike K-Means, it doesn't assume any particular shape for the clusters.

### Disadvantages:

   - Computational Complexity: Especially for agglomerative approach, can be computationally expensive with large datasets.

   - Ambiguity in Merging/Splitting Criteria: The choice of linkage criteria (how to measure distance between clusters) can significantly affect the outcome.

   - Irreversible Steps: Once a step is made to merge or split clusters, it cannot be undone, which might lead to suboptimal results.

---

### Applications

   - Gene Sequence Analysis: Used in bioinformatics for classifying organisms based on their genetic characteristics.

   - Document Clustering: Grouping documents into categories based on their content.

   - Customer Segmentation: Identifying different customer groups in marketing data.

---

## Determine the distance between clusters:

In hierarchical clustering, the method used to determine the distance between clusters is crucial. The choice often depends on the specific characteristics of the data and the goals of the clustering. 

Each linkage method has its advantages and disadvantages, and the choice of method can significantly impact the results of hierarchical clustering. 


### 1. Ward's Method:
*** Most often used & applied only to Numerical Quanitative Variables ***

- Description: Ward's method looks to minimize the total within-cluster variance. At each step, the pair of clusters with the minimum between-cluster distance (in terms of variance) is merged.

- Characteristics: This method tends to create more equally sized clusters and is particularly useful when clusters are roughly spherical. It's less likely to be influenced by outliers compared to single linkage.
  
![Screenshot 2024-01-27 at 7 17 37 AM](https://github.com/kasteway/Unsupervised_Learning/assets/62068733/c318461a-017b-44e9-a7d0-f0f1cafb2138)

### 2. Single Linkage (Nearest Neighbor):

- Description: In single linkage clustering, the distance between two clusters is defined as the shortest distance between any two points in the respective clusters.

- Characteristics: This method can create long, "stringy" clusters. It's sensitive to outliers and can sometimes result in clusters that are not very compact or homogeneous.


### 3. Complete Linkage (Farthest Neighbor):

- Description: Complete linkage defines the distance between two clusters as the longest distance between any two points in the respective clusters.

- Characteristics: This method tends to create more compact and evenly sized clusters compared to single linkage and is less sensitive to outliers. However, it can be influenced by extreme values.

### 4. Group Average Linkage (Average Linkage):

- Description: The distance between two clusters is computed as the average distance between all pairs of points in the two clusters.

- Characteristics: This method balances between the sensitivity of single and complete linkage, often providing more natural clusterings. It's less sensitive to outliers than single linkage.

### 5. Centroid Linkage (UPGMC):

- Description: In centroid linkage clustering, the distance between two clusters is the distance between their centroids (i.e., the mean point of each cluster).

- Characteristics: This method can be affected by the sizes of the clusters, and clusters may not be as well-separated as with other methods. It's also sensitive to initial conditions and may result in different clusterings depending on the initial centroids.



---

# Categorical - Matching Cofficient & Jaccard's Cofficient Similarity Measurments


Matching Coefficient and Jaccard Coefficient are two similarity measurements often used in unsupervised learning, especially for dealing with categorical or binary data. 



## 1. Matching Coefficient:

- Definition: The Matching Coefficient measures similarity between two sets by counting the number of attributes that are the same (both present or both absent) and ignoring the attributes that are different. It's used primarily for binary data.

### Usage in Unsupervised Learning:

- Suitability for Binary Data: Ideal for datasets with binary attributes (e.g., 0/1, Yes/No).

- Simple Similarity Measure: It provides a straightforward count of matches, making it easy to interpret.

- Application in Clustering: Useful in clustering algorithms, like hierarchical clustering, when working with binary attributes.

- Limitation: It doesn't account for the proportion of mismatches, which can be a limitation in some contexts.


## 2. Jaccard Coefficient:

- Definition: The Jaccard Coefficient, or Jaccard Index, measures similarity between finite sample sets. It's defined as the size of the intersection divided by the size of the union of the sample sets. Commonly used for binary and categorical data.

*** Jaccard Coefficient's consideration of mismatches often makes it a more robust choice in many applications.

### Usage in Unsupervised Learning:

- Application in Diverse Data Types: Used for both binary and categorical data, including text data (like document similarity).

- Handling Sparse Data: Particularly effective in scenarios with sparse data, like document clustering or gene sequence analysis.

- Robustness: More robust than the Matching Coefficient as it accounts for both the presence and absence of features.

- Clustering and Association: Employed in clustering algorithms and in computing similarity for association rule mining.

---

## Differences Between the Two:

- Focus on Mismatches: The Jaccard Coefficient considers the proportion of mismatches, making it more informative in datasets where the absence of a feature is as significant as its presence.

- Application Contexts: Matching Coefficient is simpler and may be preferred in contexts where the mere presence or absence of features is the focus. Jaccard Coefficient is more nuanced and useful in cases where the relative absence of features is also important.

## Choosing Between Them:

- Data Sparsity: For sparse datasets, the Jaccard Coefficient is often more appropriate.

- Data Type: If dealing exclusively with binary data and only the presence/absence of features is important, the Matching Coefficient might suffice.

- Contextual Importance of Feature Absence: If the absence of a feature is as informative as its presence, the Jaccard Coefficient is a better choice.


---

## Dendrogram to visualize the clusters:

A dendrogram is a tree-like diagram that is widely used in unsupervised learning, especially in hierarchical clustering, to visualize the arrangement of the clusters produced by the algorithm. 

Dendrograms are a crucial tool in unsupervised learning for visualizing the results of hierarchical clustering, aiding in the determination of the optimal number of clusters, understanding the data structure, and comparing different clustering approaches. They provide a unique and intuitive way to explore and interpret complex data relationships.

### 1. Visual Representation of Hierarchical Clustering:

- Structure: A dendrogram illustrates how each cluster is composed by branching out into its subclusters or individual elements. Each branch represents a cluster, and the length of the branches represents the distance or dissimilarity between clusters.

- Cluster Formation: It shows the sequence of cluster fusion or division, providing insights into the groupings and similarities within the data.

### 2. Determining the Number of Clusters:

- Cutting the Dendrogram: By 'cutting' the dendrogram at a certain level, you can decide the number of clusters to retain. The height at which the cut is made is critical – a higher cut results in fewer, larger clusters, while a lower cut leads to more, smaller clusters.

- Interpreting Distances: The height of the cuts corresponds to the distance or dissimilarity at which clusters are merged, aiding in understanding the cluster structure's strength.

### 3. Data Exploration and Interpretation:

- Insights into Data: Dendrograms help in exploring and interpreting the data structure. They can reveal relationships and natural divisions in the data that might not be apparent otherwise.

- Identifying Outliers: They are also useful for identifying outliers, as outliers will be merged into clusters at much higher distances than the rest of the data.

### 4. Comparing Clustering Methods:

- Linkage Criteria: Dendrograms can be used to compare the results of different linkage methods (like single, complete, average, centroid, Ward’s method) in hierarchical clustering.

- Evaluating Cohesiveness: They visually display the cohesiveness of the clusters formed by different methods.

### 5. Use in Other Domains:

- Beyond Clustering: While most commonly used in clustering, dendrograms can also be applied in other domains like phylogenetics, gene expression data analysis, and other fields where hierarchical relationships are explored.

### Limitations:

- Complexity with Large Data: For very large datasets, the dendrogram can become cluttered and difficult to interpret.

- Two-Dimensional Limitation: Dendrograms represent multi-dimensional data in two dimensions, which can sometimes oversimplify the relationships in the data.

--- 


