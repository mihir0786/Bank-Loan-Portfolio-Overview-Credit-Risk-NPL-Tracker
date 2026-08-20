# Data Dictionary

## Fact_Loans

| Column | Description |
|---|---|
| LoanID | Unique loan account identifier |
| CustomerID | Customer identifier linked to Dim_Customer |
| BranchID | Branch identifier linked to Dim_Branch |
| ProductID | Product identifier linked to Dim_Product |
| DisbursementDate | Date when the loan was issued |
| LoanAmount | Original loan amount disbursed |
| InterestRate | Interest rate assigned to the loan |
| TermMonths | Loan repayment term in months |
| LoanStatus | Current loan status such as Active, Closed, or Paid Off |
| OutstandingBalance | Current amount still owed by borrower |
| DaysPastDue | Number of days payment is overdue |
| DefaultFlag | Indicates whether loan is classified as defaulted |
| RiskRating | Risk category such as Low, Medium, or High |
| ProvisionAmount | Simplified reserve estimate for possible credit losses |
| RecoveryAmount | Amount recovered from defaulted or high-risk loan |
| CollateralValue | Estimated collateral value for secured loan products |
| DelinquencyBucket | DPD grouping: Current, 1-29, 30-59, 60-89, 90+ DPD |

## Dim_Branch

| Column | Description |
|---|---|
| BranchID | Unique branch identifier |
| BranchName | Branch name |
| City | Branch city |
| State | Branch state |
| Region | Geographic region |

## Dim_Product

| Column | Description |
|---|---|
| ProductID | Unique product identifier |
| LoanType | Type of loan product |
| ProductCategory | Product grouping |
| SecuredFlag | Indicates whether product is secured or unsecured |

## Dim_Customer

| Column | Description |
|---|---|
| CustomerID | Unique customer identifier |
| Age | Customer age |
| Income | Customer income |
| EmploymentType | Employment classification |
| CreditScore | Synthetic credit score |
| CreditScoreBand | Credit score grouped into bands |

## Fact_BankFinancials

| Column | Description |
|---|---|
| MonthStartDate | First day of reporting month |
| BranchID | Branch identifier |
| InterestIncome | Monthly interest income |
| FeeIncome | Monthly fee income |
| OperatingExpense | Monthly operating expense |
| LoanLossProvision | Monthly provision expense |
