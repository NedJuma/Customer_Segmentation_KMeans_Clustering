# 🛍️ Customer Segmentation using K-Means Clustering
# 📌 Project Overview

Understanding customer purchasing behavior is fundamental to developing effective marketing strategies and improving customer retention. In this project, I built an end-to-end Customer Segmentation solution using K-Means Clustering on transactional retail data. The objective was to identify groups of customers with similar purchasing behaviors and translate those insights into actionable business recommendations.

This project covers the complete machine learning lifecycle—from data cleaning and feature engineering to exploratory data analysis, model development, cluster evaluation, customer profiling, and marketing strategy recommendations.

# 🎯 Business Problem

Many businesses apply the same marketing strategy to every customer, regardless of their purchasing habits. This often results in:

- 💸 Inefficient marketing expenditure
- 📉 Poor customer retention
- 📧 Low campaign conversion rates
- 💰 Missed upselling and cross-selling opportunities

This project addresses this challenge by segmenting customers based on their purchasing behavior, enabling businesses to deliver personalized marketing campaigns that maximize customer value.

# 📂 Dataset

The project uses an Online Retail Dataset obtained from the UC Irvine Machine Learning Repository. The dataset contains transactional records for thousands of customers.
> Dataset link: https://archive.ics.uci.edu/dataset/352/online+retail

> Original Features
- InvoiceNo
- StockCode
- Description
- Quantity
- InvoiceDate
- UnitPrice
- CustomerID
- Country

Each row represents an individual product purchased within a customer invoice.

# 🧹 Data Cleaning & Preparation

Before modeling, extensive data cleaning was performed to ensure high-quality data.

> Cleaning Steps
- ✅ Removed duplicate transactions.
- ✅ Removed records with missing values.
- ✅ Removed cancelled invoices (Invoice Numbers beginning with "C").
- ✅ Removed original purchases associated with cancelled transactions to retain only completed sales.
- ✅ Removed transactions with non-positive quantities.
- ✅ Removed transactions with non-positive unit prices.
- ✅ Converted transactional data into customer-level observations suitable for clustering.

These steps ensured that the clustering model learned from genuine purchasing behavior.

# ⚙️ Feature Engineering

> Since K-Means clusters customers, not transactions - the dataset was aggregated at the customer level.
The following behavioral features were engineered:
> Feature	Description
- 💰 TotalSpent:	Total amount spent by each customer
- 🛒 Orders:	Number of unique orders placed
- 📦 ItemsPurchased:	Total quantity of items purchased
- 💳 AvgOrderValue:	Average amount spent per order
- 📅 Recency:	Number of days since the customer's last purchase

These engineered features summarize each customer's shopping behavior and form the basis of the clustering model.

# 📊 Exploratory Data Analysis (EDA)

Comprehensive exploratory analysis was conducted to understand customer behavior before modeling.

> Areas Explored
- 📈 Distribution of Total Spending
- 🛒 Distribution of Orders
- 📦 Distribution of Items Purchased
- 💳 Distribution of Average Order Value
- 📅 Distribution of Recency
- 🔗 Correlation Analysis
- 📉 Identification of skewed variables
- 🚨 Detection of purchasing outliers
> Key Findings
- Most customers spend relatively small amounts, while a few contribute exceptionally high revenue.
- Most customers place only one or two orders.
- Customer spending and purchasing quantities are highly right-skewed.
- TotalSpent and ItemsPurchased exhibit a strong positive correlation.
- Nearly all customers purchase from a single country.

These findings guided the preprocessing and feature transformation strategy.

# 🔄 Data Transformation

To improve clustering performance, I:

- ✅ Applied Log Transformation to reduce feature skewness.
- ✅ Applied StandardScaler to standardize the data into one scale.

These transformations produced more balanced customer clusters.

# 🤖 Model Development

Customer segmentation was performed using K-Means Clustering.

> Workflow
- Selected customer behavioral features.
- Applied Standard Scaling.
- Built K-Means models for multiple values of K.
> Evaluated models using:
- 📉 Elbow Method
![Elbow plot](/workspaces/Customer_Segmentation_KMeans_Clustering/images/inertia_errors.png)
- 📏 Silhouette Score
![Silhouette Scores](/workspaces/Customer_Segmentation_KMeans_Clustering/images/silhouette_scores.png)
> Compared cluster distributions.
> Selected the optimal number of customer segments.

After evaluating several models, 5 clusters were selected as the final solution, offering the best balance between clustering quality and business interpretability.

# 👥 Customer Segmentation

The final model identified five distinct customer segments.
### 📊 Cluster Analysis
![Average Total Spending](/workspaces/Customer_Segmentation_KMeans_Clustering/images/average_total_spending_by_clusters.png)
![Average Order Value](/workspaces/Customer_Segmentation_KMeans_Clustering/images/average_order_value_by_clusters.png)
![Average Recency](/workspaces/Customer_Segmentation_KMeans_Clustering/images/average_recency_by_clusters.png)
![Items Purchased](/workspaces/Customer_Segmentation_KMeans_Clustering/images/items_purchased_by_clusters.png)
![Average Orders](/workspaces/Customer_Segmentation_KMeans_Clustering/images/orders_by_clusters.png)
![Full Cluster Summary](/workspaces/Customer_Segmentation_KMeans_Clustering/images/full_cluster_summary.png)


#### 🏆 Cluster 0 — Premium / Bulk Buyers
> Characteristics
- 💰 High total spending
- 💳 Highest average order value
- 🛒 Moderate purchase frequency
- 📅 Moderately active customers
> Recommended Marketing Strategy
- Premium product recommendations
- Exclusive product collections
- Bulk purchase discounts
- Free shipping incentives
- Personalized offers
#### 😴 Cluster 1 — Dormant Low-Value Customers
> Characteristics
- 💸 Low spending
- 🛒 Few purchases
- 📦 Low purchasing volume
- 📅 Longest period since last purchase
> Recommended Marketing Strategy
- Win-back campaigns
- Discount vouchers
- Reminder emails
- Customer satisfaction surveys
- Limited-time promotions
#### ⭐ Cluster 2 — VIP Loyal Customers
> Characteristics
- 💰 Highest spending
- 🛒 Highest purchase frequency
- 📦 Highest purchasing volume
- 📅 Most recently active customers
> Recommended Marketing Strategy
- VIP membership
- Loyalty reward programs
- Early access to new products
- Personalized recommendations
- Premium customer support
#### 🤝 Cluster 3 — Regular Repeat Customers
> Characteristics
- 💰 Moderate spending
- 🛒 Moderate purchase frequency
- 📦 Moderate purchasing volume
- 📅 Active customers
> Recommended Marketing Strategy
- Cross-selling
- Upselling
- Product bundles
- Loyalty points
- Personalized recommendations
#### 🛍️ Cluster 4 — Occasional Budget Customers
> Characteristics
- 💸 Lowest spending
- 📦 Lowest purchasing volume
- 🛒 Infrequent purchases
- 📅 Becoming inactive
> Recommended Marketing Strategy
- Welcome-back promotions
- Seasonal discounts
- Affordable product recommendations
- First-repeat purchase incentives
# 🚀 Proposed Marketing Campaign Strategy

Rather than applying one marketing strategy to every customer, businesses can tailor campaigns according to each customer segment.
This targeted approach enables businesses to improve customer satisfaction while maximizing marketing effectiveness.

# 💼 Business Impact

> The insights generated from this project can help organizations:
- 🎯 Deliver personalized marketing campaigns
- ❤️ Improve customer retention
- 📈 Increase customer lifetime value
- 💰 Optimize marketing budgets
- 🛒 Increase cross-selling and upselling opportunities
- 🔍 Identify high-value customers
- ⚠️ Detect customers at risk of churn
- 📊 Support data-driven business decisions

Instead of treating every customer the same, businesses can focus the right marketing strategy on the right customer segment.

# 🛠️ Technologies Used
- 🐍 Python
- 🐼 Pandas
- 🔢 NumPy
- 📊 Plotly Express
- 🤖 Scikit-learn
- 📈 K-Means Clustering
- 📓 Jupyter Notebook

# 💡 Skills Demonstrated

> This project showcases practical experience in:

- 🧹 Data Cleaning
- ⚙️ Feature Engineering
- 📊 Exploratory Data Analysis (EDA)
- 🔄 Data Transformation
- 🤖 Unsupervised Machine Learning
- 🎯 Customer Segmentation
- 📏 Feature Scaling
- 📈 Model Evaluation
- 📉 Cluster Analysis
- 📊 Data Visualization
- 💼 Business Intelligence
- 📧 Marketing Analytics
- 📖 Business Storytelling
# 🔄 Project Workflow
🗂️ Raw Transaction Data
          │
          ▼
🧹 Data Cleaning & Preparation
          │
          ▼
⚙️ Feature Engineering
          │
          ▼
📊 Exploratory Data Analysis
          │
          ▼
🔄 Log Transformation
          │
          ▼
📏 Standard Scaling
          │
          ▼
🤖 K-Means Clustering
          │
          ▼
📉 Model Evaluation
(Elbow Method & Silhouette Score)
          │
          ▼
👥 Customer Segmentation
          │
          ▼
📊 Cluster Profiling and Analysis
          │
          ▼
📧 Marketing Strategy Recommendations

# 🔮 Future Improvements

> Potential extensions to this project include:

- 🔬 Compare K-Means with Hierarchical Clustering, DBSCAN, and Gaussian Mixture Models.
- 🤖 Automate customer assignment for newly acquired customers.
- 🔗 Integrate with a CRM platform for real-time customer segmentation.
- 🧪 Evaluate campaign effectiveness using A/B testing and marketing KPIs.

# 🎉 Conclusion

- This project demonstrates how unsupervised machine learning can transform raw transactional data into meaningful business insights. By engineering customer-level features, applying robust preprocessing techniques, and developing a K-Means clustering model, five distinct customer segments were identified—each with unique purchasing behaviors and tailored marketing recommendations.
- Beyond building a clustering model, this project bridges the gap between data science and business strategy. It illustrates how customer segmentation can drive personalized marketing, improve customer retention, optimize marketing investments, and support data-driven decision-making.
- This project highlights not only technical expertise in machine learning and data analytics but also the ability to translate data into actionable business value—an essential skill for modern Data Scientists and Machine Learning Engineers.