# Loan Default & Credit Risk Analysis

## Project Overview

This project focuses on analyzing loan default and credit risk patterns using *Python* and *Microsoft Power BI*.

The project analyzes customer demographics, income, credit scores, loan amounts, interest rates, debt-to-income ratio, employment information, previous defaults, loan types, and other financial factors to identify patterns associated with loan default.

The analysis transforms financial data into meaningful insights that can support credit-risk monitoring, customer risk assessment, loan approval decisions, and financial decision-making.

> *Note:* The dataset used in this academic project is synthetic and is intended for educational and analytical purposes only.

---

## Project Objectives

The main objectives of this project are:

- Analyze customer and loan-related data.
- Identify patterns associated with loan default.
- Study the relationship between credit score and loan default.
- Analyze default rates across different loan types.
- Analyze default rates by employment status and education.
- Study the relationship between income and loan amount.
- Analyze the relationship between debt-to-income ratio and default patterns.
- Examine previous defaults and their relationship with current default status.
- Identify high-risk customer segments.
- Create meaningful data visualizations using Python.
- Build an interactive credit-risk dashboard using Power BI.
- Generate business insights and recommendations for credit-risk management.

---

## Technologies Used

### Programming and Data Analysis

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook / Google Colab

### Business Intelligence

- Microsoft Power BI
- Power Query
- DAX

### Other Tools

- Git
- GitHub
- CSV / Excel

---

## Dataset

The project uses a *synthetic loan and credit-risk dataset* created for academic and educational analysis.

The dataset contains information about customers, loans, financial characteristics, credit scores, employment details, and loan default status.

### Dataset Features

| Column | Description |
|---|---|
| Customer_ID | Unique customer identifier |
| Gender | Customer gender |
| Age | Customer age |
| Education | Education level |
| Employment_Status | Employment category |
| Marital_Status | Customer marital status |
| Dependents | Number of dependents |
| Annual_Income | Customer annual income |
| Credit_Score | Customer credit score |
| Existing_Loans | Number of existing loans |
| Loan_ID | Unique loan identifier |
| Loan_Type | Type of loan |
| Loan_Amount | Loan amount |
| Loan_Term_Months | Loan repayment term in months |
| Interest_Rate | Loan interest rate |
| Monthly_Installment | Monthly loan installment |
| Debt_to_Income_Ratio | Debt-to-income ratio |
| Employment_Years | Years of employment |
| Previous_Defaults | Number of previous defaults |
| Credit_History | Customer credit history |
| Property_Ownership | Property ownership status |
| Region | Customer region |
| Loan_Status | Current loan status |
| Default_Status | Default or Non-Default status |

---

## Data Cleaning and Preprocessing

The raw dataset was inspected and prepared using Python.

The following preprocessing steps were performed:

1. Loaded the raw CSV dataset.
2. Examined the first and last records.
3. Checked dataset shape and column names.
4. Inspected data types.
5. Checked missing values.
6. Identified duplicate records.
7. Checked unique values in categorical columns.
8. Handled missing numerical values using appropriate statistical methods.
9. Handled missing categorical values using suitable categorical replacement methods.
10. Removed duplicate records where required.
11. Validated numerical columns.
12. Checked potential outliers using the IQR method.
13. Created credit-score categories.
14. Created income groups.
15. Created a binary default flag.
16. Prepared the final cleaned dataset for analysis and Power BI.

### Derived Features

#### Credit Score Group

Credit scores were categorized into:

- Poor: Below 580
- Fair: 580–669
- Good: 670–739
- Excellent: 740 and above

#### Income Group

Customers were grouped into income categories based on the distribution of annual income.

#### Default Flag

The default status was converted into a numerical flag for analytical purposes:

- 1 = Default
- 0 = Non-Default

---

## Exploratory Data Analysis

The analysis focuses on the following areas.

### Customer Analysis

- Customer demographics
- Age distribution
- Gender distribution
- Education
- Employment status
- Marital status
- Number of dependents
- Property ownership
- Regional distribution

### Financial Analysis

- Annual income
- Loan amount
- Interest rate
- Monthly installment
- Debt-to-income ratio
- Existing loans
- Loan term

### Credit Risk Analysis

- Credit score
- Credit score groups
- Previous defaults
- Credit history
- Loan default status
- Default rate

### Loan Analysis

- Loan types
- Loan amounts
- Loan terms
- Regional loan distribution
- Default rate by loan type

---

# Python Visualizations

The project includes the following 15 major visualizations.

### 1. Loan Default Distribution

Shows the proportion of defaulted and non-defaulted loans.

### 2. Loan Count by Loan Type

Compares the number of loans across different loan types.

### 3. Default Rate by Loan Type

Shows the percentage of defaulted loans for each loan type.

### 4. Default Rate by Employment Status

Analyzes loan default patterns across different employment categories.

### 5. Default Rate by Education

Compares default rates among different education levels.

### 6. Credit Score Distribution

Shows the distribution of customer credit scores.

### 7. Loan Amount Distribution

Displays the distribution of loan amounts.

### 8. Annual Income Distribution

Shows the distribution of customer annual income.

### 9. Credit Score vs Loan Amount

Examines the relationship between credit score and loan amount while differentiating default status.

### 10. Income vs Loan Amount

Analyzes the relationship between annual income and loan amount.

### 11. Loan Amount by Default Status

Compares loan amounts between defaulted and non-defaulted customers.

### 12. Credit Score by Default Status

Compares credit scores between defaulted and non-defaulted customers.

### 13. Debt-to-Income Ratio by Default Status

Analyzes DTI patterns across default categories.

### 14. Default Rate by Income Group

Compares default rates across different income groups.

### 15. Correlation Heatmap

Shows correlations between important numerical variables such as:

- Age
- Dependents
- Annual Income
- Credit Score
- Existing Loans
- Loan Amount
- Loan Term
- Interest Rate
- Monthly Installment
- Debt-to-Income Ratio
- Employment Years
- Previous Defaults
- Default Flag

---

# Power BI Dashboard

## Loan Default & Credit Risk Analytics Dashboard

An interactive Power BI dashboard was developed to provide a visual overview of loan and credit-risk performance.

### Key Performance Indicators

The dashboard includes:

- Total Customers
- Total Loans
- Defaulted Loans
- Default Rate %
- Average Loan Amount
- Average Credit Score
- Average Annual Income

### Power BI Visuals

The dashboard contains:

1. Default Distribution
2. Default Rate by Loan Type
3. Default Rate by Employment Status
4. Default Rate by Credit Score Group
5. Default Rate by Income Group
6. Loan Amount by Loan Type
7. Average Loan Amount by Region
8. Credit Score Distribution
9. Income vs Loan Amount
10. Loan Details Table
11. Default Distribution / Trend Analysis

### Dashboard Filters

Interactive slicers include:

- Gender
- Education
- Employment Status
- Loan Type
- Region
- Default Status
- Credit Score Group

---

# DAX Measures

The following DAX measures are used in the Power BI dashboard.

### Total Customers

DAX
Total Customers =
DISTINCTCOUNT(Loan_Credit_Risk_Cleaned[Customer_ID])


### Total Loans

DAX
Total Loans =
DISTINCTCOUNT(Loan_Credit_Risk_Cleaned[Loan_ID])


### Defaulted Loans

DAX
Defaulted Loans =
CALCULATE(
    COUNTROWS(Loan_Credit_Risk_Cleaned),
    Loan_Credit_Risk_Cleaned[Default_Status] = "Default"
)


### Non-Defaulted Loans

DAX
Non-Defaulted Loans =
CALCULATE(
    COUNTROWS(Loan_Credit_Risk_Cleaned),
    Loan_Credit_Risk_Cleaned[Default_Status] = "Non-Default"
)


### Default Rate

DAX
Default Rate % =
DIVIDE(
    [Defaulted Loans],
    [Total Loans],
    0
)


### Average Loan Amount

DAX
Average Loan Amount =
AVERAGE(Loan_Credit_Risk_Cleaned[Loan_Amount])


### Average Credit Score

DAX
Average Credit Score =
AVERAGE(Loan_Credit_Risk_Cleaned[Credit_Score])


### Average Annual Income

DAX
Average Annual Income =
AVERAGE(Loan_Credit_Risk_Cleaned[Annual_Income])


---

# Project Structure

text
LOAN-DEFAULT-CREDIT-RISK-ANALYSIS/
│
├── Dataset/
│   ├── Loan_Credit_Risk_Raw.csv
│   ├── Loan_Credit_Risk_Cleaned.csv
│   └── Data_Dictionary.csv
│
├── Python/
│   └── Loan_Credit_Risk_Analysis.ipynb
│
├── PowerBI/
│   └── Loan_Credit_Risk_Dashboard.pbix
│
├── Visualizations/
│   ├── 01_Default_Distribution.png
│   ├── 02_Loan_Count_by_Type.png
│   ├── 03_Default_Rate_by_Type.png
│   ├── 04_Default_Rate_by_Employment.png
│   ├── 05_Default_Rate_by_Education.png
│   ├── 06_Credit_Score_Distribution.png
│   ├── 07_Loan_Amount_Distribution.png
│   ├── 08_Income_Distribution.png
│   ├── 09_Credit_Score_vs_Loan_Amount.png
│   ├── 10_Income_vs_Loan_Amount.png
│   ├── 11_Loan_Amount_by_Default.png
│   ├── 12_Credit_Score_by_Default.png
│   ├── 13_DTI_by_Default.png
│   ├── 14_Default_Rate_by_Income.png
│   └── 15_Correlation_Heatmap.png
│
├── Report/
│   └── Loan_Credit_Risk_Project_Report.pdf
│
├── README.md
└── .gitignore


---

# Business Insights

The analysis is designed to identify important credit-risk patterns such as:

- Differences in default rates across loan types.
- Differences in default rates across employment categories.
- Relationship between credit score and default status.
- Relationship between debt-to-income ratio and default status.
- Relationship between previous defaults and current default status.
- Differences in default rates across income groups.
- Loan amount patterns among defaulted and non-defaulted customers.
- Regional differences in loan and default distribution.
- Customer segments that may require additional credit-risk monitoring.

> *Note:* Actual numerical findings should be taken from the final cleaned dataset and analysis results rather than being assumed in advance.

---

# Recommendations

Based on the analytical framework, financial institutions can consider:

1. Using credit-score-based risk segmentation.
2. Monitoring customers with high debt-to-income ratios.
3. Reviewing previous default history during credit assessment.
4. Applying additional risk checks for high-risk loan segments.
5. Monitoring loan amounts relative to customer income.
6. Developing targeted strategies for customers with higher observed default rates.
7. Using interactive dashboards for continuous credit-risk monitoring.
8. Combining multiple risk indicators instead of relying on a single variable.
9. Regularly monitoring changes in customer and loan risk profiles.
10. Using data-driven analysis to support responsible lending decisions.

---

# How to Run the Python Project

## Step 1: Clone the Repository

bash
git clone https://github.com/Ganesh-sanju/LOAN-DEFAULT-CREDIT-RISK-ANALYSIS.git


## Step 2: Open the Project

bash
cd LOAN-DEFAULT-CREDIT-RISK-ANALYSIS


## Step 3: Install Required Libraries

bash
pip install pandas numpy matplotlib seaborn jupyter


## Step 4: Open Jupyter Notebook

bash
jupyter notebook


Open:

text
Python/Loan_Credit_Risk_Analysis.ipynb


## Step 5: Run the Notebook

Run the notebook cells from beginning to end.

The notebook performs:

- Data loading
- Data inspection
- Data cleaning
- Data preprocessing
- Feature engineering
- Exploratory data analysis
- Statistical analysis
- Visualization
- Credit-risk analysis

---

# Power BI Instructions

1. Open *Microsoft Power BI Desktop*.
2. Load the cleaned dataset:

text
Dataset/Loan_Credit_Risk_Cleaned.csv


3. Check the data types.
4. Create the required DAX measures.
5. Build the required dashboard visuals.
6. Add slicers and filters.
7. Format the dashboard.
8. Save the Power BI file as:

text
PowerBI/Loan_Credit_Risk_Dashboard.pbix


---

# Project Report

The project report contains:

- Project Introduction
- Problem Statement
- Project Objectives
- Dataset Description
- Data Dictionary
- Tools and Technologies
- Data Cleaning
- Exploratory Data Analysis
- Python Visualizations
- Power BI Dashboard
- DAX Measures
- Business Insights
- Recommendations
- Conclusion
- Limitations
- Future Enhancements

The final report is stored in:

text
Report/Loan_Credit_Risk_Project_Report.pdf


---

# Skills Demonstrated

This project demonstrates practical skills in:

- Python
- Pandas
- NumPy
- Data Cleaning
- Data Preprocessing
- Exploratory Data Analysis
- Data Visualization
- Statistical Analysis
- Credit Risk Analysis
- Power BI
- Power Query
- DAX
- Dashboard Development
- Business Intelligence
- Business Analysis
- Git
- GitHub
- Technical Documentation

---

# Limitations

- The dataset is synthetic and may not represent actual banking customers.
- The analysis identifies associations and patterns, not causal relationships.
- The dataset may not contain every factor used by real financial institutions.
- Real-world credit-risk models require larger and validated datasets.
- Regulatory, economic, and market factors are not fully represented.
- The results are intended for academic and educational purposes.

---

# Future Enhancements

Future versions of this project could include:

- Machine Learning-based loan default prediction.
- Logistic Regression for probability of default.
- Random Forest classification.
- XGBoost classification.
- Customer risk scoring.
- Feature importance analysis.
- Model evaluation using accuracy, precision, recall, F1-score, and ROC-AUC.
- Customer segmentation using clustering.
- Real-time Power BI data refresh.
- Advanced credit-risk monitoring.
- Explainable AI for credit-risk decisions.
- Integration with validated real-world financial datasets.

---

# Project Information

*Project Title:* Loan Default & Credit Risk Analysis

*Domain:* Data Analytics / Credit Risk / Business Intelligence

*Programming Language:* Python

*Data Analysis Libraries:* Pandas, NumPy

*Visualization Libraries:* Matplotlib, Seaborn

*Business Intelligence Tool:* Microsoft Power BI

*Data Format:* CSV

*Dataset Type:* Synthetic / Educational

*Repository:* GitHub

---

# Disclaimer

This project is developed for *academic and educational purposes*.

The dataset is synthetic and should not be used for actual financial, lending, credit approval, investment, or banking decisions.

The analysis demonstrates data analytics and business intelligence techniques. It identifies patterns and associations in the dataset and does not constitute professional financial advice.

---

# Author

*GitHub:*  
https://github.com/Ganesh-sanju

---

## Acknowledgement

This project was developed as an academic data analytics and business intelligence project using Python and Microsoft Power BI.

---
 *If you find this project useful, consider giving the repository a star.*
