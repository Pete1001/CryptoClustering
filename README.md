# CryptoClustering
Module 11-apply your understanding of the K-means algorithm and principal component analysis (PCA) to classify cryptocurrencies according to their price fluctuations across various timeframes

# Cryptocurrency Clustering Analysis

This repository contains a Jupyter Notebook (`Crypto_Clustering.ipynb`) focused on clustering and analyzing cryptocurrency data using unsupervised machine learning techniques. The project employs K-Means clustering to group cryptocurrencies based on their market data, further optimized with Principal Component Analysis (PCA) for dimensionality reduction.

## Table of Contents
- [Overview](#overview)
- [Dataset](#dataset)
- [Requirements](#requirements)
- [Process](#process)
- [Results](#results)
- [Repository Structure](#repository-structure)
- [Usage](#usage)
- [Conclusion](#conclusion)

## Overview

The aim of this project is to explore and group cryptocurrencies by clustering them using K-Means, with additional optimization using PCA. The elbow method is applied to determine the optimal number of clusters (k-value), and the influence of each feature on the principal components is analyzed.

## Dataset

The analysis uses a dataset (`crypto_market_data.csv`) that includes market data on various cryptocurrencies. The dataset columns include:
- `coin_id`: Unique identifier for each cryptocurrency
- `price_change_percentage_24h`: Price change over the last 24 hours
- `price_change_percentage_7d`: Price change over the last 7 days
- Additional columns representing market and performance metrics

## Requirements

To run the notebook, install the following Python libraries:
- `pandas`
- `scikit-learn`

Install dependencies via:
```bash
pip install pandas scikit-learn
```

## Process

### Step 1: Data Loading and Preparation
1. **Data Loading**: The dataset is loaded into a pandas DataFrame with `coin_id` set as the index.
2. **Data Normalization**: The data is normalized using `StandardScaler()` for optimal clustering performance.

### Step 2: Finding the Optimal k-Value
1. **Elbow Method**: A range of k-values (from 1 to 11) is tested, and inertia values are computed for each.
2. **Elbow Plot**: The inertia values are plotted to visually identify the optimal k-value.

### Step 3: K-Means Clustering
1. **Original Scaled Data**: K-Means clustering is applied using the best k-value.
2. **Cluster Visualization**: A scatter plot of `price_change_percentage_24h` vs. `price_change_percentage_7d` shows the resulting clusters.

### Step 4: Dimensionality Reduction with PCA
1. **PCA Transformation**: The data is reduced to three principal components.
2. **Explained Variance**: The total explained variance of the components is calculated.
3. **New Clustering**: The elbow method and K-Means clustering are repeated on the PCA-reduced data.

### Step 5: Analyzing Feature Weights
- A DataFrame is created to display the weights of each feature on each principal component, indicating the influence of specific features on each component.

## Results

1. **Optimal k-value**: The best k-value is determined both with the original and PCA-reduced data.
2. **Clustering Performance**: Clustering is evaluated using both the original and PCA-reduced datasets to assess the impact of dimensionality reduction.
3. **Feature Influence**: Features with strong positive or negative influence on each principal component are identified.

## Repository Structure

- `Crypto_Clustering.ipynb`: The main Jupyter Notebook containing all steps of the analysis.
- `crypto_market_data.csv`: CSV file with cryptocurrency market data (load as instructed in the notebook).
- `README.md`: This file.

## Usage

1. Clone the repository:
   ```bash
   git clone <repository-url>
   ```
2. Open the Jupyter Notebook:
   ```bash
   jupyter notebook Crypto_Clustering.ipynb
   ```
3. Follow the steps in the notebook to run each cell sequentially.

## Conclusion

This project demonstrates the use of clustering and dimensionality reduction to analyze and group cryptocurrencies based on market performance. The optimized clustering using PCA reveals how fewer features can simplify the clustering process without significant information loss, providing insights into patterns and trends in cryptocurrency data.
