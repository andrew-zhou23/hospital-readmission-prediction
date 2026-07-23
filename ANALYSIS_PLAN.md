# ANALYSIS PLAN

## Project Overview

This document outlines the planned analytical workflow for the Hospital Readmission Analysis project. It defines the methodology that will be followed throughout the project before any data cleaning, feature engineering, statistical analysis, or machine learning begins.

The purpose of this document is to ensure that every analytical decision is intentional, reproducible, and directly aligned with the project's research question.

This document will be updated throughout the project as analytical decisions are made and validated.

## Analytical Workflow

The project will follow the workflow below:

1. Acquire and understand the datasets.
2. Merge the datasets into a single hospital-level dataset.
3. Assess data quality and identify missing or inconsistent values.
4. Clean and prepare the data for analysis.
5. Perform exploratory data analysis (EDA).
6. Engineer and transform features.
7. Develop predictive machine learning models.
8. Interpret model predictions using explainable AI techniques.
9. Develop data-driven recommendations.
10. Communicate findings through visualizations, reports, and an interactive dashboard.

Each phase builds upon the previous phase to ensure that the analysis is both systematic and reproducible.

## Target Variable

### Primary Target

**Variable:** Excess Readmission Ratio

**Dataset:** Hospital Readmissions Reduction Program

**Condition:** Heart Failure

The Excess Readmission Ratio represents the hospital's risk-adjusted 30-day heart failure readmission performance as calculated by CMS.

Version 1 of this project will focus exclusively on the Heart Failure readmission measure to simplify the analysis and ensure that each hospital has a single target observation.

### Secondary Target

A binary classification variable may also be created.

High Readmission Hospital

Definition:

Excess Readmission Ratio > 1.00

This classification will allow the development of predictive classification models in addition to regression models.

## Dataset Merge Strategy

Three CMS datasets will be combined to create a single hospital-level analytical dataset.

Datasets

• Hospital Readmissions Reduction Program
• Hospital General Information
• HCAHPS Patient Survey

Primary Join Key

Facility ID

Expected Final Structure

One row will represent one hospital.

The Hospital Readmissions dataset will first be filtered to include only Heart Failure readmission measures.

The HCAHPS dataset will then be transformed from long format into wide format so that each patient experience measure becomes a separate column before merging with the remaining datasets.

## Feature Selection Philosophy

Potential predictor variables should satisfy the following principles.

1. The variable should be available before hospital readmission performance is measured.

2. The variable should represent a hospital characteristic or patient experience measure.

3. The variable should have a reasonable theoretical relationship with hospital readmission performance.

4. The variable should be interpretable by healthcare professionals.

Variables will generally be excluded if they:

• uniquely identify a hospital
• are administrative labels
• are used to calculate the target variable
• duplicate information contained in another variable
• introduce target leakage

## Initial Feature Groups

### Hospital Characteristics

Potential predictors include:

• Hospital Ownership
• Hospital Type
• Emergency Services
• Hospital Overall Rating
• State
• County
• Number of Discharges

---

### Patient Experience Measures

Potential predictors include:

• Nurse Communication
• Doctor Communication
• Communication About Medicines
• Discharge Information
• Care Transition
• Overall Hospital Rating
• Recommend Hospital
• HCAHPS Answer Percent
• Patient Survey Star Rating

---

### Administrative Variables

The following variables will not be used for modeling but may be retained for reporting purposes.

• Facility ID
• Facility Name
• Address
• Telephone Number

---

### Variables Requiring Further Investigation

The usefulness of the following variables will be evaluated during exploratory analysis.

• Measure Count Variables
• Better/Worse Performance Counts
• Survey Response Rate
• Count of Facility Measures

## Data Cleaning Plan

The following preprocessing steps are expected before analysis begins.

• Filter the readmission dataset to Heart Failure measures.
• Remove duplicate hospitals if necessary.
• Pivot the HCAHPS dataset into hospital-level format.
• Convert percentages and numeric variables to appropriate data types.
• Replace "Not Available" and other placeholder values with missing values.
• Standardize categorical variables.
• Assess missing values and determine appropriate handling strategies.
• Verify successful dataset merges using Facility ID.

## Missing Data Strategy

Missing values will not be removed automatically.

Each missing value will first be investigated to determine the reason for its absence.

Possible causes include:

• insufficient patient volume
• hospital does not provide a service
• CMS suppression rules
• unavailable reporting

The treatment of missing values will depend on the reason they are missing.

Possible handling methods include:

• removal
• imputation
• treating missingness as meaningful information

## Exploratory Data Analysis Plan

The exploratory analysis phase will answer the following questions.

• How are heart failure readmission ratios distributed across hospitals?

• Which hospital characteristics are associated with higher readmission ratios?

• Which patient experience measures appear to be associated with readmission performance?

• Are there regional differences across the United States?

• Which variables exhibit the strongest relationships with the target variable?

• Are there important outliers or unusual hospitals that require additional investigation?

The results of this phase will guide feature engineering and model development.

## Feature Engineering Plan

Potential feature engineering tasks include:

• Encoding categorical variables.
• Creating regional indicators.
• Aggregating patient experience measures.
• Standardizing numerical variables where appropriate.
• Removing highly correlated variables.
• Creating binary outcome variables for classification models.
• Investigating interaction effects between important predictors.

Only features that improve interpretability or predictive performance will be retained.

## Modeling Strategy

Two predictive modeling approaches will be explored.

### Regression

Objective

Predict the numerical Excess Readmission Ratio.

Candidate Models

• Linear Regression
• Random Forest Regressor
• XGBoost Regressor

---

### Classification

Objective

Predict whether a hospital performs above or below the CMS benchmark.

Candidate Models

• Logistic Regression
• Decision Tree
• Random Forest
• XGBoost

Model complexity will increase gradually, beginning with interpretable baseline models before progressing to more advanced ensemble methods.

## Model Evaluation

Regression models will be evaluated using:

• Mean Absolute Error (MAE)
• Root Mean Squared Error (RMSE)
• R² Score

Classification models will be evaluated using:

• Accuracy
• Precision
• Recall
• F1 Score
• ROC-AUC
• Confusion Matrix

Model performance will be compared across multiple algorithms before selecting a final model.

## Model Interpretation

Model interpretation is a primary objective of this project.

The final predictive model will be interpreted using SHAP (SHapley Additive exPlanations).

SHAP analysis will identify the variables that contribute most strongly to hospital readmission predictions and explain how individual predictors influence model output.

The goal is not only to build an accurate model, but also to understand why hospitals differ in readmission performance.

## Risks and Limitations

The following limitations are acknowledged before analysis begins.

• This project is observational and cannot establish causal relationships.

• The analysis is limited to hospitals included in the CMS datasets.

• Version 1 focuses exclusively on Heart Failure readmissions.

• CMS reporting methods and suppression rules may introduce missing values.

• Additional social, demographic, and clinical factors influencing readmissions may not be captured within the available datasets.

## Decision Log

Major analytical decisions made throughout the project will be documented below.

| Date | Decision | Reason |
|------|----------|--------|
| July 2026 | Project scope limited to Heart Failure readmissions | Simplifies modeling and produces one observation per hospital. |
| July 2026 | Facility ID selected as the primary merge key | Shared across all CMS datasets. |
| July 2026 | Number of Readmissions excluded as a predictor | Prevents target leakage. |

Additional decisions will be recorded throughout the project to maintain transparency and reproducibility.
