# Loan Interest Rate & Borrower Risk Analysis

## 👤 Author

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

## 📊 Visualizations

![image](https://github.com/user-attachments/assets/199bc93f-8a40-430a-8b96-53c7fb04484b)

The boxplot illustrates the distribution of interest rates across different education levels—Basic, Primary, Secondary, Higher, and Vocational. Each box represents the interquartile range (IQR), with the horizontal line inside marking the median interest rate. The whiskers extend to 1.5 times the IQR, and the dots outside the whiskers indicate outliers, which are numerous across all education levels. While the central tendency (median) of interest rates is relatively similar across groups, there is a wide spread and a large number of high outliers, especially beyond the 100% interest rate mark. This suggests substantial variability in interest rates, regardless of education level.

![image](https://github.com/user-attachments/assets/0a160887-62fd-4295-b878-507232f07cb0)

The scatter plots illustrate the relationships between interest rate and four variables: loan duration, total income, amount of previous loans before the current loan, and debt-to-income ratio. Overall, the data exhibits a negative correlation trend, where higher values of the x-axis variables generally correspond to lower interest rates. In particular, as loan duration, income, previous loan amount, or debt-to-income increases, interest rates tend to decrease and become more concentrated below 50%. However, there is considerable dispersion and the presence of outliers, especially in lower ranges, indicating variability and suggesting that other factors might also be influencing interest rates.

![image](https://github.com/user-attachments/assets/11c83bc2-30eb-4a98-95e6-e19660db4720)

The scatter plot with a fitted regression line shows the relationship between the amount of previous loans before the current loan and the interest rate, modeled using simple linear regression. The negative slope of the red line of best fit indicates a weak but noticeable inverse relationship: as the amount of previous loans increases, the interest rate tends to decrease. However, the wide spread of data points and concentration of high interest rates at lower loan amounts suggest that the relationship is not strictly linear and may be influenced by other factors or better modeled with a non-linear approach.

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
