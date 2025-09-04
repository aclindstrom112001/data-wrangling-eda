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

| Column        | Description |
|---------------|-------------|
| survived      | Survival status (0 = No, 1 = Yes) |
| pclass        | Passenger class (1 = 1st, 2 = 2nd, 3 = 3rd) |
| sex           | Gender (M/F) |
| age           | Age in years |
| sibsp         | Number of siblings/spouses aboard |
| parch         | Number of parents/children aboard |
| fare          | Passenger fare |
| embarked      | Port of embarkation (C = Cherbourg, Q = Queenstown, S = Southampton) |
| class         | Passenger class as string (First, Second, Third) |
| who           | Person type (man, woman, child) |
| adult_male    | Boolean flag for adult male |
| deck          | Deck level (A–G, NaN if unknown) |
| embark_town   | Town of embarkation |
| alive         | Survival status as string (yes/no) |
| alone         | Boolean flag if traveling alone |

**Note:** The dataset has been cleaned in this project:
- Missing values for `age` were filled using random imputation from a normal distribution (10%) and median imputation.  
- `sex` has been standardized to `"M"` and `"F"`.  
- Unnecessary columns were removed to simplify EDA.