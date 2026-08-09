# Credit Card Customer Segmentation Using K-Means Clustering

## Project Overview

This project uses Python and K-Means clustering to segment credit card customers based on account activity, credit usage, and transaction behavior.

The goal was to identify meaningful customer groups, understand the characteristics that distinguish them, and develop business recommendations that could support more targeted customer engagement strategies.

The analysis includes data validation, feature selection, feature standardization, cluster evaluation, customer profiling, post-clustering analysis, and data visualization.

---

## Business Problem

Credit card customers can have similar levels of transaction activity while using their available credit in very different ways.

Understanding these differences can help financial institutions identify meaningful customer groups and develop more targeted engagement strategies.

This project explores whether customers can be segmented based on their financial and behavioral characteristics and identifies the key features that distinguish those segments.

---

## Tools & Libraries

- Python
- Jupyter Notebook
- Pandas
- NumPy
- Matplotlib
- Seaborn
- scikit-learn

---

## Project Workflow

1. Explored the dataset and reviewed customer, account, credit, and transaction features.
2. Validated data quality, including investigating negative `Avg_Open_To_Buy` values.
3. Selected relevant behavioral and financial features for customer segmentation.
4. Encoded categorical variables and standardized numerical features.
5. Evaluated K-Means models using inertia and silhouette scores.
6. Identified limitations in the initial clustering model and refined the feature set.
7. Compared multiple cluster solutions and selected a final three-cluster model.
8. Profiled and named the resulting customer segments.
9. Compared the segments across attrition, income category, and card category.
10. Developed visualizations, insights, and potential business recommendations.

---

## Model Development

### Initial Model

The initial clustering model included one-hot encoded Income Category variables.

Although the initial model produced a seven-cluster solution, analysis of the cluster centers showed that the clusters were driven primarily by individual income categories rather than broader differences in customer behavior.

Income groups also showed relatively similar characteristics across several behavioral measures.

As a result, Income Category was removed from the final clustering feature set and retained instead for post-clustering customer profiling.

### Refined Model

After removing Income Category, the clustering process was repeated and multiple values of `k` were evaluated.

The two-cluster solution achieved the highest silhouette score, but primarily created a broad high-versus-low utilization split. A three-cluster solution provided an additional interpretable credit behavior profile while maintaining a relatively simple segmentation.

The final model therefore uses **three customer segments**.

---

## Final Customer Segments

### 1. Low Utilization Customers

- Approximately **4,565 customers**
- Average credit limit of approximately **$17,554**
- Average revolving balance of approximately **$584**
- Average credit utilization of approximately **5%**

These customers have moderate credit capacity but carry relatively little revolving credit.

### 2. High Utilization Customers

- Approximately **1,366 customers**
- Average credit limit of approximately **$4,354**
- Average revolving balance of approximately **$1,753**
- Average credit utilization of approximately **54%**

These customers use a substantially larger proportion of their available credit than the other customer segments.

### 3. High Credit Capacity Customers

- Approximately **4,069 customers**
- Average credit limit of approximately **$23,004**
- Average revolving balance of approximately **$1,797**
- Average credit utilization of approximately **9%**

These customers have substantially greater available credit while maintaining relatively low utilization.

---

## Key Insights

- Credit limit, revolving balance, available credit, and credit utilization were the strongest characteristics distinguishing the final customer segments.
- Transaction activity, customer age, relationship length, and several other account characteristics were relatively similar across the segments.
- Income Category was relatively evenly distributed across the final segments and did not meaningfully distinguish customer behavior.
- Card Category distributions were also similar across the three segments.
- Attrition rates ranged from approximately **14% to 16%** across the segments, suggesting that the identified credit behavior patterns were not strongly associated with customer attrition.
- The segmentation is therefore more useful for understanding differences in customer credit usage and capacity than for predicting attrition.

---

## Visualizations

### Customer Distribution by Segment

<img width="805" height="391" alt="Customer Distribution by Segment" src="https://github.com/user-attachments/assets/73632318-d74e-4913-9c4d-f1cb9fd92a25" />

### Average Credit Limit and Revolving Balance by Segment

<img width="805" height="469" alt="Average Credit Limit and Revolving Balance by Segment" src="https://github.com/user-attachments/assets/c7e73493-5b7d-48c8-aac3-9e11c1bbfbf2" />

### Average Credit Utilization by Segment

<img width="748" height="396" alt="Average Credit Utilization by Segment" src="https://github.com/user-attachments/assets/b7e0090f-7350-4bcd-a65e-5038b55c1f86" />

---

## Business Recommendations

### Low Utilization Customers
Explore relevant rewards, spending incentives, or personalized offers that could encourage greater card engagement among customers who currently use relatively little of their available credit.

### High Utilization Customers
Monitor utilization patterns and consider appropriate account-management communications or financial tools. Individual credit decisions should continue to follow normal eligibility and risk-assessment processes.

### High Credit Capacity Customers
Explore relevant rewards, card benefits, or other engagement opportunities suited to customers with substantial unused credit capacity.

---

## Limitations

- The final clustering solutions produced relatively low silhouette scores, indicating some overlap between customer groups.
- K-Means requires the number of clusters to be selected in advance and relies on distance-based similarity.
- The dataset represents customer characteristics at a particular point in time rather than changes in behavior over time.
- The identified segments should not be interpreted as measures of creditworthiness, financial risk, or customer financial health.
- Additional behavioral, product, risk, and longitudinal data could potentially improve the segmentation.

---

## Dataset

The dataset contains anonymized credit card customer information covering demographics, account characteristics, credit usage, transaction behavior, and customer attrition.

**License:** CC0: Public Domain

**Source:** [Credit Card Churn Dataset on Kaggle](https://www.kaggle.com/datasets/kunalgp/credit-card-churn)

---

## Repository Contents

- `credit_card_customer_segmentation.ipynb` – Complete Python analysis and K-Means clustering workflow
- `Credit_Card_Churn.csv` – Dataset used for the analysis

---

## Author

**Opeyemi Okunmuyide**
