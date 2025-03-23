# Clustering Subreddit Texts

## Overview
This project analyzes unsupervised clustering of Reddit texts using a subset of 2,000 samples from [Religion Kaggle Dataset](https://www.kaggle.com/datasets/rayyan123z/religion) across four categories: Hinduism, Travel, Fitness, and Food. The goal is to evaluate whether clustering methods can discover meaningful groupings aligned with original subreddit labels.

## Methodology
The texts were preprocessed (stopword removal, tokenization, etc.) and represented in two ways: 
- **TF-IDF**, followed by dimensionality reduction with **UMAP**
- **Word2Vec**, trained on the dataset.

Three clustering algorithms were applied with grid search for hyperparameter tuning:
- **K-Medoids** (cosine, Euclidean, Manhattan)
- **Gaussian Mixture Models** (full/diag/spherical covariance)
- **K-Means**.

The number of clusters was selected based on the **Silhouette Score**. Labels were inferred using majority voting in each cluster.

## Results
In all methods, the best Silhouette Score was achieved with 4 clusters—matching the number of true labels. Accuracy of label inference was consistently high (>90%), comparable to a supervised KNN classifier.

TF-IDF with UMAP consistently outperformed Word2Vec in clustering metrics, although both achieved strong classification accuracy. Silhouette Score did not always correlate with accuracy, highlighting the complexity of text data.

## Documentation
Detailed analysis with visuals, confusion matrices, and performance tables is available in the [PDF documentation](subreddit_clustering_doc.pdf).


