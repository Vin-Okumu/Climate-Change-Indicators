# Dry Eye Disease Modeling

## 📝Introduction

Dry Eye Disease (DED) is a common ocular condition that affects millions of individuals worldwide, causing discomfort, visual disturbances, and a reduction in quality of life. Accurate prediction and early diagnosis of DED remain essential for improving patient care and preventing complications. As such, machine learning (ML) models, including Decision Trees and Random Forest, have shown promise in handling complex, non-linear relationships in medical datasets like the one used in this analysis. This disease modeling analysis aimed to develop a Random Forest model to predict DED incidence using patient data and evaluate the model's performance.🚀

## 🧪Methods

### 📂Data Description

The dataset used for this analysis contains information of about 20000 subjects of teenagers, middle-aged adults and post-adulthood beings of both genders - male and female. Of the 26 columns included in the datasets were measurement on daily steps, sleep time, pulse measurement, blood pressure, eating and drinking habits, stress levels, medical issues such as anxiety, hypertension, asthma etc. and any medication used. Additionally, the data also consists of basic ocular attributes used to predict presence of dry eye disease. 

### 🛠️Data Preprocessing

#### 1. 🧹Data Cleaning

Missing values were handled using median imputation for numerical variables and mode imputation for categorical variables.
Feature names were standardized (lowercased and stripped of extra spaces) to ensure consistency.

#### 2. 🔢One-Hot Encoding

Categorical variables (e.g., Gender, Sleep Quality, Stress Level) were one-hot encoded using `pd.get_dummies()` to convert them into binary columns.
The `drop_first=True` parameter was applied to avoid multicollinearity.

#### 3. 🔄Feature Alignment

After encoding, feature alignment was ensured between training and test data using `reindex()` to handle missing or extra features consistently.

### 🌲Model Training

A Random Forest classifier was trained using the processed data:

🌳Model Type: Random Forest

🌲Number of Trees: 100

🔎Max Depth: None (default)

🏆Criterion: Gini index

🔀Train-Test Split: 80% training, 20% testing

The model was trained using the `RandomForestClassifier` from `scikit-learn`. The target variable was binarized to reflect the presence or absence of DED.

### 📏Model Evaluation

The model’s performance was evaluated using:

✅**Accuracy** – Percentage of correctly classified cases

🎯**Precision** – Percentage of positive predictions that were correct

🔍**Recall** – Percentage of actual positive cases correctly identified

📈**F1-Score** – Harmonic mean of precision and recall

The classification report was generated using `classification_report()` to assess detailed class-wise performance.

### 🔮Prediction on New Data

After training, the model was applied to a new patient dataset:

🏥New data was encoded using the same encoding strategy as training data.

🚫Any missing features were filled with zeros to maintain consistency.

🚀Predictions were made using `predict()` and `predict_proba()` to estimate both classification and probability of DED incidence.

The predictions were saved to a CSV file for further analysis.

## 📊Results

### 🌟Model Performance

The Random Forest model achieved the following performance on the test data:

✅**Accuracy:** 66%

🎯**Precision:** 67% for DED cases, 28% for non-DED cases

🔍**Recall:** 96% for DED cases, 3% for non-DED cases

📈**F1-Score:** 79% for DED cases, 6% for non-DED cases

The model exhibited high sensitivity (recall) for detecting DED cases but struggled to correctly classify non-DED cases due to class imbalance.

#### 🔎Prediction on New Data

The model was applied to new patient data, generating individual predictions and probabilities for each patient. The predicted probability values provided insight into the confidence level of the model's classification.

## 💡Discussion

The Random Forest model demonstrated strong predictive capability for DED, particularly in identifying positive cases (high recall). However, the low recall for non-DED cases indicated a class imbalance issue. This could be addressed through:

✔️**SMOTE** (Synthetic Minority Over-Sampling Technique) to balance the dataset.

✔️**Threshold tuning** to reduce bias toward predicting DED.

✔️**Alternative models** such as Gradient Boosting or Logistic Regression for improved class balance.

The model’s high recall for DED cases suggests it could serve as a valuable screening tool for early diagnosis and intervention, but improvements are needed to enhance its ability to identify non-DED cases accurately.

## ✅Conclusion

This analysis, implementing a Random Forest model to predict Dry Eye Disease (DED) using clinical and demographic data, cretaed a disease model capable of achieving high recall for DED cases. However, while it highlights the model's potential for early diagnosis, improvements in handling class imbalance are necessary to enhance overall classification performance. Further model tuning and exploration of alternative machine learning approaches could refine the model's accuracy and generalizability.

## Proposed Next Steps

🔄 Improve classification of non-DED cases through class balancing techniques.

📈 Explore other machine learning models (e.g., XGBoost, Logistic Regression).

🩺 Incorporate additional clinical features for better predictive power.

👉[*Link to Dataset*](https://www.kaggle.com/code/vincentokumu/dry-eye-disease-modeling?select=Dry_Eye_Dataset.csv)

[![Open adn Execute Analysis In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Vin-Okumu/Dry-Eye-Disease-Modeling/blob/Main/dry-eye-disease-modeling.ipynb)
