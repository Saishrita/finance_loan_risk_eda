# Lending Club Loan Analysis - Exploratory Data Analysis

## 📊 Project Overview
This project conducts a comprehensive Exploratory Data Analysis (EDA) on Lending Club's loan data to understand factors influencing loan performance and credit risk.

## 📋 Selected Features for Analysis

We selected 20 key features that align with industry-standard credit risk assessment frameworks:

### 💰 Loan Amount & Terms
- **`loan_amnt`**: The total amount of the loan applied for by the borrower
- **`int_rate`**: Interest rate on the loan (key pricing variable)  
- **`installment`**: Monthly payment amount owed by borrower
- **`term`**: Loan duration (e.g., "36 months", "60 months")

### 💳 Borrower Financial Capacity
- **`annual_inc`**: Borrower's self-reported annual income
- **`dti`**: Debt-to-Income ratio = Total monthly debt payments / Monthly income
  - *Critical metric measuring borrower's ability to manage payments*

### 📊 Credit History & Scores
- **`fico_range_low`**: Lower end of borrower's FICO score range
- **`fico_range_high`**: Upper end of borrower's FICO score range  
- **`open_acc`**: Number of open credit lines (credit cards, loans, etc.)
- **`total_acc`**: Total number of credit lines ever opened
- **`pub_rec`**: Number of derogatory public records (bankruptcies, tax liens, etc.)

### 🔄 Credit Utilization & Behavior
- **`revol_bal`**: Total credit revolving balance (credit card debt)
- **`revol_util`**: Revolving line utilization rate = Credit used / Total credit available
  - *Key risk indicator: High utilization (>30%) signals credit stress*

### 👤 Borrower Demographics & Loan Context
- **`home_ownership`**: Home ownership status (RENT, MORTGAGE, OWN, OTHER)
- **`emp_length`**: Employment length in years
- **`verification_status`**: Whether income was verified by lender
- **`purpose`**: Loan purpose (debt consolidation, home improvement, car, etc.)
- **`addr_state`**: Borrower's state (geographic risk factor)
- **`issue_d`**: Loan issuance date (for time series analysis)

### 🎯 Target Variable
- **`loan_status`**: **Most important column** - shows loan performance:
  - "Current", "Fully Paid" → Performing loans
  - "Charged Off", "Default" → Non-performing loans
  - "Late" → Potential future defaults

## 🎯 Feature Selection Rationale

These features align with the **5 C's of Credit** framework:
- **Character**: Credit history (`fico_score`, `pub_rec`, credit behavior)
- **Capacity**: Ability to pay (`annual_inc`, `dti`, `installment`)  
- **Capital**: Financial reserves (`home_ownership`, `emp_length`)
- **Collateral**: Loan security (`loan_amnt`, implied)
- **Conditions**: Loan purpose & terms (`purpose`, `term`, `int_rate`)

## 📁 Dataset Information
- **Source**: Lending Club accepted loans dataset (2007-2018)
- **Original Size**: 36,032 rows × 151 columns
- **Final Working Dataset**: 33,871 rows × 20 columns
- **Data Period**: 2007-2018

## 🔧 Data Processing Steps

1. **Column Selection**: Chose 20 relevant features from original 151 columns
2. **Data Cleaning**: Standardized column names and handled missing values
3. **Missing Value Treatment**: Removed rows with missing critical financial data
4. **Quality Assurance**: Conducted comprehensive data quality checks

## 📈 Analysis Approach

The EDA focuses on:
- Loan performance patterns and default drivers
- Borrower risk profiling
- Credit policy implications
- Investment decision insights

## 🛠 Technical Stack
- Python 3.x
- Pandas & NumPy (Data manipulation)
- Matplotlib & Seaborn (Visualization)
- Colab Notebook
