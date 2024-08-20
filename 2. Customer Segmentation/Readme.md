Objective:
The project focuses on analyzing customer buying behavior to understand and improve product selling performance by segmenting customers using the K-Means clustering algorithm. The data consists of a large number of transactions, and the analysis involves several steps, from data preparation to clustering.

1) Create Recency-Frequency-Monetary (RFM) Table
Recency: Time since the last purchase.
Frequency: Number of transactions.
Monetary Value: Total amount spent.

2) Manage Skewness 
Transformations: Apply and visualize various transformations to manage skewness, including log, square root, and Box-Cox transformations. Use the analyze_skewness function to apply these transformations and evaluate their effect on skewness.
Box-Cox Transformation: Applied to Recency and Frequency.
Cubic Root Transformation: Applied to MonetaryValue to handle negative values

*MORE about box-cox transformation*: 
Mathematical Formula: 
$$
y(\lambda) = 
\begin{cases} 
\frac{y^\lambda - 1}{\lambda} & \text{if } \lambda \neq 0, \\
\log(y) & \text{if } \lambda = 0.
\end{cases}
$$
y is the original data and lambda is the parameter that the Box-cos method optimizes to transform the data to be as close to normal as possible. 
1. λ=1: No transformation is applied; the data remains unchanged.
2. λ=0: A logarithmic transformation is applied, which is useful for reducing positive skewness.
3. λ<1: This compresses large values and stretches small values, helping to reduce positive skewness.
4. λ>1: This stretches large values and compresses small values, which can help to reduce negative skewness.
- These transformations aim to make the data more normally distributed, which is often a requirement for many statistical techniques.
- The box-cox transformation can only be applied to positive data because the logarithmic transformation is not defined for non-positive values. 
    - if the data contain zeros or negative numbers, it is common to add a constant to all values in the data. 
- The optimal lambda is usually found by maximizing the log-likelihood function, which measures how well the transformed data fits a normal distribution. 

*Cubic root transformation*
Cubic root can handle negative values, making it suitable for datasets with negative or zero values.
In summary, the cubic root transformation is a useful tool for handling data with negative values and reducing positive skewness. However, its effectiveness depends on the nature of the data and the degree of skewness. It’s often beneficial to compare the results of different transformations to determine the most appropriate one for your specific dataset.

3) Implement Clustering
Determine Optimal Number of Clusters: Use the elbow method to choose the number of clusters. 

4) Analyze Clusters
From the aggregation, you can interpret the clusters as follows:

Cluster 0: High Recency, moderate Frequency, and low MonetaryValue. This suggests a group of recent and frequent customers with relatively lower spending. They may be loyal but not necessarily high spenders.
Cluster 1: Low Recency, high Frequency, and moderate MonetaryValue. This indicates a group of active and frequent customers who are spending moderately. They could be newer but engaged customers.
Cluster 2: Low Recency, high Frequency, and high MonetaryValue. This cluster contains less frequent customers but with high spending and older purchases. They may represent churned or less active high-value customers.

