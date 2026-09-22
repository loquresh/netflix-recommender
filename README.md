# Netflix Movie Rating Analysis

## Overview

This project analyzes a sparse movie rating matrix using matrix factorization, K-Means clustering, and principal component analysis (PCA). The goal is to predict missing movie ratings and explore groups of movies with similar rating patterns.

## Project Questions

* How well can matrix factorization predict missing movie ratings?
* Can movies be grouped based on similarities in user rating patterns?
* How do these movie clusters appear when visualized using PCA?

## Data Source

[Netflix Movie Ratings](https://www.kaggle.com/datasets/luisheitorribeiro/netflix-movie-ratings) — Kaggle

The dataset contains an incomplete user-by-movie rating matrix along with a complete version used to evaluate the predictions. Ratings range from 1 to 5, with missing ratings represented by 0 in the incomplete matrix.

## Methodology

### 1. Matrix Factorization

Matrix factorization was used to estimate missing ratings in the incomplete rating matrix. The model represents users and movies using latent factors and alternates between estimating user and movie factors.

The model was trained using:

* Rank: 3 latent factors
* Regularization parameter: 0.001
* Maximum iterations: 10

### 2. Movie Clustering

The completed rating matrix was used to represent each movie by its rating pattern across users. The movie vectors were normalized and clustered using K-Means.

The elbow method was used to evaluate different numbers of clusters. The plot showed a noticeable bend around **k = 3**, so three clusters were used for the final analysis.

### 3. PCA Visualization

PCA was used to reduce the movie rating data to two dimensions for visualization. Each point represents a movie, with color indicating its K-Means cluster assignment.

## Findings

### 1. Matrix Factorization Performance

The final model achieved an **RMSE of 0.503** when comparing the predicted ratings with the complete rating matrix. RMSE is measured on the same 1-5 scale as the original ratings, with lower values indicating smaller prediction errors.

### 2. Movie Clusters

K-Means identified three groups of movies based on similarities in their user rating patterns. The cluster assignments provide a way to explore whether movies with similar rating behavior tend to group together.

### 3. PCA Visualization

The PCA plot provides a two-dimensional view of the movie rating patterns and allows the K-Means clusters to be visually compared. Movies that appear closer together have more similar patterns in the dimensions captured by the PCA visualization.

## Tools

Python, NumPy, pandas, SciPy, scikit-learn, Matplotlib, Google Colab
