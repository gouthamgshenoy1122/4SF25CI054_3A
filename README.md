# Milestone 2: Exploratory Data Analysis and Feature Engineering

Gautham G Shenoy | 4SF25CI054_3A

## Dataset
This project analyzes the orders table from [Olist’s Brazilian E-Commerce dataset](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce), licensed CC BY-NC-SA 4.0. It has 99,441 orders and eight original columns, including order status and timestamps.

## Method
The notebook checks dimensions, types, missing values, duplicates and outliers, and creates labeled univariate, bivariate and multivariate visualizations. It creates 12 features describing purchase time and order processing. Missing delivery information is retained; negative carrier handoff intervals are treated as missing. Features that depend on events after purchase must not be used to predict at purchase time.

## Findings
1. 96,478 orders have delivered status.
2. Monday has the most orders: 16,196.
3. The busiest purchase hour is 16:00.
4. Weekend orders account for 22.98% of orders.
5. November 2017 has the highest monthly count.
6. Median observed delivery time is 10.22 days.
7. Mean observed delivery time is 12.56 days.
8. Among 96,476 orders with known delivery and estimate, 8.11% were late.
9. Median approval time is 0.34 hours.
10. The delivery-duration IQR upper threshold is 29.15 days; 4,899 values exceed it.
11. Afternoon is the most common purchase period, with 38,361 orders.
12. Mean estimated delivery time is 23.77 days; actual and estimated averages cover different populations when delivery dates are missing.

## Running the notebook
Install pandas, numpy, matplotlib and seaborn. Keep olist_orders_dataset.csv in the same folder as Olist_EDA_Feature_Engineering.ipynb, open the notebook in Jupyter, and run its cells in order. It generates olist_orders_processed.csv. In Databricks, upload the CSV and adjust the path in the loading cell.
