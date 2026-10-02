# Phase 2 — Literature and Data Research

## 1. Dataset Selection

### Selected Dataset

The primary dataset selected for this project is the DataCo SMART Supply Chain dataset, commonly distributed as the "DataCo Smart Supply Chain for Big Data Analysis" dataset.

The dataset is suitable for the proposed logistics analytics project because it contains order-level/item-level information covering multiple dimensions of supply-chain operations, including order characteristics, shipping information, customer information, product categories, geographical attributes, sales, and profitability.

The dataset contains approximately 180,519 order-item records and 53 original variables. It provides sufficient information to investigate shipment performance, identify operational patterns, calculate logistics KPIs, and develop predictive analytics models.

The dataset has been used in published research for supply-chain prediction, shipment-delay analysis, customer segmentation, and related logistics analytics applications.

## 2. Data Granularity

The dataset is primarily structured at the order-item level rather than representing one unique row for every customer order.

Therefore, the 180,519 records should not automatically be interpreted as 180,519 unique orders. Order identifiers and order-item identifiers must be examined during data understanding to distinguish individual orders from their associated line items.

Understanding the data grain is important because KPI calculations, aggregation, and machine-learning sampling can produce misleading results if order-item records are incorrectly treated as independent orders.

## 3. Relevant Data Domains

The dataset contains information from several domains relevant to logistics analytics:

### Order Information
- Order identifiers
- Order dates
- Order status
- Order quantities

### Shipping Information
- Shipping mode
- Scheduled shipping duration
- Actual shipping duration
- Shipping status

### Customer Information
- Customer segment
- Customer location
- Customer market/region

### Product Information
- Product category
- Product name
- Product price
- Product quantity

### Financial Information
- Sales
- Profit/benefit
- Order value
- Customer-level sales information

### Geographic Information
- Customer city
- Customer state
- Customer country
- Market and regional information

## 4. Candidate Target Variable

The initial candidate target variable for predictive modelling is `Late_delivery_risk`.

The project will treat this variable as an outcome label rather than as an input feature. Before modelling, all candidate predictors will be evaluated according to their information availability at the intended prediction time.

This point is particularly important because variables representing realized shipping outcomes can introduce target leakage. A leakage-aware feature selection process will therefore be performed before model training.

## 5. Critical Dataset Limitation

A major methodological limitation is that the dataset does not contain a conventional last-mile delivery date.

Recent research on the DataCo dataset identifies the shipping date as a dispatch-related timestamp and distinguishes shipment/dispatch delay from actual last-mile delivery delay.

Therefore, this project will avoid automatically referring to the target as "customer delivery delay." Instead, the analysis will carefully distinguish between shipment/dispatch performance and actual delivery performance.

This distinction will be maintained throughout the analysis, modelling, interpretation, and final report.

## 6. Dataset Suitability

The DataCo SMART Supply Chain dataset was selected because it provides:

1. A relatively large number of observations for exploratory and predictive analysis.
2. Multiple operational, financial, product, customer, and geographical variables.
3. Shipping-related variables directly relevant to the project.
4. A binary shipment-delay outcome suitable for classification.
5. Sufficient categorical and numerical variables for feature engineering.
6. A public research benchmark that supports reproducibility and comparison with previous studies.
7. Opportunities to apply multiple data-science techniques, including descriptive analytics, statistical analysis, classification, clustering, and feature interpretation.