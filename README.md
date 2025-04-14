# 🛒 Walmart Weekly Sales Prediction

## Introduction

Retail giants like Walmart rely heavily on precise inventory and supply chain planning to remain profitable. One of the key challenges is aligning stock availability with customer demand — a mismatch can lead to lost revenue or excess inventory.

In this project, I aimed to **predict weekly sales across Walmart stores using machine learning**, with the goal of helping reduce inventory issues, minimize waste, and improve customer satisfaction. The regression-based approach used here can be generalized to other industries facing similar demand-supply forecasting challenges.

## Dataset

I used the publicly available dataset from Kaggle:  
🔗 [Walmart Store Sales Dataset](https://www.kaggle.com/datasets/bharatkumar0925/walmart-store-sales)

This dataset includes historical weekly sales data from 45 Walmart stores, along with features like temperature, fuel prices, CPI, unemployment rate, and holiday indicators.

## Approach

### Exploratory Data Analysis (EDA)

To understand the data better, I performed EDA and observed the following patterns:

- **Temperature vs Sales**: Sales tend to drop during extremely hot or cold weeks.
- **Holiday Weeks**: Holiday weeks usually have higher average sales.
- **Seasonal Effects**: December stands out with the highest average weekly sales, likely due to holiday shopping.
- **Correlation Analysis**: Helped in identifying weakly and strongly related features.

### Feature Engineering

- Extracted `month`, `week`, and `year` from the date.
- Scaled numerical features using **RobustScaler** to handle outliers.
- Selected relevant features such as `Store`, `Temperature`, `Fuel_Price`, `CPI`, `Unemployment`, and `Holiday_Flag`.

### Baseline Model

To establish a baseline for model comparison, I used a **Dummy Regressor** that predicts the mean weekly sales.

## Machine Learning Models

I implemented and evaluated the following regression models using `Pipeline`, `RobustScaler`, and `GridSearchCV`:

- Linear Regression  
- Ridge & ElasticNet  
- K-Nearest Neighbors  
- Support Vector Regressor  
- Random Forest  
- Gradient Boosting Regressor  
- AdaBoost  
- Bayesian Ridge  
- Multi-Layer Perceptron (MLP)

Each model was evaluated using **Negative Root Mean Squared Error (neg RMSE)** via cross-validation.

## 🏆 Best Model

The **Gradient Boosting Regressor** performed the best, achieving the **lowest RMSE** across all models tested.

## Final Evaluation

On the test dataset, I computed the following evaluation metrics:

- **Root Mean Squared Error (RMSE)**: **94288.895**
- **Mean Absolute Error (MAE)**: **54381.644**
- **R² Score**: **0.973**, indicating strong predictive performance

I also visualized **feature importance**, which revealed:

- `Store` had the most influence on weekly sales,
- Followed by `CPI`, `Unemployment`, and `Month`.

---

## Conclusion

This project demonstrates how machine learning can be used to forecast sales and support smarter business decisions in retail. With a highly accurate Gradient Boosting model and interpretable feature insights, this approach can help optimize inventory management and reduce operational costs.
