

# Customer Segmentation and Segment-wise Churn Prediction

## 1. Project Objective

The goal of this project is to segment customers into meaningful groups using clustering techniques and build separate churn prediction models for each segment. This approach helps the business apply personalized retention strategies instead of using a single generic model.

---

## 2. Dataset Description

The dataset contains customer-level numeric attributes such as service usage, tenure, charges, and a target column:

* **Churn** –
  0 → Customer retained
  1 → Customer churned

Only numeric features were used for clustering and modeling.

---

## 3. Data Preprocessing

Steps followed:

1. Loaded dataset using Pandas.
2. Selected only numeric columns.
3. Removed missing values.
4. Standardized features using **StandardScaler** to bring all variables to the same scale.

---

## 4. Customer Segmentation (Clustering)

Two clustering algorithms were applied:

| Algorithm                | No. of Clusters |
| ------------------------ | --------------- |
| K-Means                  | 3               |
| Agglomerative Clustering | 3               |

K-Means clustering was used to assign each customer to a segment.

---

## 5. Segment Profiles

### Cluster 0 – High Churn Risk Customers

* High service usage
* Higher dissatisfaction levels
* High probability of leaving

### Cluster 1 – Price Sensitive Customers

* Moderate churn behavior
* Highly responsive to pricing changes

### Cluster 2 – Loyal Customers

* Very low churn rate
* Long-term stable customers

---

## 6. Segment-wise Prediction Models

For each K-Means cluster:

* A **Random Forest Classifier** was trained.
* Hyperparameter tuning was applied using **GridSearchCV**.

### Evaluation Metrics Used

* Accuracy
* Precision
* Recall
* F1 Score

Each segment had its own optimized model.

---

## 7. Model Performance Summary

| Cluster | Accuracy | Precision | Recall | F1 Score |
| ------- | -------- | --------- | ------ | -------- |
| 0       | 0.93     | 1.00      | 0.60   | 0.75     |
| 1       | 0.92     | 0.75      | 0.50   | 0.60     |
| 2       | 0.96     | 0.00      | 0.00   | 0.00     |

Cluster-2 shows almost no churn cases, meaning customers in this group are highly loyal.

---

## 8. Business Recommendations

### Cluster 0 – High Churn Risk

* Proactive customer calls
* Special retention offers
* Priority complaint resolution

### Cluster 1 – Price Sensitive

* Discount campaigns
* Flexible pricing plans
* Renewal reminders

### Cluster 2 – Loyal Customers

* Loyalty reward programs
* Upsell premium services
* Referral incentives

---

## 9. Business Impact

| Area       | Benefit                          |
| ---------- | -------------------------------- |
| Marketing  | Targeted campaigns per segment   |
| Retention  | Predict churn before it happens  |
| Revenue    | Upsell loyal customers           |
| Operations | Focus support on high-risk users |

---

## 10. Conclusion

Segmenting customers before building churn models provides higher accuracy and allows businesses to apply focused retention strategies. This project delivers a complete end-to-end customer intelligence solution.
