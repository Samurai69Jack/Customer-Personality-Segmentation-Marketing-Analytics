# Customer-Personality-Segmentation-Marketing-Analytics

## 📌 Project Overview

This project analyzes a Customer Personality Assessment dataset to understand customer behavior, spending patterns, and campaign responsiveness.
The goal is to clean the data, perform exploratory data analysis (EDA), segment customers using clustering algorithms, and derive actionable marketing insights.

The project demonstrates end-to-end data science workflow including data cleaning, feature engineering, visualization, clustering, and model evaluation.

## 📂 Dataset Description

The dataset contains demographic, behavioral, and campaign-related information for customers, including:

Demographics: Age, Education, Marital Status, Income, Family Structure

Spending Behavior: Wines, Meat, Fruits, Fish, Sweets, Gold products

Marketing Campaign Responses

Customer Tenure and Purchase History

## ⚙️ Tools & Technologies Used

Python (Pandas, NumPy, Scikit-learn)

Data Visualization: Matplotlib, Seaborn

Machine Learning: KMeans, PCA, Silhouette Score, Adjusted Rand Index

Jupyter Notebook


## 🧹 Data Cleaning & Feature Engineering

Key preprocessing steps:

Parsed date fields and created Customer Tenure

Created Age, Family Size, and Has Children features

Engineered Total Spending across product categories

Handled missing values (median imputation for Income)

Removed extreme outliers using quantile filtering

Encoded categorical variables using one-hot encoding


## 📈 Exploratory Data Analysis (EDA)
Key EDA Findings:

Income strongly correlates with total spending

Wines and meat products are the highest revenue-generating categories

Middle-aged customers tend to spend more

Larger families show higher spending on food categories

Campaign responders generally have higher income and spending

Customer tenure positively influences loyalty and purchase behavior


## 🤖 Customer Segmentation (Clustering)
🔹 Feature Selection for Clustering

Age

Income

Total Spending

Family Size

Customer Tenure

🔹 Scaling Techniques Compared

StandardScaler

MinMaxScaler

🔹 KMeans Clustering

Optimal clusters identified using Elbow Method and Silhouette Score

Customers segmented into 4 behavioral clusters

PCA used for 2D visualization of clusters

## 📊 Cluster Personas Identified

Cluster 0->	Luxury Buyers=>	        High income, high spending, strong campaign response.
Cluster 1->	Family Shoppers=>	      Medium income, large family size, high food spending.
Cluster 2->	Budget Customers=>	    Low income, low spending, low campaign engagement.
Cluster 3->	Young Spenders=>        Younger customers with moderate spending patterns.


## 🔬 Clustering Robustness Evaluation

To test segmentation stability, clustering results under different scaling methods were compared using Adjusted Rand Index (ARI): 0.45


## Interpretation:

Moderate agreement between scaling methods

Scaling significantly influences customer segmentation boundaries

Core customer groups remain consistent across scaling assumptions

This highlights the importance of feature normalization in distance-based clustering models.



## 📉 PCA Visualization

Principal Component Analysis (PCA) was applied to visualize high-dimensional customer data in 2D, revealing clearly separable customer segments.




## 💡 Business Insights & Recommendations

Target Luxury Buyers with premium campaigns and loyalty programs

Family Shoppers respond well to bundled discounts and grocery promotions

Budget Customers are price-sensitive and require discount-driven marketing

Young Moderate Spenders are ideal candidates for cross-selling and upselling

Campaign responders represent high-value customers and should be prioritized
