# Loan Approval Prediction System

A machine learning classification project that predicts whether a loan application is likely to be approved based on applicant financial, demographic, employment, and loan-related information.

## Project Overview

The goal of this project is to explore applicant data, preprocess it, identify useful patterns, engineer relevant features, and build classification models for loan approval prediction.

The project covers the complete basic machine learning workflow:

- Data understanding and cleaning
- Exploratory Data Analysis (EDA)
- Missing-value handling
- Categorical encoding
- Feature scaling
- Feature engineering
- Train-test splitting
- Model training and evaluation
- Model comparison

## Dataset

The dataset contains **1,000 loan applications** with **20 original columns**.

The features include:

- Applicant income
- Coapplicant income
- Age
- Dependents
- Credit score
- Existing loans
- DTI ratio
- Savings
- Collateral value
- Loan amount
- Loan term
- Loan purpose
- Property area
- Education level
- Gender
- Employment status
- Employer category

### Target

`Loan_Approved`

- `Yes` → Loan approved
- `No` → Loan not approved

## Data Preprocessing

The following preprocessing steps were performed:

1. **Missing Value Handling**
   - Numerical features were imputed using the mean.
   - Categorical features were imputed using the most frequent value.

2. **Feature Removal**
   - `Applicant_ID` was removed because it is an identifier rather than a predictive feature.

3. **Categorical Encoding**
   - Label Encoding was applied to `Education_Level` and `Loan_Approved`.
   - One-Hot Encoding was applied to other categorical variables.

4. **Feature Scaling**
   - `StandardScaler` was used to standardize the input features.

## Exploratory Data Analysis

EDA was performed to understand relationships and patterns within the dataset.

Some of the analysis included:

- Loan approval class distribution
- Applicant income distribution
- Coapplicant income distribution
- Credit score distribution
- Outlier analysis using box plots
- Comparison of numerical features with loan approval
- Correlation heatmap
- Feature correlation with the target variable

The analysis showed that **Credit Score** and **DTI Ratio** had relatively strong correlations with the loan approval target in this dataset.

## Feature Engineering

Additional features were created to capture non-linear relationships:

- `DTI_Ratio_sq`
- `Credit_Score_sq`
- `Applicant_Income_log`

These transformations were used in the second round of model training.

## Machine Learning Models

Three classification algorithms were evaluated:

| Model | Accuracy | Precision | Recall | F1 Score |
|---|---:|---:|---:|---:|
| Logistic Regression | **88.0%** | 78.46% | **83.61%** | **80.95%** |
| KNN | 78.5% | 67.31% | 57.38% | 61.95% |
| Gaussian Naive Bayes | 86.0% | **81.13%** | 70.49% | 75.44% |

The final Logistic Regression experiment achieved:

- **Accuracy:** 88.00%
- **Precision:** 78.46%
- **Recall:** 83.61%
- **F1 Score:** 80.95%

These results are based on an **80/20 train-test split**.

## Tech Stack

- **Python**
- **Pandas** — data manipulation
- **NumPy** — numerical operations
- **Matplotlib** — data visualization
- **Seaborn** — statistical visualization
- **Scikit-learn** — preprocessing, model training and evaluation
- **Jupyter Notebook** — development and experimentation

## Project Workflow

```text
Dataset
   ↓
Data Understanding
   ↓
Missing Value Handling
   ↓
Exploratory Data Analysis
   ↓
Feature Selection
   ↓
Categorical Encoding
   ↓
Train-Test Split
   ↓
Feature Scaling
   ↓
Feature Engineering
   ↓
Model Training
   ↓
Model Evaluation
   ↓
Model Comparison