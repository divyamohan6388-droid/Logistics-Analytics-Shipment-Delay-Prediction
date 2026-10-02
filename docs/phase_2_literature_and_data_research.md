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

## 7. Literature Review

### 7.1 Shipment-Delay Prediction

Recent research has demonstrated the application of machine-learning techniques to supply-chain shipment-delay prediction using transactional logistics data. One recent study applied Logistic Regression, Decision Trees, Random Forest, XGBoost, and LightGBM to the DataCo SMART Supply Chain dataset and evaluated their predictive performance using classification metrics and feature-importance analysis.

This demonstrates that supervised machine learning can be used to identify patterns associated with shipment-delay outcomes. However, predictive performance alone is insufficient for a logistics analytics system because operational decisions require an understanding of the underlying business patterns and relevant performance indicators.

### 7.2 Leakage-Aware Predictive Analytics

A recent 2026 study specifically investigated leakage-aware prediction of shipment delays using the DataCo dataset. The study performed a point-in-time audit of candidate predictors and demonstrated that post-outcome variables can substantially inflate apparent model performance.

The study reported that the dataset's `Late_delivery_risk` variable represents shipment/dispatch delay rather than true last-mile delivery delay. It therefore emphasizes the importance of identifying which variables would genuinely be available at the time a prediction is intended to be made.

This finding will directly inform the methodology of the present project. Candidate features will be evaluated according to their temporal availability before predictive modelling is performed.

### 7.3 Data-Driven Supply Chain Optimization

Recent research has also demonstrated broader applications of the DataCo dataset beyond binary delay prediction. These include predictive modelling, customer segmentation, and supply-chain decision support. In particular, clustering techniques such as K-Means can be used to identify groups with different behavioural or operational characteristics.

This supports the use of multiple analytical techniques in the proposed project rather than relying exclusively on a single predictive model.

### 7.4 Research Methodological Considerations

The literature indicates several important methodological considerations for supply-chain analytics:

1. Predictive models should use information that would realistically be available at prediction time.
2. Post-outcome variables should be investigated for potential data leakage.
3. Model performance should be evaluated using multiple appropriate metrics rather than accuracy alone.
4. Predictive results should be interpreted in a business and operational context.
5. The grain of the dataset should be understood before calculating KPIs or constructing models.
6. Shipment-delay terminology should accurately reflect what the underlying data measures.

## 8. Research Gap and Project Positioning

Existing studies and projects demonstrate that the DataCo SMART Supply Chain dataset can support shipment-delay prediction, classification, customer segmentation, and supply-chain performance analysis.

However, predictive modelling alone does not provide a complete logistics analytics workflow. A practical analytics pipeline should connect operational KPIs, exploratory and diagnostic analysis, statistical investigation, predictive modelling, segmentation, and business-oriented decision support.

Therefore, this project is positioned as an integrated logistics analytics pipeline rather than a standalone machine-learning classifier.

The project will emphasize:

- systematic KPI-based performance measurement;
- exploratory and diagnostic analysis of logistics operations;
- statistical investigation of factors associated with shipment delays;
- leakage-aware predictive modelling;
- customer or operational segmentation where supported by the data;
- model interpretation and business translation;
- reproducibility through Python-based analysis and version-controlled development.

The objective is not to reproduce previous studies, but to develop an independent analytical workflow and derive project-specific findings from the publicly available dataset.

## 9. Data Source Record

| Attribute | Description |
|---|---|
| Dataset | DataCo SMART Supply Chain Dataset |
| Domain | Logistics and Supply Chain Analytics |
| Approximate Records | 180,519 |
| Original Variables | 53 |
| Data Granularity | Order-item level |
| Primary Analytical Outcome | `Late_delivery_risk` |
| Major Domains | Orders, shipping, customers, products, geography, sales and profit |
| Primary Use | Logistics performance and shipment-delay analytics |
| Data Type | Structured tabular data |
| Access | Publicly available dataset |
| Main Methodological Concern | Potential target leakage and temporal availability of predictors |

### Data Governance and Reproducibility

The dataset will be treated as an external public data source. The analysis will document the dataset source, acquisition procedure, version or download information where available, and any transformations applied to the raw data.

The original raw dataset will be preserved separately from processed datasets. Analytical transformations will be performed programmatically using Python so that the workflow can be reproduced.

## 10. Final Research Gap

The existing literature demonstrates that the DataCo SMART Supply Chain dataset can support shipment-delay prediction, classification, segmentation, and broader supply-chain analysis. However, these applications do not eliminate the need for an integrated analytical workflow that connects operational performance measurement with statistical investigation, predictive modelling, and business interpretation.

This project therefore focuses on developing a reproducible, end-to-end logistics analytics pipeline rather than reproducing an existing predictive model.

The proposed workflow will combine:

1. Logistics KPI measurement.
2. Exploratory data analysis.
3. Statistical analysis.
4. Operational and customer segmentation.
5. Leakage-aware predictive modelling.
6. Model interpretation.
7. Business-oriented decision support.

The project will independently generate its analytical results from the public dataset while using existing literature to inform methodological choices and identify potential limitations.

## 11. Preliminary References

1. DataCo SMART Supply Chain Dataset. Publicly available supply-chain dataset containing order, shipping, customer, product, geographical, and financial information.

2. Interpretable and leakage-aware prediction of shipment delay using the DataCo SMART Supply Chain dataset. Emerald, 2026.

3. Research on machine-learning approaches for late-delivery risk prediction using the DataCo SMART Supply Chain dataset.

4. Research applying machine learning and segmentation techniques to supply-chain and customer analytics using the DataCo dataset.