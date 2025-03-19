# CryptoClustering

### Solved File

#### Prepare the Data

• Used the StandardScaler() module from scikit-learn to normalize the data from the CSV file.

• Created a DataFrame with the scaled data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.

  > • The first five rows of the scaled DataFrame appear as follows:

![image](https://github.com/user-attachments/assets/bc59d643-4b10-4f93-aacf-bc92d646a86b)

### Find the Best Value for k Using the Scaled DataFrame

**Used the elbow method to find the best value for k using the following steps:**

• Create a list with the number of k values from 1 to 11.

• Create an empty list to store the inertia values.

• Created a for loop to compute the inertia with each possible value of k.

• Created a dictionary with the data to plot the elbow curve.

• Ploted a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k.

• The best value for K is 4 

### Cluster Cryptocurrencies with K-means Using the Scaled DataFrame

**Used the following steps to cluster the cryptocurrencies for the best value for k on the scaled DataFrame:**

• Initialize the K-means model with the best value for k.

• Fit the K-means model using the scaled DataFrame.

• Predict the clusters to group the cryptocurrencies using the scaled DataFrame.

• Create a copy of the scaled DataFrame and add a new column with the predicted clusters.

• Create a scatter plot using hvPlot as follows:

  > • Set the x-axis as "price_change_percentage_24h" and the y-axis as "price_change_percentage_7d".
  
  > • Color the graph points with the labels found using K-means.
  
  > • Add the "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point.

### Optimized Clusters with Principal Component Analysis

• Using the original scaled DataFrame, perform a PCA and reduce the features to three principal components.

• Retrieve the explained variance to determine how much information can be attributed to each principal component and then answer the following question in your notebook:

  > • The total explained variance of the three principal components is .886774 (89%)

• Create a new DataFrame with the scaled PCA data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.

  > • The first five rows of the scaled PCA DataFrame appear as follows:

![image](https://github.com/user-attachments/assets/840ddd8c-1c16-48f8-adc1-ded4384e3401)

### Find the Best Value for k Using the PCA DataFrame

**Use the elbow method on the scaled PCA DataFrame to find the best value for k using the following steps:**

• Create a list with the number of k-values from 1 to 11.

• Create an empty list to store the inertia values.

• Create a for loop to compute the inertia with each possible value of k.

• Create a dictionary with the data to plot the Elbow curve.

• Plot a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k.

• Was asked to answer the following question in my notebook:
  
  > • The best value for k when using the scaled PCA DataFrame is 4 

  > • Does it differ from the best k value found using the original scaled DataFrame? No 

### Cluster Cryptocurrencies with K-means Using the PCA DataFrame

**Use the following steps to cluster the cryptocurrencies for the best value for k on the PCA DataFrame:**

• Initialize the K-means model with the best value for k.

• Fit the K-means model using the scaled PCA DataFrame.

• Predict the clusters to group the cryptocurrencies using the scaled PCA DataFrame.

• Create a copy of the scaled PCA DataFrame and add a new column to store the predicted clusters.

• Create a scatter plot using hvPlot as follows:

  > • Set the x-axis as "PC1" and the y-axis as "PC2".
  
  > • Color the graph points with the labels found using K-means.
  
  > • Add the "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point.
  
• Answer the following question:

  > • What is the impact of using fewer features to cluster the data using K-Means?

**By using fewer features, we can achieve similar or even better clustering performance. The fact that we can still clearly identify three clusters in the reduced feature space indicates that the critical information required for accurate clustering is preserved. The use of dimensionality reduction techniques, like PCA, enhances the model's efficiency, reduces complexity, and potentially prevents overfitting, all while maintaining the ability to identify meaningful clusters in the data.**
