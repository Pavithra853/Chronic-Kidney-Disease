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

