# Standard Delivery Procedure — Spreadsheet Processing

## Objective

Deliver accurate, reproducible, and understandable outputs that satisfy an agreed client specification.

## 1. Confirm Scope

Before processing:

1. Review the agreed input and output schemas.
2. Confirm transformation and validation rules.
3. Identify ambiguous records and unresolved decisions.
4. Confirm the delivery deadline and file formats.
5. Confirm authorized data handling and retention requirements.

## 2. Preserve Original Data

Keep an unchanged copy of the source data in an approved working location.

Do not overwrite original client files.

Use separate input, working, and output directories where appropriate.

## 3. Prepare Processing

- Select the applicable existing tool or transformation workflow.
- Validate the input schema.
- Preserve important identifier formats.
- Confirm locale-specific date and number rules.
- Test the transformation on a small representative sample.
- Document assumptions that affect the result.

## 4. Execute the Transformation

Process the agreed input files.

Capture the processing outcome, including warnings and records requiring review.

Do not silently remove records whose business meaning is unresolved.

## 5. Verify Output

Perform applicable checks:

- Output file exists and can be opened.
- Required column names and order are correct.
- Data types and significant text formatting are preserved.
- Input and output counts reconcile under the agreed rules.
- Rejected or excluded records have documented reasons.
- Expected calculations match independently checked values.
- Representative transformations match the client's examples.
- Unresolved exceptions are disclosed.

Where applicable, use automated tests and a read-back of exported files.

Passing a test suite does not replace checking the actual client dataset.

## 6. Prepare Delivery Package

Proposed structure:

```text
client-delivery/
├── output/
│   └── cleaned_data.csv
├── reports/
│   ├── flagged_records.csv
│   └── processing_summary.md
└── README.md
```

File names and included artifacts may vary according to the contract.

## 7. Processing Summary

The delivery summary must state:

- Input files processed.
- Transformation rules applied.
- Number of records processed.
- Number accepted, rejected, excluded, or otherwise classified.
- Verification checks performed and their outcomes.
- Outstanding ambiguities or limitations.
- Instructions for reviewing the deliverables.

## 8. Delivery and Revisions

Deliver the files through the approved channel.

Ask the client to review them against the agreed acceptance criteria.

Correct confirmed defects that fall within the agreed scope and revision policy.

Treat new rules, additional files, or substantially changed requirements as potential scope changes.

## 9. Data Retention and Closure

Follow the agreed retention and deletion requirements.

Do not publish client data, screenshots, code containing secrets, or confidential business information without appropriate authorization.

Retain only records necessary and authorized for the agreed purpose.

Document completion and any unresolved exceptions.

## Definition of Done

A project is complete when the agreed deliverables have been generated, verified against documented acceptance criteria, securely delivered, and any required closure actions have been completed.