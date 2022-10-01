# Cryptocurrencies
An analysis of Cryptocurrency data using Unsupervised Machine Learning models and techniques.

## Overview
To assist the manager of an Advisory Services Team at Accountability Accounting, a prominent investment bank, who is interested in offering a new cryptocurrency investment portfolio for customers, the following analysis was provided to determine what cryptocurrencies are on the trading market and how they could be grouped to create a classification system for this new investment.

The data for this analysis was taken from https://min-api.cryptocompare.com/data/all/coinlist and required processing to fit the machine learning models. Since there was no known output for what our client was looking for, we decided to use unsupervised machine learning techniques, specifically, a clustering algorithm. This analysis was broken down into four steps:

1. Preprocess the dataset in preparation for testing.
2. Use the Principal Component Analysis (PCA) algorithm to reduce the dimensions of our dataset to 3 principal components.
3. Use the K-Means algorithm to create an elbow curve to find the best value for K and use it to predict K clusters for the data. 
4. Visualize the distinct groups corresponding to the 3 principal components and create a table with all currently tradable cryptocurrencies.

Visualizations of these processes are provided below.

## Results

### Preprocess the dataset in preparation for testing
Using Pandas, we preprocessed the dataset to prepare it for Principal Component Analysis. This involved determining which cryptocurrencies were being actively traded, dropping null values and rows that did not contain mined values, as well as columns that were considered to be unhelpful. 

### Principal Component Analysis
Applying the Principal Component Analysis (PCA) algorithm, we reduced the dimensions of the X DataFrame to three principal components and placed these dimensions in a new DataFrame.

### K-Means Algorithm and the Elbow Curve
Using the K-means algorithm, we created an elbow curve using hvPlot to find the best value for K from the pcs_df DataFrame created in step 2. Then, we ran the K-means algorithm to predict the K clusters for the cryptocurrencies’ data.

<img width="587" alt="elbow_curve" src="https://user-images.githubusercontent.com/104729703/193395074-7d432f2f-f2ce-4757-b200-72a84ca320cc.png">

### Visualizing the Distinct Cryptocurrencies
Using scatter plots with Plotly Express and hvplot, we visualized the distinct groups that corresponded to the three principal components created in Step 2, then created a table with all the currently tradable cryptocurrencies using the hvplot.table() function.

![PCA_analysis_3d_plot](https://user-images.githubusercontent.com/104729703/193395083-674168e0-585f-4185-b20e-38326bd707ca.png)


<img width="593" alt="Tradable_cryptocurrencies_table" src="https://user-images.githubusercontent.com/104729703/193395210-5137de49-c83a-41be-92c4-85b47978f450.png">


<img width="551" alt="MinMaxScaled_Crypto_scatterplot" src="https://user-images.githubusercontent.com/104729703/193395181-de0f5d5b-9366-4d25-af31-d97bc4e5c413.png">

## Summary
Our analysis showed that 533 distinct cryptocurrencies were found in our dataset that met the criteria for usable data. Of those, 35 are currently depleted.
