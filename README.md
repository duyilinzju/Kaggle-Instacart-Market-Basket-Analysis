Instacart Market Basket Analysis

Solution to the Kaggle Competition: Instacart Market Basket Analysis 

Dataset:
The dataset is an open-source dataset provided by Instacart 

This anonymized dataset contains a sample of over 3 million grocery orders from more than 200,000 Instacart users. For each user, we provide between 4 and 100 of their orders, with the sequence of products purchased in each order. 

Problem Statement:
Use the anonymized data on customer orders over time to predict which previous purchased products will be in a user’s next order. The task can be formulated as a binary prediction: given a user, a product(this product has been purchased by the user in the previous orders) and the user’s prior purchase history, predict whether or not the given product will be reordered in the user’s next order. The output format will be: user’s last order id and a list of products that will be reordered. 

Evaluation Matric:
F1 score between the set of predicted reordered products and the set of true reordered products

The Approach:
Exploratory Data Analysis: Further explore the dataset to see if we have any missing data or outliers in the orders and user dataset.
Sampling: It’s a huge dataset and the memory may be an issue when running the machine learning model. I sampled 20% of the training set for machine learning model. 
Feature Engineering: feature engineering is the key in the competition. User-related, order-related, product-related features are extracted from the dataset. Other more complicated features like user-product interaction features and NLP are applied to generate new features as well.
Machine Learning Model: I build a user-product machine learning model and apply logic regression to output the re-order probability for each product.  There are many features involved in the model, popular tree-based models like xgboost and lightgbm are used.
F1-optimization: The output of the machine learning model is a list of products the user purchased and the re-order probability for each product. I apply an algorithm to maximize the f1 score for the product list selected given their probabilities to be re-ordered.
Model Stacking: It’s a kaggle open competition and some kagglers will share their model and predictions in the forum. In the final stage, I use some stacking technologies to combine my model and other well-performed shared model results for final submission. 

Results:
Ranked 230/2630 (top 9%)

Requirements:
8 GB RAM, Python 3.4

Python packages:

numpy == 1.12.1
pandas == 0.20.2
xgboost == 0.6
scikit-learn == 0.12.2
gensim == 2.2.0

