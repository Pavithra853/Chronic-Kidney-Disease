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


# Week 3: Predictive Modeling and Algorithm Selection

## 📌 Objective

The objective of Week 3 is to develop and compare machine learning models capable of predicting **Chronic Kidney Disease (CKD)** using patient clinical and laboratory data. This phase focuses on implementing classification algorithms, optimizing their performance, and handling class imbalance to improve prediction accuracy.

---

## 📂 Dataset Splitting

The cleaned dataset was divided into two subsets before training the machine learning models.

- **Training Set (80%)** – Used to train the models.
- **Testing Set (20%)** – Used to evaluate the trained models on unseen data.

The dataset was split using Scikit-learn's `train_test_split()` function with a fixed random state to ensure reproducibility.

### Why Train-Test Split?

Separating the dataset prevents overfitting and allows the models to be evaluated on new data, providing a realistic estimate of their performance.

---

## ⚙️ Feature Scaling

Feature scaling was applied using **StandardScaler** before training the Logistic Regression model.

### Why Feature Scaling?

Medical attributes such as blood pressure, blood glucose, age, and serum creatinine have different value ranges. Standardization ensures that all features contribute equally during model training and improves convergence.

---

## 🤖 Machine Learning Models

Two supervised classification algorithms were implemented and compared.

### 1. Logistic Regression

Logistic Regression is a statistical classification algorithm used to estimate the probability that a patient belongs to the CKD or Non-CKD class.

#### Advantages

- Simple and interpretable
- Fast training process
- Suitable for binary classification
- Produces probability estimates

#### Purpose

Used as the baseline classification model for Chronic Kidney Disease prediction.

---

### 2. Random Forest Classifier

Random Forest is an ensemble learning algorithm that combines multiple decision trees to improve prediction accuracy and reduce overfitting.

#### Advantages

- Handles complex feature relationships
- Works well with medical datasets
- Less prone to overfitting
- Provides feature importance scores

#### Purpose

Used to improve prediction accuracy and compare its performance with Logistic Regression.

---

## 🎯 Hyperparameter Tuning

Hyperparameter tuning was performed to optimize the performance of both classification models.

### Logistic Regression

The following parameters were tuned:

- `max_iter`
- `C` (Regularization Strength)
- `solver`

### Random Forest

The following parameters were tuned:

- `n_estimators`
- `max_depth`
- `min_samples_split`
- `min_samples_leaf`

Hyperparameter tuning improves model generalization and helps identify the optimal model configuration.

---

## ⚖️ Handling Class Imbalance

Medical datasets frequently contain more healthy patients than diseased patients. Such imbalance can bias machine learning models toward the majority class.

To overcome this issue, **SMOTE (Synthetic Minority Oversampling Technique)** was applied to the training dataset.

### What is SMOTE?

SMOTE generates synthetic examples for the minority class instead of duplicating existing records. This creates a balanced dataset and helps the models learn disease patterns more effectively.

### Benefits of SMOTE

- Reduces bias toward the majority class
- Improves CKD detection
- Increases Recall and F1-Score
- Produces a balanced training dataset

> **Note:** SMOTE was applied only to the training data to prevent data leakage.

---

## 🔄 Model Training Workflow

The following workflow was implemented:

1. Load the cleaned CKD dataset.
2. Separate features (`X`) and target variable (`y`).
3. Split the dataset into training and testing sets.
4. Apply feature scaling where required.
5. Balance the training data using SMOTE.
6. Train the Logistic Regression model.
7. Train the Random Forest model.
8. Tune model hyperparameters.
9. Predict outcomes using the testing dataset.
10. Compare the performance of both models.

---

## 📊 Model Evaluation

The trained models were evaluated using the following performance metrics:

### Accuracy

Measures the percentage of correctly classified patient records.

### Precision

Measures how many patients predicted as CKD actually have the disease.

### Recall (Sensitivity)

Measures how many actual CKD patients were correctly identified.

### F1-Score

Provides a balanced evaluation by combining Precision and Recall.

### Confusion Matrix

The Confusion Matrix summarizes:

- True Positives (TP)
- True Negatives (TN)
- False Positives (FP)
- False Negatives (FN)

This provides a detailed understanding of model performance.

---

## ✅ Week 3 Outcomes

By the end of Week 3, the following tasks were successfully completed:

- Split the dataset into training and testing subsets.
- Built and trained Logistic Regression and Random Forest classifiers.
- Applied feature scaling using StandardScaler.
- Addressed class imbalance using SMOTE.
- Tuned model hyperparameters for improved performance.
- Evaluated both models using multiple classification metrics.
- Compared model performance to identify the most effective algorithm for CKD prediction.

---

## 🛠️ Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- imbalanced-learn (SMOTE)
- Matplotlib
- Seaborn
- Jupyter Notebook

---

## 📝 Conclusion

Week 3 focused on implementing supervised machine learning techniques for Chronic Kidney Disease prediction. Two classification models—Logistic Regression and Random Forest—were trained and optimized through hyperparameter tuning. Class imbalance was addressed using SMOTE, ensuring fair model learning. The models were evaluated using standard classification metrics, providing a solid foundation for model evaluation, comparison, and deployment in Week 4.


