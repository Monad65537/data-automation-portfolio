# Case Study 1 — Customer Data Cleaning and Validation

## 1. Business Problem

Businesses frequently maintain customer information in CSV or Excel files containing inconsistent formatting, missing values, invalid numerical entries, and potentially conflicting records.

These inconsistencies can compromise reporting, create duplicate customer profiles, and introduce errors into downstream workflows.

**Objective:** Demonstrate a controlled data-cleaning process that improves dataset consistency while preserving important information and identifying records requiring further review.

This is a portfolio demonstration using synthetic data, not a completed client engagement.

## 2. Example Input

The demonstration dataset contains five customer records with deliberately introduced data-quality problems.

| Customer ID | Name | Amount | Data-quality issue |
|---|---|---|---|
| 000101 | `  ALICE smith  ` | 125.50 | Excess whitespace and inconsistent capitalization |
| 000102 | BOB jones | 75.00 | Identifier shared with another record |
| 000102 | EVE brown | 90.00 | Conflicting customer details |
| 000104 | DIANA white | unknown | Nonnumeric amount |
| 000105 | FRANK green | -20 | Negative amount requiring an explicit business rule |

The dataset illustrates why data cleaning must be based on defined rules rather than unrestricted automatic modification.

## 3. Technical Solution

The Python-based workflow uses pandas and separates data processing into distinct operations.

### Data ingestion

CSV files are loaded with customer identifiers explicitly interpreted as strings, protecting leading zeros.

### Data normalization

Text can be standardized through operations such as whitespace trimming and capitalization normalization, according to the selected workflow.

### Validation

The workflow checks data against defined requirements, including customer-identifier validity and numerical-value constraints.

### Data integrity

Potentially conflicting records require explicit handling rules. Two records sharing an identifier must not automatically be treated as interchangeable.

### Output

The workflow produces cleaned data and, where supported by the selected tool, validation or exception information.

## 4. Demonstrated Capabilities

The portfolio project demonstrates:

- Python and pandas data processing
- Customer-ID preservation
- Text normalization
- Blank-identifier validation
- Recognition of invalid values
- Automated testing
- Repeatable CSV processing

These are demonstrated technical capabilities, not claims of guaranteed correctness for arbitrary datasets.

## 5. Quality Assurance

The project has undergone automated testing, dependency consistency checks, and Ruff static analysis.

The Day 7 audit additionally identified and addressed an edge case involving blank customer identifiers and inconsistent CSV parsing settings.

The current verification report records the exact automated test results and remaining limitations.

## 6. Business Value

A controlled data-cleaning workflow can help businesses:

- Reduce manual correction of repetitive formatting problems.
- Identify records that require human decisions.
- Prepare more consistent data for reporting or further processing.
- Apply documented transformation rules reproducibly.
- Reduce the risk of silently changing important customer information.

These are potential benefits. No actual client time savings or financial improvements have been measured in this demonstration.

## 7. Limitations

- Validation rules depend on the business context.
- A shared customer identifier does not necessarily establish that two records are duplicates.
- Negative monetary values may represent refunds or legitimate adjustments.
- Automatic cleaning cannot establish whether every source value is factually correct.
- Sensitive data requires appropriate access controls and handling procedures.

## 8. Technologies

Python 3.12, pandas, pytest, Ruff, Git, and GitHub.

## 9. Repository

[View the Data Cleaning Toolkit on GitHub](https://github.com/Monad65537/freelancing-data-toolkit)


## 10. Demonstration Results

The demonstration processed five synthetic customer records.

- **Input records:** 5
- **Accepted records:** 2
- **Flagged records:** 3
- **Unaccounted records:** 0

**Processing outcome:** The pipeline processed five synthetic
customer records, accepted two and flagged three for review.
It standardized customer names, preserved leading-zero
identifiers, and identified one duplicate customer ID,
one nonnumeric amount, and one negative amount.
Each flagged record was retained in a separate exception
file with an explicit rejection reason. All five input
records were accounted for, and a JSON quality report
was generated.

### Deliverables

- [Original input](../portfolio-assets/data-cleaning/input.csv)
- [Cleaned records](../portfolio-assets/data-cleaning/demo-output/cleaned_customers.csv)
- [Flagged records](../portfolio-assets/data-cleaning/demo-output/flagged_rows.csv)
- [Quality report](../portfolio-assets/data-cleaning/demo-output/quality_report.json)

This demonstration uses synthetic data and does not
represent a completed client engagement.
