## Customer Segmentation & Clustering (K-Means)

Segmenting mall customers into behavioral groups using K-Means clustering on demographic and spending data, to support targeted marketing and personalization.

## Overview

This project uses the Mall Customers dataset (200 records) to explore customer behavior and group customers into clusters based on:

Annual Income vs Spending Score
Age vs Spending Score


The optimal number of clusters for each was chosen using the Elbow Method, and results were visualized with centroid-labeled scatter plots. A simple Streamlit app demonstrates predicting a customer's segment from new input.

## Dataset

ColumnDescriptionCustomerIDUnique customer identifierGenderMale / FemaleAgeCustomer ageAnnual Income (k$)Yearly income in $1,000sSpending Score (1-100)Mall-assigned spending behavior score


200 rows, no missing values
Gender split: 56% Female / 44% Male


## Exploratory Data Analysis


Age is right-skewed toward younger adults; Spending Score is close to uniform across its range.
Gender has little effect on income or spending — medians are nearly identical between Male and Female.
Correlation heatmap shows Income vs Spending Score has ~0 linear correlation (0.0099) — meaning income doesn't predict spending in a straight-line sense, which is exactly why clustering (not regression) is the right approach here.
Age vs Spending Score has a weak negative correlation (-0.33): older customers trend slightly lower in spending.

## Clustering Results

Annual Income vs Spending Score (5 clusters)

Chosen via the elbow method (clear bend at k=5):


ClusterProfileLabel0Mid income, mid spendingStandard1High income, high spendingPremium / Target2Low income, high spendingImpulsive3High income, low spendingFrugal4Low income, low spendingBudget-conscious

Age vs Spending Score (4 clusters)

Chosen via the elbow method (clear bend at k=4):


ClusterProfileLabel0Older, moderate spenders~55 yrs, mid spend1Younger, high spenders~30 yrs, high spend2Middle-aged, low spenders~43 yrs, low spend3Younger, moderate spenders~28 yrs, mid spend

## Project Structure

customer-segmentation-clustering/
├── README.md
├── Customer_Segmentation_Clustering.ipynb
├── app.py
├── data/
│   └── Mall_Customers.csv
└── images/

## Next Steps
- Apply feature scaling before clustering
- Validate cluster quality with silhouette score
- Try clustering on all three features (Age, Income, Spending) together

Apply feature scaling before clustering
Validate cluster quality with silhouette score
Try clustering on all three features (Age, Income, Spending) together
