# Credit Card Fraud Detection Project
# Credit Card Transaction Analysis and Fraud Detection

## Project Overview

This project focuses on analyzing credit card transaction data to identify spending patterns, detect fraudulent activities, and segment customers based on their financial behavior. The goal is to provide actionable insights for financial institutions to enhance security, optimize marketing strategies, and improve overall customer experience.

## Table of Contents

- [Project Objectives](#project-objectives)
- [Dataset](#dataset)
- [Methodology](#methodology)
  - [Data Generation](#data-generation)
  - [Data Exploration and Preprocessing](#data-exploration-and-preprocessing)
  - [Data Visualization and Insights](#data-visualization-and-insights)
  - [Machine Learning Models](#machine-learning-models)
    - [Fraud Detection](#fraud-detection)
    - [Customer Segmentation](#customer-segmentation)
- [Results and Discussion](#results-and-discussion)
- [Installation and Usage](#installation-and-usage)
- [File Structure](#file-structure)
- [Future Work](#future-work)
- [License](#license)

## Project Objectives

As outlined in `docs/project_objectives.md`, the primary objectives of this project are:

1.  **Understand Credit Card Transaction Patterns**: Analyze historical credit card transaction data to identify common spending behaviors, popular merchants, and peak transaction periods.
2.  **Detect Fraudulent Transactions**: Develop a machine learning model to accurately identify and predict fraudulent credit card transactions, minimizing financial losses and enhancing security.
3.  **Segment Customers**: Group customers based on their transaction behavior and demographic information to enable targeted marketing strategies and personalized financial services.
4.  **Provide Actionable Insights**: Generate clear, data-driven insights and visualizations that can inform business decisions related to risk management, customer engagement, and product development.

## Dataset

The dataset used in this project is synthetically generated to simulate real-world credit card transactions. It includes the following features:

-   `transaction_id`: Unique identifier for each transaction.
-   `customer_id`: Unique identifier for each customer.
-   `date`: Date and time of the transaction.
-   `amount`: Transaction amount.
-   `card_type`: Type of credit card (e.g., Visa, Mastercard, Amex).
-   `merchant`: Merchant where the transaction occurred.
-   `is_fraud`: Binary indicator (1 for fraud, 0 for legitimate).
-   `age`: Customer's age.
-   `gender`: Customer's gender.
-   `income`: Customer's annual income.

## Methodology

### Data Generation

The synthetic dataset was generated using Python scripts (`src/generate_data.py`) to ensure a realistic distribution of transaction amounts, card types, merchants, and customer demographics. A small percentage of transactions were intentionally marked as fraudulent to simulate a real-world fraud detection scenario.

### Data Exploration and Preprocessing

Initial data exploration was performed to understand the dataset's structure, identify missing values, and analyze data distributions. Key steps included:

-   Loading and examining the dataset (`notebooks/data_exploration.py`).
-   Performing data quality checks, including identifying missing values, duplicate rows, and data types.
-   Calculating descriptive statistics for numerical and categorical features.
-   Identifying potential outliers in transaction amounts.

### Data Visualization and Insights

Various visualizations were created to gain insights into spending patterns, customer demographics, and trends. These visualizations are saved in the `docs/` directory and include:

-   Distribution of numerical features (e.g., `amount_distribution.png`, `age_distribution.png`, `income_distribution.png`).
-   Distribution of categorical features (e.g., `card_type_distribution.png`, `merchant_distribution.png`, `gender_distribution.png`).
-   Spending patterns by merchant (`spending_by_merchant.png`).
-   Customer demographics: Age vs. Income (`age_vs_income.png`).
-   Correlation matrix of numerical features (`correlation_matrix.png`).
-   Monthly spending trends (`monthly_spending_trends.png`).
-   Fraud incidents over time (`fraud_over_time.png`).

### Machine Learning Models

Two main machine learning models were developed:

#### Fraud Detection

A Random Forest Classifier was used to build a fraud detection model. The data was preprocessed by encoding categorical features using `LabelEncoder` and scaling numerical features using `StandardScaler`. The model was trained on a portion of the dataset and evaluated using classification metrics such as precision, recall, F1-score, and confusion matrix. Feature importances were also analyzed to understand which features contribute most to fraud detection.

#### Customer Segmentation

K-Means clustering was applied to segment customers based on their aggregated transaction behavior (total amount spent) and demographic information (age, income). The Elbow Method was used to determine the optimal number of clusters. The resulting customer segments are visualized to show distinct groups based on their financial profiles.

## Results and Discussion

-   **Fraud Detection**: The Random Forest model demonstrated strong performance in identifying fraudulent transactions, achieving high precision and recall. The feature importance analysis revealed that `amount` was the most significant feature in detecting fraud.
-   **Customer Segmentation**: The K-Means clustering successfully grouped customers into distinct segments. These segments can be used for targeted marketing campaigns, personalized product offerings, and risk assessment.
-   **Insights**: The data analysis and visualizations provided insights into typical spending behaviors, popular merchants, and trends in both legitimate and fraudulent transactions. For instance, high-value transactions are more likely to be fraudulent, and spending patterns vary significantly across different merchants and card types.

## Installation and Usage

To run this project locally, follow these steps:

1.  **Clone the repository**:
    ```bash
    git clone <repository_url>
    cd credit_card_project
    ```
2.  **Install dependencies**:
    ```bash
    pip install -r requirements.txt
    ```
    (Note: `requirements.txt` needs to be created, listing `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`)
3.  **Generate the synthetic dataset**:
    ```bash
    python src/generate_data.py
    ```
4.  **Run data exploration and analysis**:
    ```bash
    python notebooks/data_exploration.py
    python notebooks/data_quality_assessment.py
    ```
5.  **Generate visualizations**:
    ```bash
    python notebooks/simple_visualization.py
    python notebooks/advanced_analysis.py
    ```
6.  **Run machine learning models**:
    ```bash
    python src/simple_ml.py
    ```

## File Structure

```
credit_card_project/
├── data/
│   └── credit_card_transactions.csv
├── notebooks/
│   ├── data_exploration.py
│   ├── data_quality_assessment.py
│   ├── simple_visualization.py
│   └── advanced_analysis.py
├── src/
│   ├── generate_data.py
│   └── simple_ml.py
├── docs/
│   ├── project_objectives.md
│   ├── amount_distribution.png
│   ├── merchant_distribution.png
│   ├── fraud_distribution.png
│   ├── spending_by_card_type.png
│   ├── avg_spending_merchant_card_type.png
│   ├── age_distribution.png
│   ├── income_distribution.png
│   ├── monthly_spending_trends.png
│   ├── fraud_over_time.png
│   ├── elbow_method.png
│   └── customer_segments.png
├── models/ (for saved models, if any)
├── README.md
└── requirements.txt
```

## Future Work

-   Explore more advanced fraud detection techniques (e.g., anomaly detection, deep learning).
-   Implement real-time fraud detection system.
-   Integrate with external data sources for richer customer profiles.
-   Develop a web application for interactive data visualization and model deployment.






