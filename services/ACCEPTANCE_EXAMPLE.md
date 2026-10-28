# Simulated Client Acceptance Test

**Project:** Customer Records Cleanup  
**Client:** Fictional small-business client  
**Status:** Simulation — not a paid engagement

## 1. Client Request

The fictional client supplies a CSV file containing customer records with inconsistent capitalization, duplicate identifiers, and invalid monetary values.

The client requests:

1. Normalize customer names.
2. Preserve customer IDs, including leading zeros.
3. Identify duplicate customer IDs without silently discarding records.
4. Flag invalid or negative amounts.
5. Deliver accepted records, flagged records, and a processing summary.

## 2. Input Schema

Required columns:

- `customer_id`
- `name`
- `email`
- `amount`
- `order_date`

## 3. Acceptance Criteria

| ID | Criterion | Result |
|---|---|---|
| AC-01 | Valid names follow the documented capitalization rule | PENDING |
| AC-02 | Customer IDs retain leading zeros | PENDING |
| AC-03 | Duplicate customer IDs are identified | PENDING |
| AC-04 | Invalid and negative amounts are flagged | PENDING |
| AC-05 | Every input row is accounted for in accepted or flagged outputs | PENDING |

## 4. Planned Deliverables

- Synthetic input CSV.
- Accepted records CSV.
- Flagged records CSV.
- JSON quality report.
- Summary of acceptance-test results.

## 5. Execution Evidence

**Tool:** DataClean Pro  
**Input path:** [To be completed]  
**Output path:** [To be completed]  
**Command executed:** [To be completed]

## 6. Verification Results

**Input count:** [To be completed]  
**Accepted count:** [To be completed]  
**Flagged count:** [To be completed]

Record the evidence for every acceptance criterion and mark each one PASS or FAIL.

## 7. Conclusion

[To be completed after executing and verifying the simulation.]

This is a synthetic exercise designed to assess technical and delivery readiness. It does not represent paid client work.