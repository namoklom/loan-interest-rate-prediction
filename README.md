# Loan Interest Rate & Borrower Risk Analysis

| Name            | Role              | LinkedIn                                      |
|-----------------|-------------------|-----------------------------------------------|
| Jason Emmanuel  | Data Analyst | [linkedin.com/in/jasoneml](https://www.linkedin.com/in/jasoneml/) |

This project analyzes a **fintech loan dataset** (Bondora P2P Loans) to explore the factors affecting **loan interest rates** and identify **borrower risk**. It includes data cleaning, exploratory data analysis (EDA), and basic predictive modeling to provide insights into lending behavior.

---

## 🗂 Dataset Features

The dataset contains the following key attributes:

- **VerificationType:** Method used to verify loan application (e.g., verified, not verified)  
- **Age:** Borrower’s age (in years)  
- **AppliedAmount:** Amount borrower requested  
- **Amount:** Amount approved for the loan  
- **Interest:** Loan interest rate (target variable)  
- **LoanDuration:** Duration of loan in months  
- **Education:** Borrower’s education level (categorical)  
- **EmploymentDurationCurrentEmployer:** Years working with current employer  
- **HomeOwnershipType:** Borrower’s home ownership status (e.g., rent, own)  
- **IncomeTotal:** Borrower’s total income  
- **ExistingLiabilities:** Number of current liabilities  
- **RefinanceLiabilities:** Total liabilities after refinancing  
- **Rating:** Credit rating score/category  
- **NoOfPreviousLoansBeforeLoan:** Number of previous loans taken before current loan  
- **AmountOfPreviousLoansBeforeLoan:** Total amount of previous loans  

---

## 🧹 Data Cleaning & Preparation

- Removed rows with missing or invalid data for accurate analysis  
- Set **LoanId** as the dataframe index for easy referencing  
- Converted categorical features as needed for analysis  

---

## 📈 Exploratory Data Analysis (EDA)

- **Interest Rate Statistics:**  
  - Mean interest rate: ~27.3%  
  - Standard deviation: ~18.0%  
- **Loan Amount Analysis:**  
  - Most loans approved at or near requested amount  
  - Approximately 2.75% loans approved for less than requested amount  
- **Risky Borrower Definition:**  
  - Debt-to-income ratio ≥ 0.35  
  - Employment duration ≤ 1 year  
- **Risky Loan Insights:**  
  - 15.9% of loans flagged as risky based on above criteria  
  - Risky loans have higher average interest rates (~28.9%) compared to non-risky (~27.0%)  
- **Visualization Highlights:**  
  - Boxplots showing interest rate variation by education level  
  - Scatterplots and correlation heatmaps show weak but present relationships between interest and numeric features  
- **Correlation Findings:**  
  - Interest rate weakly negatively correlated with amount of previous loans (-0.175)  
  - Other numeric features have very low correlation  

---

## 🧮 Predictive Modeling

- Performed **simple linear regression** using `AmountOfPreviousLoansBeforeLoan` to predict `Interest`  
- Model is statistically significant (p < 0.05) but explains only about 3% of the variance (R² ≈ 0.03)  
- Suggests prior loan amount alone is not a strong predictor of interest rates  
- Indicates need for multivariate models including categorical variables and other features  

---

## 🔍 Conclusions & Future Work

- Some borrower characteristics correlate with loan interest rates and risk but overall relationships are weak  
- Risk assessment using debt-to-income and employment duration is effective in identifying higher-risk borrowers  
- Predictive modeling requires more complex, multivariate approaches to improve accuracy  
- Next steps:  
  - Incorporate more features into regression or machine learning models  
  - Experiment with classification models for risk prediction  
  - Explore advanced feature engineering and model tuning  

---

## 🛠 Tools & Libraries Used

| Tool / Library   | Purpose                                  |
|------------------|------------------------------------------|
| Python           | Programming language                      |
| Pandas           | Data manipulation and cleaning            |
| NumPy            | Numerical computations                     |
| Matplotlib       | Data visualization                        |
| Seaborn          | Statistical data visualization             |
| Scikit-learn     | Machine learning algorithms                |
| Statsmodels      | Statistical modeling and tests              |
| Jupyter Notebook | Interactive coding environment              |

---

## 📂 How to Use

1. Clone this repository  
2. Open the Jupyter Notebook (`loan_analysis.ipynb`) for step-by-step code and explanations  
3. Explore the dataset (`bondora_data.csv`) included or download it from the source  
4. Modify or extend analyses as needed  
