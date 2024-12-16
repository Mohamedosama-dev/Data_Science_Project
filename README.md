![Screenshot 2024-12-15 at 18-40-48 Prediction AI - بحث Google](https://github.com/user-attachments/assets/82321ad6-59c5-491f-aa3b-c883cf2683e7)
# Prediction System

This project uses machine learning models to predict different aspects of charity donations based on user transaction data. We have applied several machine learning techniques including regression and classification algorithms to forecast various donation-related outcomes. The models are trained using data from an SQLite database that contains information about transactions, services, and charity categories.



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
- ![gifmaker_me(1)](https://github.com/user-attachments/assets/68781ad8-4015-46da-b85f-eefba4d5c053)


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
- ![Screenshot 2024-12-15 at 19-17-29 Random Forest Regressor logo - بحث Google](https://github.com/user-attachments/assets/ba98e77b-2c58-446b-af1d-1c0b2ba21ebe)

### Gradient Boosting Regressor
This model predicts **transaction amounts** based on the `month` and `user_id`. It uses a gradient boosting approach to minimize errors.

- **Key Features**: `month`, `user_id`
- **Target Variable**: `amount`
- **Evaluation Metric**: Mean Squared Error (MSE)
- ![Screenshot 2024-12-15 at 19-18-33 Gradient Boosting Regressor logo - بحث Google](https://github.com/user-attachments/assets/771fd38e-ffef-4649-b9a2-2d4f0a41a9b9)

### XGBoost Regressor
An optimized gradient boosting model used to predict **charity donations** based on `month` and `charity_name` for better control over overfitting .

- **Key Features**: `month`, `charity_name`
- **Target Variable**: `amount`
- **Evaluation Metric**: Mean Squared Error (MSE)
- ![Screenshot 2024-12-15 at 19-19-47 XGBoost Regressor logo - بحث Google](https://github.com/user-attachments/assets/c53d3de6-5a7f-4bae-9194-876d8dec133d)


### Random Forest Classifier
This classifier predicts the **charity category preferences** based on user data.

- **Key Features**: `month`, `user_id`, `category_name`
- **Target Variable**: `charity_category_id`
- **Evaluation Metric**: Accuracy, Confusion Matrix
- ![Screenshot 2024-12-15 at 19-20-49 Random Forest Classifier - بحث Google](https://github.com/user-attachments/assets/0abb07ad-f810-48ae-9440-eaa1a66168a8)



## Results

### Confusion Matrix
The confusion matrix provides insights into the classification model's performance by showing the number of true positive, false positive, true negative, and false negative predictions.

### Residual Plots
Residual plots are used to visualize the residuals  of the regression models, helping to understand the distribution of prediction .


