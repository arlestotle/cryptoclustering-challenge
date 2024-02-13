# Module 19 - cryptoclustering-challenge

### In this challenge, you’ll use your knowledge of Python and unsupervised learning to predict if cryptocurrencies are affected by 24-hour or 7-day price changes.

## Prepare the Data
#### 
Use the StandardScaler() module from scikit-learn to normalize the data from the CSV file.

Create a DataFrame with the scaled data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.

## Find the Best Value for k Using the Original Scaled DataFrame
#### Use the elbow method to find the best value for k using the following steps:
1. Create a list with the number of k values from 1 to 11.
2. Create an empty list to store the inertia values.
3. Create a for loop to compute the inertia with each possible value of k.
4. Create a dictionary with the data to plot the elbow curve.
5. Plot a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k.
6. Answer the following question in your notebook: What is the best value for k?
- The best value for k is 4, because it is the point where intertia starts decreasing in a linear fashion. 4 is the optimal number of clusters for the dataset.

## Cluster Cryptocurrencies with K-means Using the Original Scaled Data
#### Use the following steps to cluster the cryptocurrencies for the best value for k on the original scaled data:
1. Initialize the K-means model with the best value for k.
2. Fit the K-means model using the original scaled DataFrame.
3. Predict the clusters to group the cryptocurrencies using the original scaled DataFrame.
4. Create a copy of the original data and add a new column with the predicted clusters.
5. Create a scatter plot using hvPlot as follows:
 - Set the x-axis as "PC1" and the y-axis as "PC2".
 - Color the graph points with the labels found using K-means.
 - Add the "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point.
 
## Optimize Clusters with Principal Component Analysis
#### 
1. Using the original scaled DataFrame, perform a PCA and reduce the features to three principal components.
2. Retrieve the explained variance to determine how much information can be attributed to each principal component and then answer the following question in your notebook:
 - What is the total explained variance of the three principal components? 
     - Roughly 88% of the total variance can be explained by the three components. The total explained variance can be found by taking the sum of the three principal components.
3. Create a new DataFrame with the PCA data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.

## Find the Best Value for k Using the PCA Data
#### Use the elbow method on the PCA data to find the best value for k using the following steps:
1. Create a list with the number of k-values from 1 to 11.
2. Create an empty list to store the inertia values.
3. Create a for loop to compute the inertia with each possible value of k.
4. Create a dictionary with the data to plot the Elbow curve.
5. Plot a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k.
6. Answer the following question in your notebook:
 - What is the best value for k when using the PCA data? 
     - The best k-value for the PCA data is 4. k = 4 is the point where intertia starts decreasing in a linear fashion, thus, it is the optimal number of clusters for the dataset.
 - Does it differ from the best k value found using the original data?
     - The optimal k values for both the PCA clusters and original cluster data were the same.

## Cluster Cryptocurrencies with K-means Using the PCA Data
#### Use the following steps to cluster the cryptocurrencies for the best value for k on the PCA data:
1. Initialize the K-means model with the best value for k.
2. Fit the K-means model using the PCA data.
3. Predict the clusters to group the cryptocurrencies using the PCA data.
4. Create a copy of the DataFrame with the PCA data and add a new column to store the predicted clusters.
5. Create a scatter plot using hvPlot as follows:
 - Set the x-axis as "price_change_percentage_24h" and the y-axis as "price_change_percentage_7d".
 - Color the graph points with the labels found using K-means.
 - Add the "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point.
6. Answer the following question:
 - What is the impact of using fewer features to cluster the data using K-Means?

## Visualize and Compare the Results 
#### 
1. Create a composite plot by using hvPlot and the plus sign (+) operator to compare the elbow curve that you created from the original data with the one that you created from the PCA data.
2. Create a composite plot by using hvPlot and the plus (+) operator to compare the cryptocurrency clusters that resulted from using the original data with those that resulted from the PCA data.
3. Answer the following question: 
 - Based on visually analyzing the cluster analysis results, what’s the impact of using fewer features to cluster the data by using K-means?
     - The impact of using PCA data resulted clusters that were closer to eachother on the graph. Using the PCA data there were more datapoints in the 0 and 1 cluster groups and using the original data there were more datapoints in the 0 and 2 cluster groups. Looking at the scatter plots, it appears that the original data crypto clusters has some overlapping predictions, whereas the PCA crypto clusters appear to have a more clear separation. 




