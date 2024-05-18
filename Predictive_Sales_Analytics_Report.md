
### Predictive Sales Analytics Report

## Introduction

This project aims to predict close values using machine learning models based on integrated data from multiple datasets, including accounts, products, sales pipeline, and sales teams. The objective is to identify key factors influencing sales outcomes and provide actionable insights to improve sales strategies.

## Data Integration and Preprocessing

### Datasets Used:
1. **Accounts**: Contains information about the company such as sector, year established, revenue, employees, and office location.
2. **Products**: Contains details about the product and sales price.
3. **Sales Pipeline**: Contains sales transactions including sales agent, product, account, deal stage, engage date, close date, and close value.
4. **Sales Teams**: Contains information about the sales agents and their managers.

### Merging Datasets:
The datasets were merged based on the following keys:
- `account` from `accounts` and `sales_pipeline`
- `product` from `products` and `sales_pipeline`
- `sales_agent` from `sales_teams` and `sales_pipeline`

### Data Preprocessing:
- Handled missing values by dropping rows with missing data.
- Encoded categorical features using `LabelEncoder`.

## Exploratory Data Analysis (EDA)

### Correlation Matrix
The correlation matrix provides insights into the relationships between various features.

![Correlation Matrix](file-zSwzWE0qtz1RqKHSxImeZftX)

### Close Value Distribution
The distribution of the `close_value` shows a right-skewed pattern indicating that most deals close at lower values, with a few high-value deals.

![Close Value Distribution](file-ybVUazAL5wUSmQRbmCLpyGsU)

## Feature Engineering

### New Features Created:
- **sales_per_product**: Calculated as `close_value / sales_price`.
- **account_age**: Calculated as `2024 - year_established`.

## Model Building

### RandomForest Model
A RandomForest Regressor was used to predict `close_value`.

### Model Performance:
- **Mean Squared Error (MSE)**: 694,838.42
- **R^2 Score**: 0.8100

### Feature Importances
The RandomForest model identified the most important features for predicting sales outcomes.

![Feature Importances](file-5tfbTCnp4NSTAx2VDaFDMdb1)

### Actual vs. Predicted Close Value
The scatter plot shows the relationship between actual and predicted close values, indicating good model performance.

![Actual vs. Predicted Close Value](file-AKlwmubnAn3eREaIfZJdu0VT)

## Model Interpretation

### Feature Ranking:
1. **sales_price**: 0.3783
2. **deal_stage**: 0.1715
3. **sales_per_product**: 0.1628
4. **product**: 0.1416
5. **series**: 0.1133

Other features had minimal impact on the model's predictions, such as `engage_date`, `employees`, `sales_agent`, and `opportunity_id`.

## Conclusion

The RandomForest model achieved good performance in predicting `close_value` with an R^2 score of 0.8100. The most influential features identified were `sales_price`, `deal_stage`, `sales_per_product`, `product`, and `series`. These insights can help in strategising sales efforts and focusing on high-impact areas to improve overall sales performance.

By following the steps outlined in this report, you can replicate the analysis, customize it for different datasets, and use the findings to drive data-driven decisions in sales management.

