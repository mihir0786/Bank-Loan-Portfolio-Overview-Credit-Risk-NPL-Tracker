# Methodology Notes

## Project Purpose

This project was created to practice Power BI, banking analytics, credit-risk reporting, and portfolio-level financial analysis using synthetic retail banking data.

The project has two analytical layers:

1. Bank Loan Portfolio Overview
2. Credit Risk & NPL Tracker

## Synthetic Data

The dataset is fully synthetic and does not include real bank, borrower, or customer information.

Synthetic data was used because real loan-level banking data is not publicly available due to privacy, confidentiality, and regulatory concerns.

## Risk Definition

For this project, a loan is treated as non-performing when Days Past Due is 90 or greater.

This is a simplified learning assumption and should not be treated as a full regulatory or accounting definition of non-performing loans.

## Default Rate

Default Rate is calculated as:

Defaulted Loan Count / Total Loan Count

This is an account-based metric. It measures the percentage of loan accounts flagged as defaulted.

## NPL Ratio

NPL Ratio is calculated as:

Total NPL Balance / Total Outstanding Balance

This is a balance-based metric. It measures the share of outstanding exposure classified as non-performing.

## Provision Amount

ProvisionAmount is a simplified reserve estimate based on outstanding balance and delinquency severity.

A production expected-credit-loss model would require a more advanced approach using:

- EAD: Exposure at Default
- PD: Probability of Default
- LGD: Loss Given Default

## Time Analysis Limitation

The current dashboard uses loan disbursement date as the date relationship.

Therefore, monthly credit-risk visuals should be interpreted as origination/vintage-style views, not true month-by-month borrower performance migration.

A production-grade credit-risk model would require a monthly loan performance snapshot table with one row per loan per reporting month.

## Future Methodology Improvements

- Add monthly performance snapshots
- Add roll-rate analysis
- Add cure-rate analysis
- Add write-off and recovery tracking
- Build probability-of-default scoring
- Build expected-loss calculations using EAD, PD, and LGD
- Add branch-level row-level security
