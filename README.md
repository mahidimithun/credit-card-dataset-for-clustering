
# Credit Card Customer Segmentation using K-Means Clustering

## Project Overview

This project applies **Unsupervised Machine Learning** to segment credit card customers based on their spending behavior. Customer segmentation helps financial institutions understand different types of customers and design personalized marketing campaigns, credit policies, and promotional offers.

Since the dataset does not contain any target variable, **K-Means Clustering** is used to discover hidden customer groups based on purchasing patterns, credit usage, and payment behavior.

---

## Problem Statement

Banks have thousands of customers with different spending habits. Treating every customer the same is not an effective marketing strategy.

The objective of this project is to:

- Identify groups of similar customers
- Analyze each customer segment
- Provide business recommendations for each segment

---

## Dataset

**Dataset:** Credit Card Dataset for Clustering

Source:
https://www.kaggle.com/datasets/arjunbhasin2013/ccdata

The dataset contains approximately **8,950 customers** and **18 behavioral features** collected over the previous six months.

### Features

| Feature | Description |
|----------|-------------|
| BALANCE | Remaining account balance |
| BALANCE_FREQUENCY | Frequency of balance updates |
| PURCHASES | Total purchase amount |
| ONEOFF_PURCHASES | Largest one-time purchase |
| INSTALLMENTS_PURCHASES | Installment purchases |
| CASH_ADVANCE | Cash advances taken |
| PURCHASES_FREQUENCY | Purchase frequency |
| ONEOFF_PURCHASES_FREQUENCY | One-time purchase frequency |
| PURCHASES_INSTALLMENTS_FREQUENCY | Installment purchase frequency |
| CASH_ADVANCE_FREQUENCY | Cash advance frequency |
| CASH_ADVANCE_TRX | Cash advance transactions |
| PURCHASES_TRX | Purchase transactions |
| CREDIT_LIMIT | Credit limit |
| PAYMENTS | Total payments |
| MINIMUM_PAYMENTS | Minimum payments |
| PRC_FULL_PAYMENT | Percentage of full payments |
| TENURE | Card tenure |

---

# Machine Learning Workflow

## 1. Import Libraries

Imported the required Python libraries for:

- Data manipulation
- Data visualization
- Data preprocessing
- Clustering
- Model evaluation

Libraries used:

- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-Learn

---

## 2. Load Dataset

Loaded the dataset using Pandas and explored its structure.

Performed:

- View first rows
- Check shape
- Data types
- Summary statistics

---

## 3. Data Cleaning

### Remove Customer ID

`CUST_ID` is a unique identifier and does not contribute to clustering, so it was removed.

### Handle Missing Values

Missing values were found in:

- CREDIT_LIMIT
- MINIMUM_PAYMENTS

These values were replaced using the **median** because financial data usually contains outliers and right-skewed distributions. Median is more robust than the mean in such cases.

---

## 4. Exploratory Data Analysis (EDA)

Performed exploratory analysis to understand customer behavior.

Visualizations include:

- Histograms
- Correlation Heatmap
- Distribution plots

The analysis helped identify skewed features and relationships among variables.

<img width="602" height="473" alt="heatmap" src="https://github.com/user-attachments/assets/f538cec8-4551-4d85-9275-df357ffb2481" />

---

## 5. Feature Scaling

Since K-Means uses **Euclidean Distance**, all features were standardized using **StandardScaler**.

Without scaling, variables with large values (such as BALANCE or PURCHASES) would dominate the clustering process.

---

## 6. Choosing the Optimal Number of Clusters

Two evaluation methods were used.

### Elbow Method

The Elbow Method measures **Within Cluster Sum of Squares (WCSS)**.

The objective is to find the point where increasing the number of clusters no longer significantly reduces WCSS.

<img width="652" height="422" alt="elbow" src="https://github.com/user-attachments/assets/57067921-8a6f-4c6b-9c77-582afa61f041" />

### Silhouette Score

Silhouette Score evaluates cluster quality by measuring:

- Cohesion (how close data points are within the same cluster)
- Separation (how different clusters are from one another)

The K value with the highest silhouette score was selected.

---

## 7. K-Means Clustering

After selecting the optimal number of clusters, the K-Means algorithm was trained.

Each customer was assigned to a cluster representing a unique customer segment.

---

## 8. Cluster Visualization

Principal Component Analysis (PCA) was used to reduce the high-dimensional data into two dimensions.

This makes it possible to visualize customer clusters on a 2D scatter plot.

<img width="758" height="491" alt="segmentation " src="https://github.com/user-attachments/assets/66fec519-a66f-4fe8-8870-b24ec887661a" />

---

## 9. Cluster Analysis

The average value of each feature was calculated for every cluster.

This helps understand the characteristics of each customer segment.

Example:

- High spenders
- Low activity customers
- Installment users
- Cash advance users

<img width="922" height="605" alt="avg_values_by_cluster" src="https://github.com/user-attachments/assets/47a8603b-21e3-4be8-a6e4-5598b3190ba3" />

---

## Business Insights

Customer segmentation enables banks to create targeted marketing strategies.

Examples:

- Offer premium cards to high-value customers.
- Provide cashback offers to low-activity customers.
- Promote installment plans to installment users.
- Reduce cash advance dependency through financial awareness campaigns.

---

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-Learn
- Jupyter Notebook

---

## Project Structure

```
Credit-Card-Clustering/
│
├── dataset/
│   └── CC GENERAL.csv
│
├── notebook/
│   └── credit_card_clustering.ipynb
│
├── images/
│   ├── elbow_method.png
│   ├── silhouette_score.png
│   ├── pca_clusters.png
│   └── heatmap.png
│
├── README.md
│
└── requirements.txt
```

---

## Results

- Cleaned missing values
- Standardized numerical features
- Determined the optimal number of clusters
- Built a K-Means clustering model
- Visualized customer groups using PCA
- Generated meaningful customer segments for business decision-making

---

## Future Improvements

- Compare K-Means with Hierarchical Clustering
- Try DBSCAN clustering
- Detect and remove outliers before clustering
- Use PCA before clustering for dimensionality reduction
- Build an interactive dashboard using Power BI or Streamlit

---

## Author

Mahidi Hasan Mithun

Computer Science & Engineering Graduate
