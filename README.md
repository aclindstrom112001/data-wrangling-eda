
# Titanic Data Wrangling & EDA Project
Homework #3: Collaborative Data Wrangling & EDA 
DSE 511 - Fall 2025

Analysis of the Titanic dataset focusing on data cleaning, exploratory data analysis, PCA, and feature importance for survival prediction.

## Dataset Information
**Source:** [Titanic dataset from Seaborn](https://github.com/mwaskom/seaborn-data/blob/master/titanic.csv)
**Date Accessed:** September 5, 2025
**Size:** 55.7 kb, 892 rows, 12 columns

---

## Methods
### Data Cleaning (Cooper)
**Steps taken to clean the dataset:**
1. Inspected the dataset to identify variables with missing values.
2. Removed the Deck variable due to a majority of missing values.
3. Filled the two missing values in Embarked with the mode of the variable.
4. Imputed missing values in Age using a random distribution around the median.
5. Standardized the Sex variable to 'M' and 'F'.
6. Selected and retained variables relevant for analysis.

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

**Tools/libraries used:** 
- NumPy – Used for random distribution imputation for Age.
- Pandas – For data manipulation.
- Seaborn and Matplotlib – For data visualization.
- scikit-learn – For PCA, mutual information, and random forest computations.

---

### Exploratory Data Analysis (Amine)
**Ticket classes distribution:** 
- Class 1: 216 passengers
- Class 2: 184 passengers
- Class 3: 491 passengers

**Fare Statistics:**

|       | Price (1912) | Adjusted Price (2025, inflation-adjusted) |
|-------|--------------|-------------------------------------------|
| mean  | 32.20        | 1052.216696                               |
| std   | 49.69        | 1623.646677                               |
| min   | 0            | 0                                         |
| 25%   | 7.91         | 258.46                                    |
| 50%   | 14.45        | 472.26                                    |
| 75%   | 31           | 1012.87                                   |
| max   | 512.32       | 16739.46                                  |

![Tickets Price Distribution](pictures/price_distribution.png)

**Observations:**
- Class 3 has the largest number of passengers, reflecting the overall passenger composition.
- Ticket prices are heavily right-skewed, especially after inflation adjustment, with a few passengers paying very high fares.
- The median fares indicate that most passengers paid significantly less than the maximum fares, highlighting economic disparities.

---

**Gender and Family Distribution:** 
- Male: 577 passengers
- Female: 314 passengers
- Number of Parents and Children: 340

**Observations:**
- The passenger population is predominantly male.
- A substantial portion of passengers were traveling with family (parents and children), which could influence survival and other analyses.

---

**Age Distribution:**

|       | Age       |
|-------|-----------|
| mean  | 29.294284 |
| std   | 13.182392 |
| min   | 0.000000  |
| 25%   | 22.000000 |
| 50%   | 28.000000 |
| 75%   | 35.000000 |
| max   | 80.000000 |

![Age Distribution](pictures/age_distribution.png)

**Observations:**
- The passenger age ranges from newborns to 80 years old.
- The median age is 28, indicating a relatively young passenger population.
- The distribution is slightly right-skewed, with a few older passengers influencing the mean.

---

**Correlation Matrix:** 

![Correlation Matrix](pictures/Correlation_Matrix.png)

**Observations:**
- Strong correlations exist between SiblingsSpouses and ParentsChildren, suggesting that family groups often traveled together.
- Fare is moderately correlated with Class, reflecting higher prices for higher classes.
- Other variables show weak correlations, indicating mostly independent features.

---

**Principal Component Analysis (PCA):**

PCA computations showed that: 
 - Ticket Price holds 93% of the variance
 - Age holds 6.5% of the variance
This suggests that most of the variability in the dataset can be explained by ticket price, with age contributing a smaller portion.

---

**Feature Importance for Survival:**
Using Mutual Information and tree-based feature importance, the variables that most influence the probability of survival are:
- Gender
- Age
- Ticket Price

![Features Importances](pictures/feature_importances.png)

**Observations:**
- Gender is the most significant predictor of survival, reflecting historical accounts of the “women and children first” policy.
- Age and Ticket Price also play important roles, indicating that younger passengers and those in higher ticket classes had higher survival chances.

---

## Results

Exploratory data analysis revealed that ticket price and age captured the majority of variance in the dataset, reflecting their importance as numerical features. Gender also emerged as a key predictor of survival, likely influenced by the uneven distribution of males and females on board as well as the number of children. 

Overall, the chance of survival on the Titanic was approximately 38%.

**Reflection:**  
It was notable that socioeconomic factors, such as ticket price, strongly influenced survival, and that historical patterns like “women and children first” are clearly reflected in the data.

---

## Collaboration Notes
**Partner A (Cooper):** 
- Repository Setup
- Data Cleaning
- README formatting and editing

**Partner B (Amine):** 
- Exploratory data analysis (EDA)  
- Feature correlations computation

**Both:** 
- Documentation
- Merge conflict resolution

**Branches:**
- 'feature-cooper': Data cleaning
- 'amine-eda': EDA

---

## Reproducibility Instructions

**Python Version:**  
- Python 3.10

**How to Run:**  
1. Open Jupyter Lab or Jupyter Notebook.
2. Navigate to the `notebooks/` folder.
3. Open `eda_cooper.ipynb`.
4. Run all cells sequentially from top to bottom.  

**Dependencies:**  
Install required packages using the provided `requirements.txt`:  
```bash
pip install -r requirements.txt
```
**Special Instructions:**
- Make sure all images referenced in the notebook (e.g., pictures/price_distribution.png, pictures/Correlation_Matrix.png) are in the pictures/ folder relative to the notebook.
- Ensure the dataset (titanic.csv) is located in the same directory as the notebook or update the file path in the notebook accordingly.
- To reproduce the random imputations for missing Age values and PCA results, set a random seed in the notebook, e.g.:
```python
import numpy as np
np.random.seed(42)
```

## Merge Conflict Reflection
Briefly describe the merge conflict you created and how you resolved it.
