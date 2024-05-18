# Predictive Sales Analytics

Predictive Sales Analytics project aims to leverage machine learning techniques to predict sales outcomes based on integrated data from multiple sources. The project involves data preprocessing, exploratory data analysis (EDA), feature engineering, model building, and interpretation to derive actionable insights that can help improve sales strategies.

## Table of Contents

- [Introduction](#introduction)
- [Datasets](#datasets)
- [Data Integration and Preprocessing](#data-integration-and-preprocessing)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Feature Engineering](#feature-engineering)
- [Model Building](#model-building)
- [Model Interpretation](#model-interpretation)
- [Conclusion](#conclusion)
- [Visualizations](#visualizations)
- [How to Run](#how-to-run)
- [Contributing](#contributing)
- [License](#license)

## Introduction

This project aims to predict close values using machine learning models based on integrated data from multiple datasets. The objective is to identify key factors influencing sales outcomes and provide actionable insights to improve sales strategies.

## Datasets

1. **Accounts**: Contains information about the company such as sector, year established, revenue, employees, and office location.
2. **Products**: Contains details about the product and sales price.
3. **Sales Pipeline**: Contains sales transactions including sales agent, product, account, deal stage, engage date, close date, and close value.
4. **Sales Teams**: Contains information about the sales agents and their managers.

## Data Integration and Preprocessing

### Merging Datasets

The datasets were merged based on the following keys:
- `account` from `accounts` and `sales_pipeline`
- `product` from `products` and `sales_pipeline`
- `sales_agent` from `sales_teams` and `sales_pipeline`

### Data Preprocessing

- Handled missing values by dropping rows with missing data.
- Encoded categorical features using `LabelEncoder`.

## Exploratory Data Analysis

### Correlation Matrix
The correlation matrix provides insights into the relationships between various features.

![Correlation Matrix](path_to_image/correlation_matrix.png)

### Close Value Distribution
The distribution of the `close_value` shows a right-skewed pattern indicating that most deals close at lower values, with a few high-value deals.

![Close Value Distribution](path_to_image/close_value_distribution.png)

## Feature Engineering

### New Features Created

- **sales_per_product**: Calculated as `close_value / sales_price`.
- **account_age**: Calculated as `2024 - year_established`.

## Model Building

### RandomForest Model

A RandomForest Regressor was used to predict `close_value`.

### Model Performance

- **Mean Squared Error (MSE)**: 694,838.42
- **R^2 Score**: 0.8100

### Feature Importances

The RandomForest model identified the most important features for predicting sales outcomes.

![Feature Importances](path_to_image/feature_importances.png)

### Actual vs. Predicted Close Value

The scatter plot shows the relationship between actual and predicted close values, indicating good model performance.

![Actual vs. Predicted Close Value](path_to_image/actual_vs_predicted.png)

## Model Interpretation

### Feature Ranking

1. **sales_price**: 0.3783
2. **deal_stage**: 0.1715
3. **sales_per_product**: 0.1628
4. **product**: 0.1416
5. **series**: 0.1133

Other features had minimal impact on the model's predictions, such as `engage_date`, `employees`, `sales_agent`, and `opportunity_id`.

## Conclusion

The RandomForest model achieved good performance in predicting `close_value` with an R^2 score of 0.8100. The most influential features identified were `sales_price`, `deal_stage`, `sales_per_product`, `product`, and `series`. These insights can help in strategising sales efforts and focusing on high-impact areas to improve overall sales performance.

## Visualizations

- Correlation Matrix
- Close Value Distribution
- Feature Importances
- Actual vs. Predicted Close Value

## How to Run

1. Clone the repository:
    ```sh
    git clone https://github.com/yourusername/predictive-sales-analytics.git
    ```
2. Navigate to the project directory:
    ```sh
    cd predictive-sales-analytics
    ```
3. Install the required packages:
    ```sh
    pip install -r requirements.txt
    ```
4. Run the project:
    ```sh
    python main.py
    ```

## Contributing

Contributions are welcome! Please open an issue or submit a pull request for any improvements or new features.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

By following the steps outlined in this project, you can replicate the analysis, customize it for different datasets, and use the findings to drive data-driven decisions in sales management.
