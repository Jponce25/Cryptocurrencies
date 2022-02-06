# Cryptocurrencies

## Overview of the analysis
For this project we are interested in identify a new cryptocurrency investment portfolio for customers, so we create a report that includes what cryptocurrencies are on the trading market and how they could be grouped to create a classification system for this new investment.

The data need to be processed to fit the unsupervised machine learning models because there is no know output. For the type of data we need a clustering algorithm (K-means algorithm). Finally using the results we try to analyze it and discover trends to invest in these new currencies 

## Data Preprocessing

Using pandas, we reduce and clean our dataset for 1,252 cryptocurrencies to 532 tradable cryptocurrencies.

For this process we follow this steps:
-Remove non trading cryptocurrencies and remove the column
-Filter only when coins have been mined
-Remove rows that have at least one null value
-Use get_dummies method to change text for numbers in our strings columns (Algorithm and ProofType)
-Scale data using the StandardScaler fit_transform() function 

## Principal Component Analysis

Then we use the SKLearn Principal Component Analysis (PCA) algorithm, in order to reduce the dimensions of the X DataFrame to three principal components and place these dimensions in a new DataFrame (PC 1, PC 2 and PC 3).

<img src="https://github.com/Jponce25/Cryptocurrencies/blob/fa501ece8144b10b95295a9f89557f7305c5840d/Image/Imagen1.png" width="250">

## Elbow Curve and K-means Algorithm

As we don´t know about what is the best number of clusters, we create an elbow curve using hvPlot to find the best value for K from the pcs_df DataFrame (4). Then, using the K-means algorithm we run a model to predict the K clusters for the cryptocurrencies’ data.

<img src="https://github.com/Jponce25/Cryptocurrencies/blob/fa501ece8144b10b95295a9f89557f7305c5840d/Image/Imagen2.png" width="700">

<img src="https://github.com/Jponce25/Cryptocurrencies/blob/fa501ece8144b10b95295a9f89557f7305c5840d/Image/Imagen3.png" width="700">

## Visualizing Cryptocurrencies Results

Finally, creating scatter plots with Plotly Express and hvplot, we can visualize the distinct groups that correspond to the three principal components we create above. The 3-D scatter allows us to graph our data using the 3 components that we have previously created using the PCA algorithm 

<img src="https://github.com/Jponce25/Cryptocurrencies/blob/fa501ece8144b10b95295a9f89557f7305c5840d/Image/Imagen4.png" width="700">

Then we create a table with all the currently tradable cryptocurrencies using the hvplot.table() function.

<img src="https://github.com/Jponce25/Cryptocurrencies/blob/fa501ece8144b10b95295a9f89557f7305c5840d/Image/Imagen5.png" width="700">

Finally, we make a scatter with the information that we consider to be relevant (TotalCoinSupply and TotalCoinsMined), maintaining the classification that we made with the K means model.

<img src="https://github.com/Jponce25/Cryptocurrencies/blob/fa501ece8144b10b95295a9f89557f7305c5840d/Image/Imagen6.png" width="400">

<img src="https://github.com/Jponce25/Cryptocurrencies/blob/fa501ece8144b10b95295a9f89557f7305c5840d/Image/Imagen7.png" width="700">

## Conclusions

Analyzing the data we can identify that there is a cluster where we only have one observation (BitTorrent). The scatter diagrams allow us to know the distribution and classification of the data in four groups of cryptocurrencies.

Analyzing the last scatter plot we can see the relationship that exists between the supply variable and the mined quantity, If we know that the price of a cryptocurrency is defined by these two variables, we can conclude that cryptocurrencies belonging to classes 0 and 1 could be a good option to invest, especially in more stable cryptocurrencies such as *ByteCoin (1), gCn Coin (1), the Qwertycoin (1), infinite Coin (1) and Lynx (0)*
