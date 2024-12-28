# Next Basket Recommendation Using TIFU-KNN

This project implements a next basket recommendation system leveraging the TIFU-KNN algorithm. It is based on the dataset provided by the Instacart Market Basket Analysis competition and inspired by the methodology described in the paper [TIFU-KNN](https://arxiv.org/pdf/2006.00556).

---

## Overview

Next basket recommendation systems are vital in e-commerce and retail, helping predict the next set of items a user is likely to purchase based on their historical purchasing behavior. This project uses TIFU-KNN, an item-based collaborative filtering approach that adapts to the temporal evolution of user preferences.

---

## Dataset

- **Source**: [Instacart Market Basket Analysis](https://www.kaggle.com/competitions/instacart-market-basket-analysis)
- **Description**: The dataset contains millions of orders made by over 200,000 users. Each order comprises a list of products, along with metadata such as order time, sequence, and user-product interactions.
- **Features**:
  - User ID
  - Product ID
  - Order ID
  - Reorder status
  - Order sequence and timing
  - Product metadata (aisle, department)

---

## Original Paper: TIFU-KNN

### Summary

The TIFU-KNN algorithm introduces a **time-resilient, item-based collaborative filtering approach** for recommendation tasks. Unlike traditional KNN-based recommender systems, which often struggle with dynamic user preferences, TIFU-KNN incorporates temporal information to improve relevance.

#### Key Contributions:
1. **Temporal Decay**: Assigns higher importance to recent interactions, addressing the shift in user preferences over time.
2. **Localized Similarity**: Computes item similarity dynamically based on subsets of relevant historical data, avoiding biases from outdated interactions.
3. **Performance**: Demonstrates competitive accuracy compared to deep-learning-based methods, with significantly lower computational requirements.

#### Algorithm Highlights:
- **Similarity Measure**: Combines traditional item similarity metrics with a temporal decay function to ensure that recent interactions carry more weight.
- **Top-K Filtering**: Dynamically selects the top K most similar items based on the user's recent activity.
- **Scalability**: Efficiently handles large-scale datasets due to its simplicity and ability to work with sparse data matrices.

#### Results:
- Superior performance in datasets with strong temporal patterns.
- Lightweight computation, making it suitable for real-time recommendations.

---

## Implementation Details

### Steps:
1. **Data Preprocessing**:
   - Cleaning and transforming the Instacart dataset into user-item interaction matrices.
   - Incorporating temporal features such as order sequence and timestamps.

2. **Feature Engineering**:
   - Generating item similarity matrices based on user interaction data.
   - Applying temporal decay functions to recent interactions.

3. **Model Training**:
   - Building the TIFU-KNN model by computing K-nearest neighbors for each item.
   - Incorporating temporal adjustments in similarity calculations.

4. **Recommendation**:
   - Predicting the next basket of items for each user based on their recent purchase history and the TIFU-KNN model.

---

## References

1. Instacart Market Basket Analysis Dataset - [Kaggle](https://www.kaggle.com/competitions/instacart-market-basket-analysis)
2. TIFU-KNN - [ArXiv](https://arxiv.org/pdf/2006.00556)