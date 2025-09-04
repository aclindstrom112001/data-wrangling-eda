# hw3-data-wrangling-eda

# Titanic Data Wrangling & EDA Project

## Project Overview
This project explores the Titanic passenger dataset to practice data wrangling and exploratory data analysis (EDA).
The dataset provides information about passengers, such as age, gender ticket class, and survival status.

Our team responsibilities: 
- **Cooper (Data Cleaning):** Handle missing values, rename variables, select useful subset
- **Amine (EDA):** Perform descriptive statistics, and create visualizations
- **Both:** Documentation, commits, and merging pull requests

## Dataset

**Source:** [Titanic dataset from Seaborn](https://github.com/mwaskom/seaborn-data/blob/master/titanic.csv)

The dataset contains information about passengers on the Titanic, including demographic, travel, and survival information.

**Variables:**

| Column            | Description |
|------------------|-------------|
| Survived          | Survival status (0 = No, 1 = Yes) |
| Class             | Passenger class (1 = 1st, 2 = 2nd, 3 = 3rd) |
| Sex               | Gender (M/F) |
| Age               | Age in years (missing values filled via random imputation + median) |
| SiblingsSpouses   | Number of siblings/spouses aboard |
| ParentsChildren   | Number of parents/children aboard |
| Fare              | Passenger fare |

**Note:** The dataset has been cleaned in this project:
- Missing values for `age` were filled using random imputation from a normal distribution (10%) and median imputation.  
- `sex` has been standardized to `"M"` and `"F"`.  
- Unnecessary columns were removed to simplify EDA.