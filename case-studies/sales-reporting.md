# Case Study 3 — Automated Sales Reporting

## 1. Business Problem

Businesses frequently generate sales reports manually from spreadsheets containing transaction and product data.

Manual reporting can be repetitive and vulnerable to errors involving invalid records, incorrect monetary calculations, duplicated transactions, or inconsistent currency precision.

**Objective:** Demonstrate a repeatable workflow for validating structured sales data and generating auditable Excel reports.

This project is a portfolio demonstration using synthetic data, not a completed client engagement.

## 2. Technical Solution

SalesReport Auto 0.1.0 is a Python command-line application designed to generate standalone sales Excel reports.

It supports two explicit processing modes:

- **Transactions:** Reporting based on transaction-level sales data.
- **Products:** Reporting based on product-line information, including quantities and unit prices.

The application validates inputs before generating reports and documents records requiring further review.

## 3. Key Capabilities

- CSV and XLSX ingestion
- Transaction and product reporting modes
- Exact decimal monetary processing
- Configurable currency precision
- Validation of required fields
- Validation of product line calculations
- Optional integration with SheetMerge
- Explicit output paths and exit codes
- Automated testing

## 4. Example Business Scenario

A retailer receives sales records from multiple branches and needs a structured Excel report.

The input may contain inconsistent transaction information, invalid monetary values, or records requiring clarification.

The workflow validates the supplied records, applies documented reporting rules, and generates a structured Excel deliverable.

Where supported, SheetMerge output can be supplied to the reporting workflow to preserve upstream classification and reconciliation information.

## 5. Quality Assurance

The Day 7 technical audit established:

- 521 tests passed in the default suite.
- Three additional SheetMerge integration tests passed when explicitly enabled.
- One environment-dependent symlink test remained skipped.
- Ruff static analysis passed.
- Dependency consistency checks passed.
- The installed command-line application executed successfully.
- The application reported version 0.1.0.

The complete integration-enabled suite reported 524 passed, 1 skipped, and 0 failed.

These results demonstrate verification under tested conditions, not universal correctness.

## 6. Potential Business Value

Automated reporting can help businesses:

- Reduce repetitive spreadsheet preparation.
- Standardize report generation.
- Identify invalid or ambiguous records.
- Improve consistency of monetary calculations.
- Make reporting procedures more reproducible.
- Preserve evidence for reviewing data-quality issues.

No actual client financial savings or time reductions have been measured.

## 7. Limitations

- Source data must comply with documented input requirements.
- XLSX business cells are required to be text under the supported input contract.
- Exact currency precision rules must be configured appropriately.
- The application does not establish the authenticity of source transactions.
- A reconciled report does not prove that the underlying business dataset is complete.
- Optional SheetMerge integration is available only in transaction mode.
- Sensitive business information requires appropriate access controls.

## 8. Technologies

Python 3.12, pandas, openpyxl, pytest, Ruff, Git, and GitHub.

## 9. Repository

[View the SalesReport Auto on GitHub](https://github.com/Monad65537/salesreport-auto)

## 10. Demonstration Results

### Overview

SalesReport Auto 0.1.0 was tested against two synthetic sales datasets to demonstrate transaction-level and product-level reporting.

Both executions completed successfully and generated standalone Excel workbooks.

### Transaction Report

| Metric | Verified result |
|---|---:|
| Input transactions | 7 |
| Accepted transactions | 7 |
| Rejected transactions | 0 |
| Redundant transactions | 0 |
| Unique customers | 4 |
| Net revenue | USD 435.75 |
| Monetary completeness (local input) | True |
| Processing status | Completed |

The report contains five worksheets: Summary, Monthly Sales, Branches, Data Quality, and Raw Data.

### Product Report

| Metric | Verified result |
|---|---:|
| Input product lines | 5 |
| Accepted product lines | 5 |
| Rejected product lines | 0 |
| Redundant product lines | 0 |
| Distinct transactions | 4 |
| Unique customers | 4 |
| Net revenue | USD 195.00 |
| Monetary completeness (local input) | True |
| Processing status | Completed |

The product report contains six worksheets, including a dedicated Products worksheet for product-level analysis.

### Processing Outcome

Both demonstrations successfully converted synthetic CSV sales data into structured Excel reports.

The transaction report summarized seven accepted transactions with USD 435.75 in net revenue. The product report summarized five accepted product lines across four transactions with USD 195.00 in net revenue.

Both workbooks included reporting metrics, data-quality information, source references, and original input records. No records were rejected or classified as redundant.

### Generated Deliverables

- [Transaction Excel report](../portfolio-assets/sales-reporting/transactions-report.xlsx)
- [Product Excel report](../portfolio-assets/sales-reporting/products-report.xlsx)

### Verification

The CLI results were compared with the generated Excel workbooks using openpyxl.

The Summary worksheets confirmed the expected accepted-record counts, transaction counts, revenue values, application version, and completed status.

These demonstrations use synthetic data and do not represent actual client engagements. Local monetary completeness does not establish the completeness or authenticity of underlying business activity.