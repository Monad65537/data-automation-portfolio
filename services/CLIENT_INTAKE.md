# Client Intake — Data Cleaning and Transformation

## Purpose

This checklist is completed before accepting a fixed-scope project.

Its purpose is to establish the technical requirements, business rules, deliverables, deadline, and acceptance criteria.

## 1. Input Data

- How many files require processing?
- What are their formats (CSV, XLSX, or another format)?
- Approximately how many records and columns are present?
- Are files structurally consistent?
- Do the files contain multiple Excel worksheets?
- Is an appropriately sanitized sample available?

## 2. Desired Output

- What should the final dataset look like?
- Which columns should be retained, removed, renamed, or added?
- What output file formats are required?
- Must column order and identifier formatting be preserved?
- Are there any downstream systems with strict import requirements?

## 3. Transformation Rules

- Should surrounding whitespace be removed?
- Should name capitalization be normalized?
- Which date formats are expected?
- How should monetary values and decimal separators be interpreted?
- Should empty values remain empty or be flagged?
- Are any custom mappings or calculations necessary?

## 4. Validation and Duplicates

- Which columns are mandatory?
- Which identifiers must be unique?
- What defines an actual duplicate?
- Should duplicates be reported, retained, or removed?
- What should happen to invalid records?
- Are there known exceptions to the validation rules?

No duplicate-removal or data-reconstruction policy is assumed without an explicit client decision.

## 5. Data Security and Authorization

- Does the client have authority to share the data for this work?
- Does the dataset contain personal, financial, confidential, or otherwise regulated information?
- Are there restrictions on where data may be processed or stored?
- Is use of third-party cloud services or AI tools permitted?
- What retention and deletion requirements apply?
- How should the completed files be transmitted?

Confidential client records must not be uploaded to external AI services or public repositories without the necessary authorization and approved handling conditions.

## 6. Commercial Scope

- Requested deadline:
- Agreed deliverables:
- Included revision allowance:
- Agreed price:
- Dependencies or outstanding client decisions:
- Explicit exclusions:

## 7. Acceptance Criteria

Write specific, independently checkable conditions for successful delivery.

Examples:

- Identifiers retain leading zeros.
- Output contains the agreed column names and order.
- Invalid amounts are flagged rather than silently converted.
- All input records are accounted for.
- Required export files open correctly.
- The delivered report explains unresolved issues.

## 8. Acceptance Decision

Select one:

- ACCEPT — Requirements are clear, feasible, and within the agreed scope.
- CLARIFICATION REQUIRED — Important rules or inputs remain ambiguous.
- DECLINE OR REQUOTE — Requirements exceed current capability, resources, or the proposed package.

Do not begin processing production data until scope, authorization, and handling requirements are sufficiently clear.