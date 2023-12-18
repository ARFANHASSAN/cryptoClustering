# cryptoClustering
Module 19 challenge

## Instructions:
## Prepare the Data:

Utilize the StandardScaler() module from scikit-learn to standardize the data obtained from the CSV file.

Generate a DataFrame containing the standardized data and assign the "coin_id" index from the original DataFrame as the index for the newly created DataFrame.
## Find the Best Value for k Using the Original Scaled DataFrame:

Employ the elbow method to determine the optimal value for k through the following steps:

Formulate a list comprising k values ranging from 1 to 11.
Establish an empty list to accumulate the inertia values.
Construct a for loop to calculate the inertia for each potential value of k.
Develop a dictionary containing the data necessary to plot the elbow curve.
Generate a line chart depicting all computed inertia values for diverse k values to visually discern the most suitable value for k.
In your notebook, respond to the question: What is the most advantageous value for k?
## Cluster Cryptocurrencies with K-means Using the Original Scaled Data@
Cluster the cryptocurrencies using the original scaled data by following these steps:

Initialize the K-means model with the optimal value for k.

Fit the K-means model using the original scaled DataFrame.

Predict the clusters to group the cryptocurrencies based on the original scaled DataFrame.

Duplicate the original data and introduce a new column containing the predicted clusters.

Employ hvPlot to create a scatter plot with the following specifications:
Set the x-axis as "PC1" and the y-axis as "PC2."
Color the graph points according to the labels obtained from K-means.
Include the "coin_id" column in the hover_cols parameter to identify the cryptocurrency associated with each data point.

## Optimize Clusters with Principal Component Analysis:

Conduct PCA on the original scaled DataFrame to reduce the features to three principal components.

Obtain the explained variance to assess the information attributed to each principal component. Respond to the following question in your notebook: What is the total explained variance of the three principal components?

Construct a new DataFrame containing the PCA data and designate the "coin_id" index from the original DataFrame as the index for the newly created DataFrame.

## Find the Best Value for k Using the PCA Data:


Apply the elbow method to the PCA data to determine the optimal value for k through the subsequent steps:

Formulate a list encompassing k-values ranging from 1 to 11.

Establish an empty list for accumulating inertia values.

Construct a for loop to calculate the inertia for each potential value of k.

Develop a dictionary containing the data required to plot the Elbow curve.

Generate a line chart illustrating all computed inertia values for diverse k values to visually discern the optimum k value.
Respond to the following queries in your notebook: What is the optimal value for k when utilizing the PCA data? Does it deviate from the optimal k value discovered using the original data?

## Cluster Cryptocurrencies with K-means Using the PCA Data:


Cluster the cryptocurrencies using the best value for k on the PCA data with the following steps:

Initialize the K-means model with the optimal value for k.

Fit the K-means model using the PCA data.

Predict the clusters to group the cryptocurrencies based on the PCA data.

Duplicate the DataFrame with the PCA data and introduce a new column to store the predicted clusters.

Utilize hvPlot to generate a scatter plot with the following specifications:

Set the x-axis as "price_change_percentage_24h" and the y-axis as "price_change_percentage_7d."
Color the graph points based on the labels obtained from K-means.
Include the "coin_id" column in the hover_cols parameter to identify the cryptocurrency associated with each data point.

##  Introduction:
Use your knowledge of Python and unsupervised learning to predict if cryptocurrencies are affected by 24-hour or 7-day price changes

## Findings:

## Elbow Curve Comparison:

 ![Elbow crve 1]("C:\Users\bella\Desktop\cryptoClustering\images\Elbow curve 1.png")

![Elbow curv 2]("C:\Users\bella\Desktop\cryptoClustering\images\Elbow curve 2.png")

![Elbow curve combined]("C:\Users\bella\Desktop\cryptoClustering\images\combined Elbow curve.png")


The elbow curve for the PCA data (elbow curve 2) demonstrates a diminished inertia value in contrast to the elbow curve for the original data (elbow curve 1). This signifies that employing fewer features led to a decrease in the sum of squared distances within clusters. A lower inertia value is indicative of enhanced clustering performance and a more compact grouping of data points within each cluster.

## Cluster Scatter Plot Comparison:

![cluster 1]("C:\Users\bella\Desktop\cryptoClustering\images\cluster 1.png")

![cluster 2]("C:\Users\bella\Desktop\cryptoClustering\images\cluster 2.png")

Cluster Graph 1 (utilizing original data): The clusters exhibit overlap, lacking a distinct separation or well-defined clusters. This implies that the use of the original data, featuring more elements, might not have adequately captured the underlying patterns or structure of the data for clustering purposes.

Cluster Graph 2 (utilizing PCA data): In this graph, clusters do not overlap, presenting a clear separation and well-defined clusters, identifiable as four distinct groups. This suggests that employing fewer features (via PCA) has likely mitigated noise and facilitated the disclosure of more distinct patterns in the data, resulting in more meaningful and distinguishable clusters.

## Conclusion:


Given these insights, it appears that employing fewer features (PCA data) for K-Means clustering of cryptocurrency data has yielded positive outcomes. This approach has generated more clearly defined and distinguishable clusters in contrast to utilizing the original data. The reduction in feature count through PCA is likely instrumental in emphasizing crucial patterns and mitigating noise, thereby contributing to more precise and meaningful clustering outcomes.