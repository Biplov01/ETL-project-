# ETL-project-
ETL on US healthcare
# Synthetic Data ETL Project

This project generates a synthetic dataset, transforms the data, and stores it in a SQLite database. The dataset contains health-related information, and this README outlines the steps for generating, transforming, and loading the data into a database.

## Table of Contents
- [Project Overview](#project-overview)
- [Setup Instructions](#setup-instructions)
- [Synthetic Data Generation](#synthetic-data-generation)
- [Data Transformation](#data-transformation)
- [Database Storage](#database-storage)
- [How to Run](#how-to-run)
- [License](#license)

## Project Overview
The main objective of this project is to:
1. **Generate synthetic health data**.
2. **Transform** the data (including encoding categorical variables and scaling numerical features).
3. **Load** the transformed data into an SQLite database for future analysis.

### Dataset Information:
- **Age**: Random values between 20 and 70.
- **Income**: Random values between $20,000 and $120,000.
- **Education Level**: Integer values representing education levels (1: High School, 2: Bachelor, 3: Master, 4: PhD).
- **Health Score**: Random values between 50 and 100.
- **Health Status**: Categorical variable ('good', 'bad') based on health score.

## Setup Instructions

### Prerequisites
Ensure you have the following installed:
- Python 3.x
- Required Python libraries (can be installed via `requirements.txt`)

### Required Libraries
- `pandas`
- `numpy`
- `sklearn`
- `sqlite3` (part of the Python Standard Library)
- `os` (part of the Python Standard Library)

Install the dependencies using the following command:

```bash
pip install pandas numpy scikit-learn
Directory Structure
css
data science projects/
    ├── synthetic_health_data.csv
    ├── synthetic_health_data.db
    ├── main.py
    └── README.md
Synthetic Data Generation
We generate a dataset with 1000 rows, containing random values for health-related attributes such as age, income, education level, and health score. The synthetic data is saved as a CSV file.

Sample of the Dataset
Age	Income	Education_Level	Health_Score	Health_Status
30	65000	2	85.5	good
45	45000	1	65.7	bad
55	85000	4	90.2	good
The generated data is stored in D:\data science projects\synthetic_health_data.csv.

Data Transformation
The transformation steps include:

Label Encoding: The Health_Status column is converted from good/bad to numerical values (1 for good and 0 for bad).
Feature Scaling: Age, Income, and Health_Score are standardized using StandardScaler.
Database Storage
The transformed data is loaded into a SQLite database (synthetic_health_data.db), where a table health_data is created to store the data. The database file is saved in the same directory as the project.

Database Schema
Age: REAL
Income: REAL
Education_Level: INTEGER
Health_Score: REAL
Health_Status_Encoded: INTEGER
The table stores the transformed features and makes the data queryable for future analysis.

How to Run
Clone the repository or download the files.
Ensure all dependencies are installed (as listed in the Setup Instructions).
Run the Python script main.py:
bash

python main.py
This script:

Generates the synthetic dataset.
Saves the data as a CSV file (synthetic_health_data.csv).
Transforms the data (label encoding and scaling).
Loads the transformed data into the SQLite database (synthetic_health_data.db).
To verify that the data has been loaded into the database, you can query the database using SQLite or the provided sample query in main.py.
