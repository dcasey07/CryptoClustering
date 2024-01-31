# Crypto Clustering: Module 19

## Objective

The goal for this challenge was to create an unsupervised machine learning model that will attempt to predict if cryptocurrencies are affected by 24-hour or 7-day price changes.

## Features

The jupyter notebook scales the csv of the crypto market data of price changes over various intervals from 1 day to 1 year and generate elbow plots to identify the proper amount of clusters. Then after creating a model using only the scaled data, a second model is created using PCA to reduce the dimensions of the data while still offering a robust coverage of data. The resulting scatter plots and line graphs are combined for a quick comparison, and analysis is located throughout the cells of the notebook.

## Dependencies and Implementation
This model was created using Python in Jupyter notebook, with the sklearn library importing KMeans, PCA, and a Standard Scaler. Plots were generated on hvplot through the use of pandas dataframes.

## Analysis

- The elbow curve of the original scaled data begins to flatten after the k value extends before 4. As the k value changes from 3 to 4, the inertia decreases by 44.168, while from k value 4 to 5, the inertia only decreases by 13.72. At each interval of k after that, the inertia drops by approximately 10 or less.
- After fitting the model using PCA, the total explained variance comes out to .89503166, which covers almost 90% of the information despite reducing the dimensionality to only 3 components.
- On the PCA elbow curve, the plot shows that a k value of 4 is the last interval where the inertia starts to flatten out.
- From 3 to 4, the inertia drops by 44.11, but from 4 to 5, the inertia only decreases by 11.826.
- While the k value is the same, the inertia value starts at a lower point when using PCA, and the point where it flattens out is also at a lower inertia than the original scaled data. Despite reducing the dimensionality of the data, the PCA model creates a much more clustered representation of the data, while still offering a significant amount of data coverage.
- PCA also revealed a much clearer concept of the outlier clusters, and how they might be more easily categorized as opposed to using the scaled data without PCA.




