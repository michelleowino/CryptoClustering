# CryptoClustering

In this project I used Python and unsupervised learning to predict if cryptocurrencies are affected by 24-hour or 7-day price changes.

# Steps taken: 

## Prepare the Data
- Use the StandardScaler() module from scikit-learn to normalize the data from the CSV file.
- Create a DataFrame with the scaled data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.

<img width="899" alt="Screenshot 2023-05-11 at 6 36 39 PM" src="https://github.com/michelleowino/CryptoClustering/assets/119654958/2fb5dc70-e957-431a-95ce-7b1251bd962b">

## Find the Best Value for k Using the Original Scaled DataFrame
Used the elbow method to find the best value for k using the following steps:

  - Create a list with the number of k values from 1 to 11.
  - Create an empty list to store the inertia values.
  - Create a for loop to compute the inertia with each possible value of k.
  - Create a dictionary with the data to plot the elbow curve.
  - Plot a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k.

## Cluster Cryptocurrencies with K-means Using the Original Scaled Data
Used the following steps to cluster the cryptocurrencies for the best value for k on the original scaled data:

  - Initialize the K-means model with the best value for k.
  - Fit the K-means model using the original scaled DataFrame.
  - Predict the clusters to group the cryptocurrencies using the original scaled DataFrame.
  - Create a copy of the original data and add a new column with the predicted clusters.
  - Create a scatter plot using hvPlot as follows:
  - Set the x-axis as "price_change_percentage_24h" and the y-axis as "price_change_percentage_7d".
  - Color the graph points with the labels found using K-means.
  - Add the "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point.

# Optimize Clusters with Principal Component Analysis
  - Using the original scaled DataFrame, performed a PCA and reduce the features to three principal components.
  - Retrieve the explained variance to determine how much information can be attributed to each principal component.
  - Create a new DataFrame with the PCA data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame

<img width="512" alt="Screenshot 2023-05-11 at 6 36 51 PM" src="https://github.com/michelleowino/CryptoClustering/assets/119654958/7b107b89-2098-4474-b554-01e3d5f527e8">

# Find the Best Value for k Using the PCA Data
Used the elbow method on the PCA data to find the best value for k using the following steps:
  - Create a list with the number of k-values from 1 to 11.
  - Create an empty list to store the inertia values.
  - Create a for loop to compute the inertia with each possible value of k.
  - Create a dictionary with the data to plot the Elbow curve.
  - Plot a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k.

# Cluster Cryptocurrencies with K-means Using the PCA Data
Used the following steps to cluster the cryptocurrencies for the best value for k on the PCA data:
  - Initialize the K-means model with the best value for k.
  - Fit the K-means model using the PCA data.
  - Predict the clusters to group the cryptocurrencies using the PCA data.
  - Create a copy of the DataFrame with the PCA data and add a new column to store the predicted clusters.
  - Create a scatter plot using hvPlot as follows:
  - Set the x-axis as "price_change_percentage_24h" and the y-axis as "price_change_percentage_7d".
  - Color the graph points with the labels found using K-means.
  - Add the "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point.
 
 # Results
 
 <img width="656" alt="Screenshot 2023-05-11 at 7 12 31 PM" src="https://github.com/michelleowino/CryptoClustering/assets/119654958/b085f5b3-283b-4090-b855-5698fe4063aa"> <img width="640" alt="Screenshot 2023-05-11 at 7 12 45 PM" src="https://github.com/michelleowino/CryptoClustering/assets/119654958/22443107-7872-4efb-ac93-232cc3d6f7be">
 
 <img width="658" alt="Screenshot 2023-05-11 at 7 12 56 PM" src="https://github.com/michelleowino/CryptoClustering/assets/119654958/0f4d185c-04fb-4499-a81f-15222b2b15ac">

<img width="652" alt="Screenshot 2023-05-11 at 7 13 08 PM" src="https://github.com/michelleowino/CryptoClustering/assets/119654958/bb5732cc-adea-4fe6-a28e-c464eef47092">

 After visually analyzing the results of the cluster analysis, it appears that there are no significant differences between the clusters generated using the original data and the PCA-transformed data. However, the positions of the clusters do vary between the two sets. Specifically, the clusters generated from the PCA-transformed data are more compact than those generated from the original data, which are more spread out. It's worth noting that both sets of clusters were generated using K-means with four clusters.
 
 
