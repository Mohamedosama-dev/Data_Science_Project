
# Prediction System

This project uses machine learning models to predict different aspects of charity donations based on user transaction data. We have applied several machine learning techniques including regression and classification algorithms to forecast various donation-related outcomes. The models are trained using data from an SQLite database that contains information about transactions, services, and charity categories.
![Screenshot 2024-12-15 at 18-40-48 Prediction AI - بحث Google](https://github.com/user-attachments/assets/82321ad6-59c5-491f-aa3b-c883cf2683e7)


## Table of Contents
- [Project Overview](#project-overview)
- [Technologies Used](#technologies-used)
- [Database Schema](#database-schema)
- [Models Used](#models-used)
  - [Random Forest Regressor](#random-forest-regressor)
  - [Gradient Boosting Regressor](#gradient-boosting-regressor)
  - [XGBoost Regressor](#xgboost-regressor)
  - [Random Forest Classifier](#random-forest-classifier)
- [Installation Instructions](#installation-instructions)
- [Usage Instructions](#usage-instructions)
- [Results](#results)
  - [Confusion Matrix](#confusion-matrix)
  - [Residual Plots](#residual-plots)
  - [Feature Importance](#feature-importance)
- [License](#license)

## Project Overview
The goal of this project is to predict various aspects of charity donations based on data from an SQLite database. The project applies machine learning techniques such as **Random Forest**, **Gradient Boosting**, and **XGBoost** to build predictive models for:
1. Forecasting service demand and transaction amounts.
2. Predicting charity category preferences based on donation data.

The code utilizes multiple models to handle regression and classification tasks, including predicting donation amounts and user charity category preferences.

## Technologies Used
- **Python**: Programming language used to implement the machine learning models.
- **SQLite3**: For querying and connecting to the database.
- **Pandas**: Data manipulation and preprocessing.
- **Scikit-learn**: Machine learning library for model building and evaluation.
- **XGBoost**: Advanced boosting algorithm for prediction.
- **Matplotlib & Seaborn**: For visualizing results, including confusion matrices, residual plots, and feature importance.

## Database Schema
The project uses data from an SQLite database, `datawarehouse.db`, which includes the following key tables:
1. **Service_Dimension**: Contains data about different services.
2. **Transaction_Fact**: Contains transaction details, including amount and service references.
3. **Charity_Dimension**: Contains data about charity organizations.
4. **Charity_Category_Dimension**: Contains information about charity categories such as Health, Education, and Environment.
5. **Date_Dimension**: Contains date-related information for transaction records.

## Models Used

### Random Forest Regressor
This model is used for forecasting **service demand** based on the `month` and `service_type`. The model predicts the total demand (`amount`) for each service.

- **Key Features**: `month`, `service_type`
- **Target Variable**: `amount`
- **Evaluation Metric**: Mean Squared Error (MSE)

### Gradient Boosting Regressor
This model predicts **transaction amounts** based on the `month` and `user_id`. It uses a gradient boosting approach to minimize errors.

- **Key Features**: `month`, `user_id`
- **Target Variable**: `amount`
- **Evaluation Metric**: Mean Squared Error (MSE)

### XGBoost Regressor
An optimized gradient boosting model used to predict **charity donations** based on `month` and `charity_name`.

- **Key Features**: `month`, `charity_name`
- **Target Variable**: `amount`
- **Evaluation Metric**: Mean Squared Error (MSE)

### Random Forest Classifier
This classifier predicts the **charity category preferences** based on user data.

- **Key Features**: `month`, `user_id`, `category_name`
- **Target Variable**: `charity_category_id`
- **Evaluation Metric**: Accuracy, Confusion Matrix


## Results

### Confusion Matrix
The confusion matrix provides insights into the classification model's performance by showing the number of true positive, false positive, true negative, and false negative predictions.

### Residual Plots
Residual plots are used to visualize the residuals (errors) of the regression models, helping to understand the distribution of prediction errors.


