# Milestone 2: Olist Order Analysis

Gautham G Shenoy | 4SF25CI054_3A

## Overview and dataset
Exploratory data analysis and feature engineering on [Olist's Brazilian e-commerce dataset](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce). The orders CSV has 99,441 rows and 8 columns; each row is an order. It records anonymized order/customer IDs, order status, and purchase, approval, carrier, delivery and estimated-delivery timestamps. The historical data runs from 2016 to 2018. Source license: CC BY-NC-SA 4.0.

## Method
Pandas is used to inspect dimensions, types, memory, missing values, duplicates and statuses. Dates are converted to datetime; missing delivery values are retained rather than treated as zero. No exact duplicate rows or duplicate order IDs were found. There are 160 missing approval timestamps, 1,783 missing carrier timestamps and 2,965 missing customer delivery dates. The 166 negative carrier handoff intervals are set to missing; plausible long deliveries are retained. IQR is used to flag outliers. Histograms, boxplots, bar charts, monthly trends and a correlation heatmap show distributions and relationships. The cleaned data has 99,441 rows and 20 columns.

## Findings
1. 96,478 orders have delivered status.
2. Monday has the most orders: 16,196.
3. The busiest purchase hour is 16:00.
4. Weekend orders account for 22.98% of the dataset.
5. November 2017 has the highest monthly count.
6. Median observed delivery time is 10.22 days.
7. Mean observed delivery time is 12.56 days, suggesting a longer upper tail.
8. Among 96,476 orders with known delivery and estimate, 8.11% were late.
9. Median approval time is 0.34 hours.
10. The IQR upper threshold is 29.15 days; 4,899 delivery durations exceed it.
11. Afternoon is the most common purchase period, with 38,361 orders.
12. Mean estimated time is 23.77 days. The estimate and observed delivery averages cover different populations when delivery dates are missing.

## Features
- Purchase year, month, weekday, hour, weekend and time-of-day group reveal seasonal and daily patterns.
- Approval hours and carrier handoff days measure processing stages.
- Delivery days and estimated days describe actual and promised durations.
- Delay days compare actual and estimated dates; the late flag identifies deliveries after the estimate.

Approval, carrier and delivery features use information observed after purchase and must be excluded from models predicting at purchase time to prevent leakage. Estimated delivery may be used only if known at prediction time. Findings describe historical orders from one marketplace and are not causal claims.

## Running the notebook
Install pandas, numpy, matplotlib and seaborn. In Databricks, run the seaborn installation cell before the analysis cells. Run the data-loading cell followed by the analysis cell. The notebook reads an attributed public mirror of the original data and generates a processed CSV in its working directory. The source CSV is included for review. Charts and statistics are produced when the cells run.
