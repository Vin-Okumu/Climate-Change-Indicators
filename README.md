# Dry Eye Disease Modeling

## Introduction

Dry Eye Disease (DED) is a common ocular condition that affects millions of individuals worldwide, causing discomfort, visual disturbances, and a reduction in quality of life. Accurate prediction and early diagnosis of DED remain essential for improving patient care and preventing complications. As such, machine learning (ML) models, including Decision Trees and Random Forest, have shown promise in handling complex, non-linear relationships in medical datasets like the one used in this analysis. This disease modeling analysis aimed to develop a Random Forest model to predict DED incidence using patient data and evaluate the model's performance.

## Methods

### Data Description

The dataset used for this analysis contains information of about 20000 subjects of teenagers, middle-aged adults and post-adulthood beings of both genders - male and female. Of the 26 columns included in the datasets the dataset captured measurement on daily steps, sleep time, pulse measurement, blood pressure, eating and drinking habits, stress levels, medical issues such as anxiety, hypertension, asthma etc. and any medication used. Additionally, the data also consists of basic ocular attributes used to predict presence of dry eye disease. 

### Data Preprocessing

#### 1. Data Cleaning

Missing values were handled using median imputation for numerical variables and mode imputation for categorical variables.
Feature names were standardized (lowercased and stripped of extra spaces) to ensure consistency.

#### 2. One-Hot Encoding

Categorical variables (e.g., Gender, Sleep Quality, Stress Level) were one-hot encoded using pd.get_dummies() to convert them into binary columns.
The drop_first=True parameter was applied to avoid multicollinearity.

#### 3. Feature Alignment

After encoding, feature alignment was ensured between training and test data using reindex() to handle missing or extra features consistently.

**The dataset used in this analysis is hosted on [**Kaggle**](https://www.kaggle.com/code/vincentokumu/dry-eye-disease-modeling?select=Dry_Eye_Dataset.csv)**

*Click the button below to view the code and execute the analysis in Google Colab* 

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Vin-Okumu/Dry-Eye-Disease-Modeling/blob/Main/dry-eye-disease-modeling.ipynb)
