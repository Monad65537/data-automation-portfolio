# Case Study 2 — Auditable Spreadsheet Consolidation

## 1. Business Problem

Businesses often store sales transactions across multiple CSV and Excel files, making it difficult to consolidate information reliably.

Simply combining files can create duplicate transactions, overlook conflicting records, or produce incorrect financial totals.

**Objective:** Demonstrate a repeatable workflow for consolidating sales datasets while validating records, documenting exclusions, and reconciling transaction amounts.

This is a portfolio demonstration using synthetic data, not a completed client engagement.

## 2. Technical Solution

SheetMerge 0.1.0 is a Python command-line application for validating, consolidating, and reconciling sales data from CSV and XLSX inputs.

Its workflow includes:

1. Loading input files according to explicitly defined TOML source profiles.
2. Validating records against documented requirements.
3. Classifying accepted, rejected, and redundant records.
4. Detecting duplicate and conflicting transaction information.
5. Producing structured output suitable for further processing.
6. Generating reconciliation information for audit and review.

## 3. Demonstrated Capabilities

- CSV and XLSX ingestion
- Explicit configuration through TOML
- Record validation and classification
- Duplicate and conflict handling
- Currency-aware monetary processing
- Reconciliation of known monetary amounts
- Structured audit outputs
- Resource limits for input processing

## 4. Example Business Scenario

A business receives sales files from different branches.

Some records contain valid transactions, while others contain duplicate transaction identifiers, conflicting values, or invalid information.

Rather than combining everything indiscriminately, the application classifies records and provides evidence of how transactions were handled.

This allows the business to review problematic records without silently discarding important information.

## 5. Quality Assurance

SheetMerge 0.1.0 underwent automated testing and technical verification.

The Day 7 audit established:

- 258 automated tests passed.
- No failed or skipped tests in the verified run.
- Ruff static analysis passed.
- Dependency consistency checks passed.
- The installed command-line interface executed successfully.
- Version and help commands returned successfully.

An environment-specific pytest cache permission issue was observed. The tests passed without warnings when a separate cache directory was used.

These checks support the tested behavior but do not guarantee correctness for every possible dataset.

## 6. Potential Business Value

A controlled consolidation workflow can:

- Reduce repetitive manual spreadsheet work.
- Help identify conflicting transactions.
- Improve traceability of data-processing decisions.
- Support review of rejected and redundant records.
- Make financial reconciliation more systematic.
- Enable repeatable processing of similarly structured files.

No actual client cost savings or productivity gains have been measured.

## 7. Limitations

- Input files must comply with supported formats and configuration requirements.
- Business-specific rules are necessary to interpret ambiguous transactions.
- Monetary reconciliation does not establish whether source transactions are authentic.
- Accepted records are not automatically guaranteed to represent complete business activity.
- Processing limits apply to supported input sizes and structures.
- Sensitive information requires appropriate handling safeguards.

## 8. Technologies

Python 3.12, pandas, openpyxl, pytest, Ruff, TOML, Git, and GitHub.

## 9. Repository

[View the SheetMerge on GitHub](https://github.com/Monad65537/sheetmerge)

## 10. Demonstration Results

### Scenario

A synthetic sales dataset was consolidated from three branches using 11 CSV and XLSX files with differing column names, date formats, decimal conventions, and currencies.

The application processed 33 transaction records and generated a reconciliation and audit bundle.

### Record Classification

| Classification | Records |
|---|---:|
| Input | 33 |
| Accepted | 16 |
| Rejected | 14 |
| Redundant | 3 |
| Unaccounted | 0 |

**Processing outcome:** SheetMerge consolidated 33 synthetic sales records from 11 source files, accepted 16 transactions, rejected 14 for review, and identified 3 redundant exact duplicates. The application generated consolidated CSV/XLSX outputs, detailed exclusion records, a reconciliation report, and an auditable processing manifest.

All input records were accounted for:

33 = 16 + 14 + 3

### Validation and Exception Handling

The demonstration included:

- Six conflicting transaction occurrences.
- Three invalid transaction dates.
- Three missing monetary amounts.
- Two records with excess monetary precision.
- Three redundant exact duplicates.

Conflicting transaction keys were quarantined rather than arbitrarily selecting a valid-looking record.

Invalid monetary values were not silently rounded or replaced with zero.

### Monetary Reconciliation

| Currency | Input known | Accepted | Rejected known | Redundant |
|---|---:|---:|---:|---:|
| USD | 356.55 | 141.45 | 115.00 | 100.10 |
| PLN | 583.35 | 220.35 | 163.00 | 200.00 |
| JPY | 7,389 | 1,290 | 5,099 | 1,000 |

Known monetary amounts reconciled exactly within each currency.

Five records contained unquantifiable monetary values. Consequently, the application reported:

- `count_balanced: true`
- `known_amounts_balanced: true`
- `monetary_complete: false`
- `status: review_required`

These results establish accounting consistency for classified records and known monetary amounts, not the authenticity or completeness of the underlying business transactions.

### Generated Deliverables

- [Consolidated CSV](../portfolio-assets/spreadsheet-merging/demo-output/master.csv)
- [Consolidated Excel workbook](../portfolio-assets/spreadsheet-merging/demo-output/master.xlsx)
- [Rejected and redundant records](../portfolio-assets/spreadsheet-merging/demo-output/exclusions.csv)
- [Currency reconciliation](../portfolio-assets/spreadsheet-merging/demo-output/reconciliation.csv)
- [Detailed reconciliation data](../portfolio-assets/spreadsheet-merging/demo-output/reconciliation.json)
- [Processing manifest](../portfolio-assets/spreadsheet-merging/demo-output/manifest.json)
- [Audit trail](../portfolio-assets/spreadsheet-merging/demo-output/audit.jsonl)

### Reproducibility

The demonstration uses the synthetic fixtures and source configuration provided in the SheetMerge repository.

The observed classification counts and currency totals matched the repository's documented expected results.

No real client data was used.