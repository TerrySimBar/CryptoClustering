# CryptoClustering   
<br>
An unsupervised machine learning project that uses Python (Pandas, Scikit-learn and hvPlot) and K-Means to cluster cryptocurrencies based on their performance in different time periods. 
<br>  
<br>
<br>

<img src="/images/comp_elbow.png" alt="Composite Elbow Curve" width="800"/>
<br>
<br>
<br>

<img src="/images/comp_clust.png" alt="Composite Cluster Scatter Plot" width="800"/>
<br>
<br>
<br>

## Table of Contents
### Introduction
### Features
### Requirements & Dependencies
### Project Structure
### Usage
### Contributing
### License
<br>

### Introduction
This project primarily seeks to predict if cryptocurrencies are affected by 24-hour or 7-day price changes. The project uses K-Means algorithm to cluster cryptocurrency data, and then Principal Component Analysis (PCA) is used to reduce the features to three principal components. The results are then compared to determine if reducing the dimensions with PCA reduced the quality of the clusters. 
<br>

### Features
- Use SciKit-learn's `KMeans` algorithm to cluster  data.  

- Use Scikit-learn's `StandardScaler` to process the features data.   

- Use Scikit-learn's `PCA` algorithm to reduce the dimensions of the features data and check the effect on the clusters. 

<br>

### Requirements & Dependencies
This project uses the following software and Python libraries:    

Python (version 3.10.9)

Pandas (version: 2.0.3)

Sci-Kit Learn (version: 1.3.0)

hvPlot (version: 0.8.4)

<br>

### Project Structure
<br>

#### Read and prepare the data for clustering

The data for this project is read from the `crypto_market_data.csv` file and prepared for clustering using the following steps:      

1. **Set Up Dependencies:** Import the necessary libraries/dependencies.    

2. **Read and preview the CSV file:** Read the CSV file into a Pandas DataFrame using `pd.read_csv` and preview the DataFrame using `df.head()`.      

3. **Generate the summary statistics:** Use `df.describe()` to get the summary statistics for the DataFrame.    

4. **Plot the data:** Use `hvplot.line` to plot the data.

5. **Normalize the data:** Use `StandardScaler.fit_transform`to normalize the data.  

6. **Create a DataFrame for the scaled data:** Create a DataFrame for the scaled data, and preview the DataFrame using `df.head()` to check that the data is scaled. 
 
<br>

#### Find the best value for `k` using the elbow curve 
The following process is used to find the best value for `k` using the elbow curve: 

1. **Create a list with the range of values for `k`:** Create a list with the range of values for `k` (1-11).

2. **Create an empty list to store the inertia values:** 

3. **Build the elbow DataFrame and check the head:** Use a for loop to iterate through the values in the `k` list and build the elbow DataFrame, and check the head of the DataFrame.

4. **Plot the elbow curve to get the appropriate k value:** Use `hvplot.line` to plot the elbow curve and determine the appropriate value for `k`. 

<br>

#### Cluster cryptocurrencies with K-Means and visualize the results
These steps are used to cluster the cryptocurrencies with K-Means and visualize the results:    

1. **Initialize the K-Means model:** Set the `n_clusters` parameter to the appropriate value of `k` determined from the elbow curve, and choose a random state of greater than 0. It is also recommended to set the `n_init` parameter to 10 to mitigate suboptimal clusterings.     

2. **Fit the K-Means model:** Use `fit` to fit the K-Means model with the scaled data.    

3. **Predict and print the clusters:** Use `predict` to predict the clusters for the data, and then print the clusters. Check the head of the DataFrame to ensure that the clusters are added to the DataFrame.  

4. **Plot the clusters:** Use `hvPlot.scatter` to plot the clusters.

<br>

#### Optimize clusters with Principal Component Analysis (PCA)
The following steps are used to optimize the clusters with Principal Component Analysis (PCA):   

1. **Create a PCA model instance:** Use `PCA` to create a PCA model instance with three principal components.  

2. **Reduce and preview the data:** Use `fit_transform` to reduce the dimensions of the scaled DataFrame to the three principal components, and preview the DataFrame.

3. **Check and compute the explained variance:** Retrieve and print the explained variance using `explained_variance_ratio_`. Compute the total explained variance by getting the sum of the explained variance ratio.

4. **Create a DataFrame for the PCA data:** Create a DataFrame for the PCA data, and preview the DataFrame.

5. **Find the best value for K using the PCA data:** Take similar steps as above to find the best value for `k` using the PCA data. 

6. **Plot the PCA clusters:** Use `hvplot.scatter` to plot the PCA clusters.    

<br>

#### Compare the Elbow curves and clustering results

1. **Create a composite line graph:** Use `hvplot.line` with the `+` operator to create a composite line graph of the elbow curves for the original data and the PCA data. 

2. **Create a composite scatter plot:** Use `hvplot.scatter` with the `+` operator to create a composite scatter plot of the clustering results for the original data and the PCA data.   

3. **Compare the two composite graphs:** Compare the two composite graphs to determine if reducing the dimensions with PCA reduced the quality of the clusters. 

<br>

### Usage
1. Ensure that you have all the necessary dependencies and files/scripts. 
2. Load the project files in an appropriate code editor such as Jupyter Notebook. 
3. Run the script in the Jupyter Notebook step by step
to execute the code and visualize the results appropriately.       

#### Contributions
Contributions to this project are highly encouraged! If you wish to contribute, please follow these guidelines:

- Fork the `CryptoClustering` repository and clone it locally.
- Create a new branch for your feature or bug fix.
- Commit your changes with descriptive commit messages.
- Push your branch to your forked repository.
- Submit a pull request to the original repository.
- Please ensure that your code adheres to the project's coding style and conventions.


If you encounter any issues or have suggestions for improvements, please open an issue on the GitHub repository.

### License
These projects are licensed under the MIT License. Feel free to use, modify, and distribute the code as per the terms of the license. 