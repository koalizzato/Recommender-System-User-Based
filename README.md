# Recommender-system-user-based
I developed a simple recommender system for the RentTheRunway dataset.

This project presents a recommendation system developed for Rent the Runway, focusing on user-item interactions to suggest items based on historical rental data. The system was part of my academic work and demonstrates the use of k-Nearest Neighbors (k-NN) and Singular Value Decomposition (SVD) algorithms to build and evaluate personalized recommendations.

## Project Highlights
### 1. Dataset Overview
- Source: The dataset contains 146,381 observations and 15 features, including user demographics, item characteristics, and ratings.
- Preparation: Key variables (rating, user_id, item_id) were extracted, with ratings normalized for consistency. Units like weight and height were converted to kilograms and centimeters for standardization.
- A subset of 400 most-rated items and 15,000 active users was selected to ensure computational efficiency.

### 2. Methodology
#### k-Nearest Neighbors (k-NN)
- Optimized for distance metrics (Cosine similarity, Pearson correlation) and neighbor count (1–100) using grid search.
- Despite achieving moderate RMSE and MSE values (~0.72), the k-NN struggled due to the sparsity of the rating matrix, often predicting global averages (e.g., 4.5).

#### Singular Value Decomposition (SVD)
- Used to factorize the sparse rating matrix into latent features representing user and item preferences.
- SVD improved the diversity of recommendations, providing better coverage across clusters.

### 3. Clustering and Recommendations
#### Clustering:
- Users were segmented based on cosine similarity and latent factors using k-means clustering.
- With SVD, clusters were more balanced and representative compared to k-NN, which grouped nearly all users into a single cluster.
#### Recommendations:
- Top-5 items were recommended for randomly chosen users, with SVD offering personalized suggestions compared to the repetitive outputs of k-NN.

### 4. Challenges and Future Directions
#### Challenges:
- Sparse data with >90% users rating only one item limited the performance of k-NN.
- Rating imbalance skewed predictions, favoring high ratings (4–5 stars).
#### Future Work:
- Combine sentiment analysis and natural language processing (NLP) on review text to enhance recommendations.
- Incorporate additional features like body type, category, and rental purpose for a hybrid recommendation approach.

## Conclusion
This project demonstrates the strengths and weaknesses of k-NN and SVD in building recommendation systems with sparse data. While SVD proved more robust, future improvements could explore advanced machine learning models and feature-rich algorithms to enhance performance.
