
# Customer Segmentation & Lifetime Value (CLV) Prediction:

Note: This notebook is designed strictly for educational purposes to demonstrate the practical application of machine learning algorithms, specifically K-Means clustering and XGBoost regression, in a business context.

## 1. The Dataset:
This project analyzes real-world e-commerce transactional data to identify customer behavior patterns and predict future revenue.

[Source & Copyright Reference: Kaggle - Retail Customer Segmentation Analysis](https://www.kaggle.com/datasets/thedevastator/retail-customer-segmentation-analysis-using-cust)

## 2. Methodology & Pipeline:
The code executes an end-to-end data science pipeline divided into four distinct phases:

### Phase 1 | Data Cleaning:
Filtering out returns, cancellations, and missing Customer IDs to create a clean, mathematically sound baseline of 354,321 valid transactions.

### Phase 2 | RFM Engineering:
Grouping the raw data to calculate Recency (days since last purchase), Frequency (total unique invoices), and Monetary value (total historical spend) for each customer.

### Phase 3 | Behavioral Clustering:
Applying the K-Means algorithm to group customers into behavioral cohorts. The optimal number of clusters is verified mathematically using the Silhouette Score.

### Phase 4 | CLV Forecasting:
Splitting the timeline to prevent data leakage, and training an XGBoost Regressor to predict how much a customer will spend in the future based entirely on their historical RFM profile.

## 3. Key Results:

### Segmentation Findings:
The K-Means model identified 2 optimal clusters within the historical window:

* Low-Value Shoppers: 3,007 customers

* At-Risk / Sleepers: 28 high-variance customers

### Forecasting Accuracy:
The XGBoost model successfully captured a positive signal for future spending:

* R-squared (R²):0.3967 (explaining roughly 40% of the variance in future spending).

* Root Mean Squared Error (RMSE): $616.12

### Business Insights (Feature Importance):
When predicting future lifetime value, a customer's historical Monetary spend was the dominant predictive factor (77.2% importance), heavily outweighing both Recency (13.5%) and Frequency (9.3%).
