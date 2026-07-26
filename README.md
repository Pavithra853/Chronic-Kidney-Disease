# Chronic-Kidney-Disease
# Week 1: Ethical Data Sourcing, Preprocessing, and Exploration

## Overview

The objective of Week 1 was to prepare the Chronic Kidney Disease (CKD) dataset for analysis. The work included sourcing an anonymized medical dataset, cleaning the data, preprocessing it, and performing an initial exploration to understand its structure and quality.


## Tasks Completed

### 1. Ethical Data Sourcing

- Created a GitHub repository for the project.
- Used an anonymized Chronic Kidney Disease (CKD) dataset.
- Verified that the dataset contains no personally identifiable information (PII).
- Ensured the dataset is used only for educational and research purposes.


### 2. Data Cleaning

The dataset was cleaned to improve data quality.

Completed tasks:
- Removed duplicate records.
- Standardized column names.
- Corrected inconsistent values.
- Identified missing values.
- Saved the cleaned dataset as **CKD_Cleaned_Dataset.csv**.


### 3. Data Preprocessing

The cleaned dataset was preprocessed before analysis.

Completed tasks:
- Converted numeric columns to appropriate data types.
- Converted categorical columns to category data type.
- Filled missing numeric values using the **median**.
- Filled missing categorical values using the **mode**.
- Verified that missing values were handled successfully.
- Saved the preprocessed dataset as **CKD_Preprocessed_Dataset.csv**.


### 4. Initial Data Exploration

Performed an initial exploration of the dataset by:

- Displaying dataset shape.
- Displaying column names.
- Viewing the first five records.
- Checking data types.
- Generating summary statistics.
- Checking missing values.
- Checking duplicate records.
- Examining the target class distribution.


## Clinical Rationale for Missing Value Handling

Medical datasets often contain missing values because some laboratory tests may not have been performed or recorded.

To preserve data quality:

- Numeric attributes were filled using the **median**, which is less affected by outliers.
- Categorical attributes were filled using the **mode**, which preserves the most common clinical category.
- This approach minimizes information loss while maintaining reliable statistical analysis.


## Ethical Considerations

- The dataset contains only anonymized patient records.
- No personal information was collected or modified.
- The dataset is used solely for educational and analytical purposes.
- All preprocessing steps were performed without altering the medical meaning of the data.

## Tools Used

- Python
- Pandas
- NumPy
- Visual Studio Code
- Git
- GitHub


## Files Created

- Chronic_Kidney_Disease.csv
- CKD_Cleaned_Dataset.csv
- CKD_Preprocessed_Dataset.csv
- Data_Preprocessing.py.ipynb
- Data_Exploration.py.ipynb

## Week 1 Outcome

Successfully completed:

- Ethical Data Sourcing
- Data Cleaning
- Data Preprocessing
- Initial Data Exploration
- Missing Value Assessment
- Data Type Conversion
- Summary Statistics
- GitHub Version Control

  # Week 2: Biomarker Correlation and Exploratory Data Analysis (EDA)

## Objective
The objective of Week 2 is to explore the Chronic Kidney Disease (CKD) dataset and identify meaningful relationships between clinical biomarkers. Exploratory Data Analysis (EDA) helps understand the structure of the data, detect patterns, identify outliers, and prepare the dataset for machine learning model development.


## Tasks Performed

### 1. Dataset Loading
- Loaded the preprocessed Chronic Kidney Disease dataset.
- Verified the dataset structure, dimensions, and data types.
- Ensured the dataset was ready for exploratory analysis.


### 2. Biomarker Distribution Analysis
The distributions of important clinical biomarkers were analyzed using histograms and density plots.

The following biomarkers were explored:
- Age
- Blood Pressure (BP)
- Specific Gravity (SG)
- Albumin (AL)
- Hemoglobin (Hemo)

These visualizations help identify:
- Distribution of patient values
- Presence of skewness
- Outliers
- Overall variability of each biomarker


### 3. Biomarker Relationship Analysis

Scatter plots were created to study relationships between important clinical variables.

Examples include:
- Age vs Blood Pressure
- Hemoglobin vs Serum Creatinine

These plots help determine whether changes in one biomarker are associated with changes in another and provide insight into possible clinical relationships.


### 4. Correlation Analysis

A correlation matrix was generated using all numerical features in the dataset.

The correlation heatmap provides:
- Strength of relationships between variables
- Positive and negative correlations
- Identification of highly correlated features

Highly correlated variables may provide similar information and can introduce multicollinearity during machine learning model development.


### 5. Feature Selection Preparation

Based on the correlation analysis:
- Highly correlated features were identified.
- Features showing excessive correlation can be removed or carefully selected before model training.
- This step helps improve model performance, reduce redundancy, and enhance interpretability.


## Tools and Libraries Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn



## Output Files

The following outputs were generated during Week 2:

- Biomarker Distribution Plots
- Age vs Blood Pressure Scatter Plot
- Hemoglobin vs Serum Creatinine Scatter Plot
- Correlation Heatmap
- Week 2 Summary Report


## Key Observations

- Biomarker distributions provide insight into patient characteristics.
- Scatter plots reveal potential relationships between important clinical variables.
- The correlation heatmap highlights strongly associated features.
- Identifying correlated variables helps reduce multicollinearity before machine learning.
- Exploratory Data Analysis improves understanding of the dataset and supports better feature engineering.


## Conclusion

Week 2 focused on performing comprehensive Exploratory Data Analysis (EDA) on the Chronic Kidney Disease dataset. Various visualization techniques were used to understand biomarker distributions and relationships among clinical variables. Correlation analysis helped identify highly correlated features, providing valuable guidance for feature selection. These analyses establish a strong foundation for developing accurate and reliable predictive models in the next phase of the project.


Week 3: Predictive Modeling and Algorithm Selection
Objective

The primary objective of Week 3 is to develop machine learning models capable of predicting whether a patient is affected by Chronic Kidney Disease (CKD) based on clinical and laboratory biomarkers. This phase transforms the cleaned and preprocessed medical data into predictive insights by training and evaluating classification algorithms.

Dataset Splitting

Before building machine learning models, the dataset was divided into two subsets:

Training Dataset (80%) – Used to train the machine learning models.
Testing Dataset (20%) – Used to evaluate the performance of the trained models on unseen data.

The dataset was split using the train_test_split() function from Scikit-learn with a fixed random state to ensure reproducibility of the results.

Why is Train-Test Split Important?

Training and testing on separate datasets helps prevent overfitting. It allows the model to learn from one portion of the data while evaluating its ability to generalize to new, unseen patient records.

Feature Scaling

Feature scaling was applied using StandardScaler before training the Logistic Regression model.

Why Feature Scaling?

Medical features such as blood pressure, serum creatinine, blood glucose, and age have different value ranges. Standardizing these features improves model convergence and ensures that no single feature dominates the learning process.

Machine Learning Models

Two classification algorithms were implemented and compared.

1. Logistic Regression

Logistic Regression is a statistical classification algorithm that predicts the probability of a patient belonging to either the CKD or Non-CKD class.

Advantages

Easy to understand and interpret
Fast training time
Performs well on linearly separable datasets
Provides probability estimates

Purpose in this Project

Used as a baseline classification model for predicting Chronic Kidney Disease.

2. Random Forest Classifier

Random Forest is an ensemble learning algorithm that combines multiple decision trees to improve prediction accuracy.

Advantages

Handles complex relationships between medical variables
Less prone to overfitting than a single decision tree
Works well with both numerical and categorical features
Provides feature importance scores

Purpose in this Project

Used to improve predictive performance and compare results against Logistic Regression.

Hyperparameter Tuning

Hyperparameter tuning was performed to optimize model performance.

The following parameters were adjusted:

Logistic Regression
Maximum iterations (max_iter)
Regularization strength (C)
Solver
Random Forest
Number of trees (n_estimators)
Maximum tree depth (max_depth)
Minimum samples required to split a node (min_samples_split)
Minimum samples required at a leaf node (min_samples_leaf)

Hyperparameter tuning helps identify the best model configuration, leading to improved prediction accuracy and better generalization.

Handling Class Imbalance

Medical datasets often contain significantly more healthy patients than diseased patients. Such imbalance can bias machine learning models toward the majority class.

To address this issue, the Synthetic Minority Oversampling Technique (SMOTE) was applied to the training dataset.

What is SMOTE?

SMOTE generates synthetic samples of the minority class rather than simply duplicating existing records. This creates a more balanced training dataset and helps the model learn disease patterns more effectively.

Benefits of SMOTE
Reduces bias toward the majority class
Improves recall for CKD detection
Enhances overall model performance
Produces a balanced dataset for training

Note: SMOTE was applied only to the training data to prevent data leakage and ensure a fair evaluation on the testing dataset.

Model Training Workflow

The predictive modeling process followed these steps:

Load the cleaned and preprocessed CKD dataset.
Separate input features (X) and target variable (y).
Split the dataset into training and testing sets.
Apply feature scaling where required.
Balance the training dataset using SMOTE.
Train the Logistic Regression model.
Train the Random Forest Classifier.
Tune model hyperparameters.
Generate predictions on the testing dataset.
Compare the performance of both models.
Evaluation Metrics

The models were evaluated using multiple classification metrics.

Accuracy

Measures the percentage of correctly classified patient records.

Precision

Indicates how many patients predicted as CKD actually have the disease.

Recall (Sensitivity)

Measures how many actual CKD patients were correctly identified.

F1-Score

Balances Precision and Recall, making it especially useful for imbalanced medical datasets.

Confusion Matrix

Shows the number of:

True Positives (Correct CKD predictions)
True Negatives (Correct Healthy predictions)
False Positives
False Negatives

This helps understand the strengths and weaknesses of each model.

Outcome

At the end of Week 3:

Successfully divided the dataset into training and testing sets.
Built and trained Logistic Regression and Random Forest classification models.
Applied feature scaling to improve model performance.
Handled class imbalance using SMOTE.
Tuned model hyperparameters to achieve better predictive accuracy.
Evaluated both models using multiple performance metrics.
Compared the effectiveness of both algorithms in predicting Chronic Kidney Disease.
