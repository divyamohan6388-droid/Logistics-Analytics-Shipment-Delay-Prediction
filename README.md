# Logistics Analytics: Shipment Delay Prediction

An end-to-end data analytics and machine learning capstone project analysing shipment performance, delivery risk, and operational patterns using the DataCo SMART Supply Chain dataset.

## Project Overview

Late deliveries can affect customer satisfaction, operational efficiency, and supply chain performance. This project explores historical shipment data to identify delivery-risk patterns, analyse shipping performance, and evaluate machine learning models for classifying the dataset's `Late_delivery_risk` label.

The project combines data cleaning, exploratory data analysis, KPI development, statistical testing, feature engineering, model evaluation, and business recommendations.

## Objectives

- Clean and prepare supply chain data for analysis.
- Analyse shipment delays and delivery-risk patterns.
- Develop operational KPIs for measuring shipping performance.
- Investigate relationships between shipping mode and delivery risk.
- Engineer features for machine learning.
- Compare Logistic Regression and Random Forest.
- Translate analytical findings into practical business recommendations.

## Dataset

**Dataset:** DataCo SMART Supply Chain Dataset

The project uses the DataCo SMART Supply Chain dataset for supply chain and logistics analysis.

Dataset reference: https://data.mendeley.com/datasets/8gx2fvg2k6/5

The cleaned dataset contains **180,519 records and 51 columns**.

Key data preparation steps include:
- Removing columns that were entirely missing or unnecessary for analysis.
- Excluding sensitive customer password information.
- Converting order and shipping dates into datetime format during data preparation.
- Creating `shipping_delay_days` to measure the difference between actual and scheduled shipping duration.
- Investigating missing values, duplicate records, and potential outliers.

The cleaned dataset retains 11 missing values in two customer-identification fields. These fields are not used as model features.

## Project Structure

```text
logistics-analytics-shipment-delay-prediction/
│
├── data/
│   ├── raw/
│   └── processed/
│       └── DataCoSupplyChain_cleaned.csv
│
├── notebooks/
│   ├── 01_data_understanding.ipynb
│   ├── 02_eda.ipynb
│   ├── 03_kpi_analysis.ipynb
│   ├── 04_feature_engineering.ipynb
│   └── 05_business_recommendations.ipynb
│
├── reports/
│    ├── weekly reports/
│       └── Week_1_Logistics_Data_Analysis_Report
│       └── Week_2_Data_Collection_Cleaning_Preprocessing_Report
│       └── Week_3_Advanced_Data_Analysis_and_Visualization_Report
│       └── Week_4_Feature_Engineering_Machine_Learning_Report
│   ├── figures/
│   │   ├── confusion_matrices.png
│   │   └── roc_curve_comparison.png
│   └── model_evaluation_results.csv
│
├── .gitignore
└── README.md
```

## Analysis and Methodology

### 1. Data Understanding and Cleaning
Inspected the dataset's dimensions, data types, missing values, duplicates, and potential outliers.

### 2. Exploratory Data Analysis
Explored shipment performance, delivery-risk patterns, and variations across shipping modes, regions, product categories, and time periods.

### 3. KPI Analysis
Calculated delivery-risk rates, schedule-overrun rates, and actual-versus-scheduled shipping-duration differences.

### 4. Feature Engineering
Selected relevant categorical and numerical features, extracted order-month and day-of-week information, and prepared a chronological training and testing split.

Potential target leakage was addressed by excluding outcome-related fields such as `Delivery Status`, actual shipping duration, shipping date, and `shipping_delay_days` from the model inputs.

### 5. Machine Learning and Evaluation
Compared two classification models:
- Logistic Regression
- Random Forest

Evaluation included accuracy, precision, recall, F1-score, ROC-AUC, confusion matrices, and ROC curves.

## Key Findings

- **54.83%** of records are labelled as having late-delivery risk.
- **57.28%** of records have an actual shipping duration greater than the scheduled duration.
- Second Class has an average actual-minus-scheduled duration difference of **1.99 days**.
- The analysis found a strong association between shipping mode and the late-delivery-risk label.
- Both machine learning models achieved a ROC-AUC of approximately **0.737**.

## Model Performance

| Metric | Logistic Regression | Random Forest |
|---|---:|---:|
| Accuracy | 69.04% | 69.00% |
| Precision | 83.69% | 81.68% |
| Recall | 53.86% | 55.80% |
| F1-score | 65.54% | 66.30% |
| ROC-AUC | 0.7370 | 0.7369 |

Random Forest achieved a slightly higher recall and F1-score, while Logistic Regression achieved higher precision. Neither model is clearly superior across all metrics.

## Business Recommendations

- Investigate the schedule-overrun patterns observed for First Class and Second Class shipments.
- Monitor delivery-risk rates and schedule overruns across shipping modes, regions, and product categories.
- Investigate the observed decline in order-record volume in late 2017; its cause has not been established.
- Validate model predictions and classification thresholds before considering operational use.
- Ensure that future predictions use only information available at the intended prediction time.

## Limitations

- Dataset records represent order items and may not correspond one-to-one with physical shipments.
- The `Late_delivery_risk` label is related to delivery outcome information; its meaning and timing must be considered when interpreting the model results.
- Evaluation on historical data does not establish performance in a live logistics environment.
- Observed associations do not establish causal relationships.
- Additional temporal validation and operational testing are required before deployment.

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- SciPy
- Statsmodels
- Scikit-learn
- Jupyter Notebook
- Git and GitHub

## Conclusion

This project demonstrates a structured workflow for supply chain data analysis, KPI development, statistical investigation, feature engineering, and baseline machine learning evaluation. The findings provide a starting point for investigating shipment performance and developing better-informed logistics decisions.

## 📬 Contact

I'm always open to connecting with data science enthusiasts, researchers, and professionals working in **Data Analytics, Machine Learning, Artificial Intelligence, and Statistics**.

<p align="center">
  <a href="https://linkedin.com/in/divya-mohan-a42b12389">
    <img src="https://img.shields.io/badge/LinkedIn-Connect%20with%20me-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"/>
  </a>
  <a href="https://github.com/divyamohan6388-droid">
    <img src="https://img.shields.io/badge/GitHub-Follow%20my%20work-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub"/>
  </a>
</p>

<p align="center">
  <i>Curious mind. Data-driven thinking. Continuous learning.</i>
</p>
