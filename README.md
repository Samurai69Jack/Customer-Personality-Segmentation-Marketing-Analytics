# Customer Personality Segmentation & Marketing Analytics


### Segmenting 2,240 customers into 4 behavioural clusters using KMeans and PCA to enable targeted, data-driven marketing.




## What This Project Does:-

Every business has different types of customers — some spend big, some hunt for deals, some buy in bulk for their families. This project uses machine learning to automatically group customers based on how they actually behave, not just how we assume they behave.

Instead of sending the same promotion to every customer, a business can now:


1.Send premium product launches → only to Luxury Buyers
2.Send bundle offers → only to Family Shoppers
3.Send flash sale alerts → only to Budget Customers
4.Send new product recommendations → only to Young Spenders


This means less money wasted on marketing and more revenue from customers who are actually likely to buy.

Biggest surprise from the data: Income alone does NOT predict how much someone spends. Family size, customer tenure, and past campaign response are just as important — sometimes more so.


## Project Overview

This project covers an end-to-end data science workflow:


Data cleaning and feature engineering
Exploratory Data Analysis (EDA)
Customer segmentation using KMeans clustering
Cluster validation and robustness testing
PCA-based visualisation
Business insight generation and marketing recommendations



## Dataset Description

Source: Kaggle — Customer Personality Analysis
Size: 2,240 customers · 29 features

The dataset contains demographic, behavioural, and campaign-related information:

CategoryFeaturesDemographicsAge, Education, Marital Status, Income, Family StructureSpending BehaviourWines, Meat, Fruits, Fish, Sweets, Gold productsCampaign DataResponses to 5 marketing campaignsPurchase HistoryWeb, store, and catalogue purchasesCustomer TenureDate of joining, derived tenure in years


## Tools & Technologies

ToolPurposePython (Pandas, NumPy)Data manipulation and feature engineeringScikit-learnKMeans, PCA, StandardScaler, MinMaxScaler, Silhouette Score, ARIMatplotlib, SeabornVisualisation and EDAJupyter NotebookDevelopment environment


## Data Cleaning & Feature Engineering

Key preprocessing steps applied before modelling:


Parsed date fields and derived Customer Tenure (years since joining)
Engineered Age, Family Size, and Has Children features
Created Total Spending by summing across all product categories
Handled missing values via median imputation for Income
Removed extreme outliers using quantile-based filtering
Encoded categorical variables using one-hot encoding



## Exploratory Data Analysis (EDA)

Key findings from EDA:


Income strongly correlates with total spending (r ≈ 0.58), but is not the sole predictor
Wines and Meat are the highest revenue-generating product categories
Middle-aged customers (40–60) tend to spend significantly more than other age groups
Larger families show higher spending on food-related categories
Campaign responders generally have higher income and spending than non-responders
Customer tenure positively influences loyalty and total purchase volume



## Customer Segmentation

Feature Selection

The following features were used for clustering:


Age
Income
Total Spending
Family Size
Customer Tenure


## Scaling Comparison

Both StandardScaler and MinMaxScaler were applied and compared to understand how normalisation affects cluster boundaries.

## KMeans Clustering


Optimal number of clusters determined using the Elbow Method (WCSS) and Silhouette Score
Final model: K = 4 clusters, Silhouette Score ≈ 0.43
PCA applied to reduce dimensionality for 2D cluster visualisation



## Cluster Personas

ClusterLabelProfileRevenue Share0Luxury BuyersHigh income, high spending, strong campaign response~38%1Family ShoppersMedium income, large family, heavy food spending~29%2Budget CustomersLow income, low spending, low campaign engagement~20%3Young SpendersYounger demographic, moderate spend, web-first buyers~13%


## Clustering Robustness Evaluation

To test segmentation stability across different preprocessing assumptions, clustering results under StandardScaler and MinMaxScaler were compared using Adjusted Rand Index (ARI).

ARI Score: 0.45

InterpretationDetailAgreement levelModerate agreement between scaling methodsScaling effectScaling significantly influences segment boundariesCore consistencyCore customer groups remain consistent across assumptions

This confirms that while exact boundaries shift with scaling, the fundamental segment structure is stable — validating the model's real-world reliability. It also highlights the importance of feature normalisation in distance-based clustering algorithms like KMeans.


## PCA Visualisation

Principal Component Analysis (PCA) was applied to compress the high-dimensional feature space into 2 principal components, retaining ~75% of explained variance. The resulting 2D plot shows clearly separable customer clusters, confirming that the identified segments are meaningfully distinct and not arbitrary.


## Business Insights & Recommendations

What the data says:


Income alone does not determine spending behaviour — family size, tenure, and campaign history matter equally
The top cluster (Luxury Buyers) generates 38% of revenue from a small share of customers — a retention risk worth managing
Young Spenders have the highest growth potential as their income rises with age


What to do about it:


Luxury Buyers — invest in relationship management; losing even 10% of this group has a disproportionate revenue impact. Offer exclusives, early access, and loyalty perks.
Family Shoppers — they already trust the brand. Introduce complementary products via bundles. High-volume, low-friction upsells work well here.
Budget Customers — use discount campaigns sparingly. Over-reliance on discounts trains them to never pay full price. Reserve offers for re-engagement, not routine communication.
Young Spenders — prioritise early loyalty. Cross-sell new products and build brand affinity now, while their spending capacity is still growing.
Campaign Responders (across clusters) — this subset cuts across all segments and consistently shows higher income and spend. Prioritise them in any campaign rollout regardless of cluster.



Key Technical Takeaway


Multivariate clustering reveals what simple income-band bucketing cannot — that customer behaviour is shaped by a combination of demographics, spending history, and engagement patterns. A model that accounts for all of these simultaneously produces segments that are both statistically valid and practically actionable.
