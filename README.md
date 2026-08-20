# Bank Loan Portfolio Overview & Credit Risk NPL Tracker

## Project Overview

This project is a Power BI banking analytics portfolio project built using synthetic retail loan data.

The goal of this project was to understand how banks and financial institutions can monitor loan portfolio performance, credit quality, delinquency, non-performing loans, and branch/product-level risk exposure using business intelligence dashboards.

The project includes two main Power BI dashboard pages:

1. **Bank Loan Portfolio Overview**  
   Focuses on loan disbursement, branch performance, product mix, average interest rates, loan count, and outstanding balance.

2. **Credit Risk & NPL Tracker**  
   Focuses on credit-risk monitoring through delinquency buckets, NPL ratio, default rate, high-risk exposure, branch/product risk concentration, and high-risk loan-level review.

The dataset is fully synthetic and was created for learning, portfolio demonstration, and Power BI practice only. It does not contain real customer, borrower, or bank data.

---

## Dashboard Preview

### Bank Loan Portfolio Overview

![Bank Loan Portfolio Overview](screenshots/01_bank_loan_portfolio_overview.png)

### Credit Risk & NPL Tracker

![Credit Risk NPL Tracker](screenshots/02_credit_risk_npl_tracker.png)

---

## Repository Structure

```text
bank-loan-portfolio-credit-risk-powerbi/
│
├── README.md
├── Bank_Loan_Portfolio_Credit_Risk_Report.pdf
├── Bank_Loan_Portfolio_Credit_Risk.pbix
│
├── data/
│   ├── Fact_Loans.csv
│   ├── Dim_Branch.csv
│   ├── Dim_Product.csv
│   ├── Dim_Customer.csv
│   └── Fact_BankFinancials.csv
│
├── screenshots/
│   ├── 01_bank_loan_portfolio_overview.png
│   ├── 02_credit_risk_npl_tracker.png
│   ├── 03_data_model_star_schema.png
│   └── 04_high_risk_loan_detail.png
│
└── docs/
    ├── data_dictionary.md
    ├── dax_measures.md
    └── methodology_notes.md
```
## Business Questions Answered

### Loan Portfolio Performance

- What is the total loan amount disbursed?
- How many loan accounts are in the portfolio?
- What is the current outstanding loan balance?
- What is the average interest rate?
- Which branch has the highest loan production?
- Which loan product has the largest portfolio share?
- How is lending distributed across branches, products, and regions?

### Credit Risk & NPL Monitoring

- What percentage of outstanding balance is non-performing?
- What is the total NPL exposure?
- What is the account-based default rate?
- Which branches have the highest NPL ratio?
- Which loan products have the highest default rate?
- How much outstanding balance is current, early delinquent, seriously delinquent, or 90+ DPD?
- Which loans should be prioritized for high-risk review?
- What are the key limitations of the current risk model?

---

## Dataset

The project uses synthetic/mock banking data designed to resemble common retail loan portfolio fields.

### Tables Used

| Table | Description |
|---|---|
| `Fact_Loans` | Central loan transaction and credit-risk fact table |
| `Dim_Branch` | Branch, city, state, and region details |
| `Dim_Product` | Loan type, product category, and secured/unsecured classification |
| `Dim_Customer` | Customer profile fields such as age, income, employment type, and credit score band |
| `Date_Table` | Date dimension used for time-based analysis |
| `Fact_BankFinancials` | Monthly branch-level financial metrics used for operating performance analysis |

---

## Data Model

The Power BI model follows a star-schema structure.

`Fact_Loans` is the central fact table and connects to the following dimension tables:

- `Dim_Branch`
- `Dim_Product`
- `Dim_Customer`
- `Date_Table`

This structure allows users to analyze loan performance and credit risk by:

- Region
- Branch
- Loan type
- Customer profile
- Credit score band
- Loan status
- Delinquency bucket
- Year

---

## Key Metrics

| KPI | Definition |
|---|---|
| Total Loans Disbursed | Sum of original loan amounts |
| Loan Count | Distinct count of loan accounts |
| Outstanding Balance | Current amount still owed by borrowers |
| Average Interest Rate | Average interest rate across the portfolio |
| Average Loan Size | Total loans disbursed divided by loan count |
| NPL Balance | Outstanding balance of loans in the 90+ DPD bucket |
| NPL Ratio | NPL Balance divided by Total Outstanding Balance |
| Default Rate | Defaulted loan accounts divided by total loan accounts |
| High-Risk Exposure | Outstanding balance of loans tagged as high risk |
| Provision Amount | Simplified reserve estimate for possible credit losses |
| Provision Coverage Ratio | Provision Amount divided by NPL Balance |
| Delinquency Bucket | Grouping of loans by Days Past Due |

---

## Whole-Bank KPI Snapshot

| Metric | Value |
|---|---:|
| Loan Accounts | 1,000 |
| Total Disbursed | $50.71M |
| Outstanding Balance | $22.06M |
| Average Interest Rate | 12.79% |
| Average Loan Size | $50.71K |
| NPL Ratio | 21.18% |
| Default Rate | 17.00% |
| NPL Balance | $4.673M |
| High-Risk Exposure | $4.67M |

---

## Dashboard 1: Bank Loan Portfolio Overview

The Bank Loan Portfolio Overview dashboard provides a business-performance view of the simulated loan book.

### Key Features

- KPI cards for loan count, total disbursement, outstanding balance, average interest rate, and average loan size
- Branch-level loan disbursement analysis
- Product mix analysis by loan type
- Branch performance summary table
- Monthly loan disbursement view
- Interactive filters for loan status and region

### Main Findings

- The simulated portfolio contains 1,000 loan accounts.
- Total original disbursement is $50.71M.
- Current outstanding balance is $22.06M.
- Approximately 43.5% of original disbursement remains as active outstanding exposure.
- Orlando Central is the largest production branch, with approximately $6.8M disbursed, 125 loans, and $3.32M outstanding.
- Auto Loan is the largest product by disbursement volume at $9.44M, followed by Home Loan at $9.10M and Personal Loan at $8.86M.

---

## Dashboard 2: Credit Risk & NPL Tracker

The Credit Risk & NPL Tracker expands the analysis from portfolio performance into credit-risk monitoring.

### Key Features

- KPI cards for NPL Ratio, Default Rate, Total NPL Balance, High-Risk Exposure, Provision Amount, and Outstanding Balance
- Delinquency bucket analysis
- Default rate by loan type
- NPL ratio by branch
- NPL and provision view by loan origination month
- High-risk loan detail table
- Interactive filters for region, branch, loan type, risk rating, delinquency bucket, and year

### Main Findings

- The whole-bank NPL ratio is 21.18%.
- NPL Balance is $4.673M, based on loans in the 90+ DPD bucket.
- The account-based default rate is 17.00%.
- Tampa Bay has the highest branch-level NPL ratio at 31.2%.
- Houston South has the second-highest NPL ratio at 30.2%.
- Education Loan has the highest product-level default rate at 20.26%.
- The 30-59 DPD bucket contains $4.704M of exposure, making it an important forward-looking risk pipeline.
- The 90+ DPD bucket contains $4.673M of exposure and is treated as non-performing under the simplified project definition.

---

## Delinquency Composition

| Delinquency Bucket | Balance | Share of Outstanding | Interpretation |
|---|---:|---:|---|
| Current | $8.213M | 37.23% | Performing exposure |
| 1-29 DPD | $2.259M | 10.24% | Early delinquency |
| 30-59 DPD | $4.704M | 21.32% | Material watchlist exposure |
| 60-89 DPD | $2.211M | 10.02% | Serious delinquency |
| 90+ DPD | $4.673M | 21.18% | Non-performing exposure under project rule |

---

## Branch Risk Summary

| Branch | NPL Ratio | Analytical Note |
|---|---:|---|
| Tampa Bay | 31.2% | Highest branch-level NPL ratio |
| Houston South | 30.2% | Second-highest NPL ratio |
| Orlando Central | 26.0% | High production branch with elevated risk |
| Dallas Central | 25.4% | Above-average branch risk |
| Nashville West | 24.5% | Elevated risk concentration |
| Miami Downtown | 9.0% | Lowest branch-level NPL ratio |

---

## Product Risk Summary

| Loan Type | Default Rate |
|---|---:|
| Education Loan | 20.26% |
| Credit Card Loan | 17.57% |
| Personal Loan | 17.44% |
| Small Business Loan | 16.07% |
| Home Loan | 15.91% |
| Auto Loan | 15.30% |

Education Loan has the highest default rate in the simulated dataset. However, risk is not concentrated in only one product because the difference between the highest and lowest product default rate is approximately 4.96 percentage points.

---

## Tools Used

- Power BI Desktop
- Power Query
- DAX
- Data Modeling
- Mockaroo
- Excel
- CSV
- GitHub

---

## Skills Demonstrated

- Business Intelligence
- Credit Risk Analysis
- Banking Analytics
- Financial Data Analysis
- Power BI Dashboard Development
- DAX Measures
- Power Query Data Cleaning
- Star Schema Data Modeling
- KPI Reporting
- Portfolio Risk Monitoring
- Data Storytelling
- Synthetic Data Generation

---

## Important Methodology Notes

This project uses simplified credit-risk logic for learning and portfolio demonstration.

- A loan is treated as non-performing when Days Past Due is 90 or greater.
- Default Rate is account-based, not balance-based.
- NPL Ratio is balance-based and uses outstanding balance.
- Monthly credit-risk visuals should be interpreted as vintage/origination-style views because the date relationship uses loan disbursement date.
- A production-grade credit-risk dashboard would require a monthly loan performance snapshot table with one row per loan per reporting month.
- Provision calculation is simplified and should not be treated as a production expected-credit-loss model.

---

## Project Limitations

This project is not intended to represent a real bank’s actual risk profile. The data is synthetic, and the metrics are created for learning and portfolio demonstration.

Key limitations:

- No real customer or bank data
- No actual payment history table
- No monthly loan performance snapshot table
- Simplified NPL definition
- Simplified provision logic
- No regulatory reporting framework
- No production-grade expected-credit-loss model
- No real underwriting, bureau, or behavioral repayment data

---

## Future Enhancements

- Add monthly loan performance snapshots
- Track delinquency migration and roll rates
- Add cure-rate and recovery-rate analysis
- Add write-off tracking
- Build probability-of-default scoring
- Build expected-loss calculations using EAD, PD, and LGD
- Add branch-level row-level security
- Add Key Influencers visual for default drivers
- Add decomposition tree for NPL exposure analysis
- Add Power BI Service deployment and scheduled refresh
- Add executive summary page with navigation buttons
- Improve UI/UX with a professional banking-style theme

---

## Project Report

The full project report is available here:

[Bank Loan Portfolio Credit Risk Report](Bank_Loan_Portfolio_Credit_Risk_Report.pdf)

---

## Disclaimer

This project uses synthetic data for learning and portfolio demonstration only. No real customer, borrower, or banking data is included. The analysis should not be interpreted as a real bank’s credit-risk position or regulatory reporting output.
