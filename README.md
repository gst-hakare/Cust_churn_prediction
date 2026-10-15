# Customer Churn Prediction Using Machine Learning

## Project Overview

This project analyzes telecom customer data and develops a Machine Learning model to predict whether a customer is likely to leave the company (churn). It uses customer demographics, service subscriptions, contract details, and billing information to identify patterns associated with customer churn.

## Objectives

* Analyze customer behavior and churn patterns.
* Perform data cleaning and Exploratory Data Analysis (EDA).
* Prepare categorical and numerical features for Machine Learning.
* Address class imbalance using Random OverSampling.
* Build a Random Forest classification model.
* Evaluate model performance using accuracy and cross-validation.

## Dataset

* **Dataset:** Telecom Customer Churn
* **Total Records:** 7,043
* **Total Original Features:** 20 after removing the customer ID
* **Target Variable:** `Churn`
* **Target Classes:** Yes (customer churned) and No (customer retained)

The dataset contains customer demographics, tenure, internet and phone services, contract types, payment methods, monthly charges, total charges, and churn status.

## Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Imbalanced-learn
* Jupyter Notebook

## Project Workflow

### 1. Data Loading

Imported the dataset using Pandas and inspected the first few records.

### 2. Data Cleaning

* Checked for duplicate records.
* Removed the `customerID` column.
* Identified blank values in `TotalCharges`.
* Converted `TotalCharges` to a numerical data type.
* Identified 11 missing values in `TotalCharges`.

### 3. Exploratory Data Analysis (EDA)

Performed data exploration and visualization to understand:

* Churned versus retained customers.
* Distribution of total charges.
* Monthly charges by contract type and churn status.
* Customer characteristics and service usage patterns.

Visualizations included histograms, box plots, count plots, bar plots, and pair plots.

### 4. Data Preprocessing

* Encoded categorical variables using Pandas `get_dummies()`.
* Separated independent variables (`X`) and the target variable (`y`).
* Addressed class imbalance using Random OverSampling.
* Applied StandardScaler for feature scaling.

### 5. Model Building

Implemented a Random Forest Classifier using Scikit-learn to predict customer churn.

### 6. Model Evaluation

Evaluated the model using training accuracy, testing accuracy, and 10-fold cross-validation on the training data.

## Model Performance

| Evaluation Metric                      | Result |
| -------------------------------------- | -----: |
| Training Accuracy                      | 99.81% |
| Testing Accuracy                       | 89.22% |
| Mean 10-Fold Cross-Validation Accuracy | 87.99% |

*Note: These are the results from the initial implementation. Oversampling and scaling were performed before the train-test split, which may cause data leakage. The model should be retrained using a leakage-free pipeline before these metrics are treated as final performance results.*

## Key Findings

* The dataset contains more retained customers than churned customers.
* Customer tenure, contract type, service subscriptions, and billing characteristics are useful areas to investigate when analyzing churn.
* Random OverSampling was used to balance the target classes during model development.
* The initial Random Forest model achieved 89.22% testing accuracy, although further validation is required.

## Business Applications

* Identify customers who may be at risk of leaving.
* Support customer retention strategies.
* Help businesses investigate churn patterns across contract types and service categories.
* Provide insights for customer engagement and retention planning.

## Future Improvements

* Prevent data leakage by splitting the dataset before oversampling and scaling.
* Handle missing values using an appropriate imputation strategy.
* Evaluate the model using precision, recall, F1-score, and a confusion matrix.
* Apply hyperparameter tuning using GridSearchCV or RandomizedSearchCV.
* Compare Random Forest with Logistic Regression and other classification algorithms.
* Identify important features influencing churn predictions.
* Develop an interactive dashboard or deploy the model as a web application.

## Conclusion

This project demonstrates the application of Python-based data analysis and Machine Learning techniques to a customer churn problem. It covers data cleaning, EDA, feature encoding, class balancing, feature scaling, Random Forest classification, and model evaluation. The project can be extended with improved validation, feature importance analysis, and deployment.
