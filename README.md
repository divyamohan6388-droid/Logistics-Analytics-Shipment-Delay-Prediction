# Logistics Analytics & Shipment Delay Risk Prediction

## Project Overview

This project focuses on analysing logistics and supply chain data to understand shipping performance, identify patterns associated with delivery risk, and explore how machine learning can support data-driven decision-making.

The project uses the **DataCo SMART Supply Chain dataset** and Python-based data analysis techniques.

## Objectives

- Analyse logistics and shipping performance.
- Identify patterns across shipping modes, regions, product categories, and time periods.
- Calculate key performance indicators (KPIs).
- Explore factors associated with the dataset's late-delivery-risk label.
- Develop and evaluate a machine learning model for risk prediction.
- Provide practical recommendations based on analytical findings.

## Tools & Technologies

- Python
- Pandas and NumPy
- Matplotlib and Seaborn
- SciPy
- Scikit-learn
- Jupyter Notebook
- Git and GitHub

## Project Structure

```text
logistics-analytics-shipment-delay-prediction/
├── data/
├── notebooks/
│   ├── 01_data_understanding.ipynb
│   ├── 02_eda.ipynb
│   ├── 03_kpi_analysis.ipynb
│   ├── 04_feature_engineering.ipynb
│   ├── 05_model_training.ipynb
│   ├── 06_model_evaluation.ipynb
│   └── 07_business_recommendations.ipynb
├── README.md
└── .gitignore
```

*Note: Update this structure to match the actual files and folders in the repository. The listed future notebooks are planned stages, not claims that they are already complete.*

## Current Progress

- Data understanding and initial dataset inspection completed.
- Exploratory data analysis completed.
- Statistical analysis of shipping-mode differences performed.
- KPI analysis and predictive modelling planned as the next stages.

## Dataset

The project uses the DataCo SMART Supply Chain dataset for supply chain and logistics analysis.

Dataset reference: https://data.mendeley.com/datasets/8gx2fvg2k6/5

## Methodology

1. Data understanding and quality checks.
2. Data cleaning and preprocessing.
3. Exploratory data analysis and visualization.
4. KPI calculation and interpretation.
5. Feature engineering and leakage prevention.
6. Predictive model training and evaluation.
7. Business insights and recommendations.

## Important Note

The dataset's `Late_delivery_risk` field is treated as the dataset's recorded risk label. It is analysed separately from the difference between actual and scheduled shipping duration. Observed associations do not necessarily establish causation.
