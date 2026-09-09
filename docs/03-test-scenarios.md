# SecureBank — Test Scenarios

## 1. Document Information

| Field | Details |
|---|---|
| Project | SecureBank Banking Web Application |
| Document | Test Scenarios |
| Test Management Tool | Azure DevOps Test Plans |
| Source | Project Overview & Requirements |
| Status | Draft |
| Version | 2.0 |

---

## 2. Purpose

This document contains the **high-level test scenarios** identified for the SecureBank banking web application.

A test scenario defines **what functionality or business behavior needs to be validated**. It does not contain individual test steps, detailed test data, expected results, actual results, or execution results.

Individual test cases will be derived from these scenarios and managed in **Azure DevOps Test Plans**.

> **Important:** The table below contains high-level test scenarios only. It does not contain individual test cases.

---

## 3. Test Scenario Summary

| Test Scenario ID | Reference | Test Scenario Description | Priority | Number of Test Cases | Status |
|---|---|---|---|---:|---|
| TS-001 | Project Overview | Validate the working of Account Information functionality | P1 | TBD | Planned |
| TS-002 | Project Overview | Validate the working of Account Balance functionality | P0 | TBD | Planned |
| TS-003 | Project Overview | Validate the working of Available Balance functionality | P0 | TBD | Planned |
| TS-004 | Project Overview | Validate the consistency of account-related financial information | P0 | TBD | Planned |
| TS-005 | Project Overview | Validate account information after financial transactions | P0 | TBD | Planned |
| TS-006 | Project Overview | Validate the working of Quick Transfer functionality | P0 | TBD | Planned |
| TS-007 | Project Overview | Validate source account selection for transfers | P1 | TBD | Planned |
| TS-008 | Project Overview | Validate destination account selection for transfers | P1 | TBD | Planned |
| TS-009 | Project Overview | Validate transfer amount entry | P1 | TBD | Planned |
| TS-010 | Project Overview | Validate transfer amount rules and input validation | P0 | TBD | Planned |
| TS-011 | Project Overview | Validate source and destination account rules for transfers | P0 | TBD | Planned |
| TS-012 | Project Overview | Validate available-funds validation for transfers | P0 | TBD | Planned |
| TS-013 | Project Overview | Validate successful transfer processing | P0 | TBD | Planned |
| TS-014 | Project Overview | Validate transfer rejection and error handling | P0 | TBD | Planned |
| TS-015 | Project Overview | Validate account information after a successful transfer | P0 | TBD | Planned |
| TS-016 | Project Overview | Validate transaction creation after a successful transfer | P0 | TBD | Planned |
| TS-017 | Project Overview | Validate the working of Transaction History functionality | P1 | TBD | Planned |
| TS-018 | Project Overview | Validate transaction information display | P1 | TBD | Planned |
| TS-019 | Project Overview | Validate transaction data accuracy | P0 | TBD | Planned |
| TS-020 | Project Overview | Validate transaction identification and uniqueness | P0 | TBD | Planned |
| TS-021 | Project Overview | Validate transaction classification and description consistency | P0 | TBD | Planned |
| TS-022 | Project Overview | Validate transaction date information | P1 | TBD | Planned |
| TS-023 | Project Overview | Validate transaction running balance calculation | P0 | TBD | Planned |
| TS-024 | Project Overview | Validate recording of successful financial transactions | P0 | TBD | Planned |
| TS-025 | Project Overview | Validate the working of Bill Payment functionality | P0 | TBD | Planned |
| TS-026 | Project Overview | Validate bill information display | P1 | TBD | Planned |
| TS-027 | Project Overview | Validate bill amount information | P0 | TBD | Planned |
| TS-028 | Project Overview | Validate bill due-date information | P1 | TBD | Planned |
| TS-029 | Project Overview | Validate bill payment processing | P0 | TBD | Planned |
| TS-030 | Project Overview | Validate payment amount and duplicate-charge prevention | P0 | TBD | Planned |
| TS-031 | Project Overview | Validate account information after bill payment | P0 | TBD | Planned |
| TS-032 | Project Overview | Validate bill payment status and confirmation | P1 | TBD | Planned |
| TS-033 | Project Overview | Validate customer logout functionality | P0 | TBD | Planned |
| TS-034 | Project Overview | Validate authenticated session termination after logout | P0 | TBD | Planned |
| TS-035 | Project Overview | Validate access protection after logout | P0 | TBD | Planned |
| TS-036 | Project Overview | Validate session timeout functionality | P0 | TBD | Planned |
| TS-037 | Project Overview | Validate access protection after session expiration | P0 | TBD | Planned |
| TS-038 | Project Overview | Validate accuracy of last-login information | P1 | TBD | Planned |
| TS-039 | Project Overview | Validate password information protection | P0 | TBD | Planned |
| TS-040 | Project Overview | Validate protection of sensitive authentication information | P0 | TBD | Planned |
| TS-041 | Project Overview | Validate end-to-end consistency of a successful fund transfer | P0 | TBD | Planned |
| TS-042 | Project Overview | Validate end-to-end behavior of a rejected fund transfer | P0 | TBD | Planned |
| TS-043 | Project Overview | Validate consistency between account information and transaction history | P0 | TBD | Planned |
| TS-044 | Project Overview | Validate end-to-end consistency of a successful bill payment | P0 | TBD | Planned |
| TS-045 | Project Overview | Validate protection of banking functionality after logout | P0 | TBD | Planned |
| TS-046 | Project Overview | Validate protection of banking functionality after session expiration | P0 | TBD | Planned |

---

# 4. Scenario Priority

| Priority | Meaning |
|---|---|
| P0 | Critical business, financial, security, or data-integrity functionality |
| P1 | Important business or supporting functionality |
| P2 | Lower-risk functionality |

Priority may be adjusted when confirmed business requirements, risk assessment, or project priorities change.

---

# 5. Number of Test Cases

The **Number of Test Cases** column is initially marked as `TBD`.

After detailed test-case design, the column will be updated with the actual number of test cases derived from each scenario.

For example:

| Test Scenario | Number of Test Cases |
|---|---:|
| TS-010 — Validate transfer amount rules and input validation | 6 |
| TS-012 — Validate available-funds validation for transfers | 4 |
| TS-023 — Validate transaction running balance calculation | 5 |

The exact numbers will be determined during test-case design.

---

# 6. Scenario-to-Test-Case Relationship

One test scenario can produce multiple test cases.

For example:

### TS-010 — Validate Transfer Amount Rules and Input Validation

Possible test cases:

```text
TS-010
│
├── TC-010-01 — Valid positive amount
├── TC-010-02 — Zero amount
├── TC-010-03 — Negative amount
├── TC-010-04 — Decimal amount
├── TC-010-05 — Invalid input
└── TC-010-06 — Boundary value
```

The scenario describes the **testing objective**, while the test cases describe the **specific conditions and procedures**.

---

# 7. Scenario Status

| Status | Meaning |
|---|---|
| Planned | Scenario has been identified but detailed test cases have not yet been executed |
| In Progress | Related test cases are being designed or executed |
| Completed | Related testing has been completed |
| Blocked | Testing cannot proceed because of a blocking issue |
| Deferred | Testing has been intentionally postponed |

All scenarios are initially marked as **Planned**.

---

# 8. Requirement Traceability

The test scenarios are derived from the requirements documented in the Project Overview & Requirements document.

The traceability relationship is:

```text
Requirement
      ↓
Test Scenario
      ↓
Test Case
      ↓
Test Execution
      ↓
Pass / Fail
      ↓
Bug (if applicable)
      ↓
Retest
      ↓
Regression
```

Example:

```text
REQ-TRF-006
Transfer cannot exceed available balance
          ↓
TS-012
Validate available-funds validation for transfers
          ↓
TC-012-01
Detailed insufficient-funds test case
          ↓
Test Execution
          ↓
Fail
          ↓
Azure DevOps Bug
```

---

# 9. Azure DevOps Test Plan Mapping

The scenarios will be converted into detailed test cases within Azure DevOps Test Plans.

Recommended suite structure:

```text
SecureBank — System & Functional Testing
│
├── Account Management
│   ├── TS-001 to TS-005
│   └── Detailed Test Cases
│
├── Quick Transfer
│   ├── TS-006 to TS-016
│   └── Detailed Test Cases
│
├── Transaction History
│   ├── TS-017 to TS-024
│   └── Detailed Test Cases
│
├── Bill Payment
│   ├── TS-025 to TS-032
│   └── Detailed Test Cases
│
├── Security
│   ├── TS-033 to TS-040
│   └── Detailed Test Cases
│
└── Cross-Functional
    ├── TS-041 to TS-046
    └── Detailed Test Cases
```

---

# 10. Test Scenario Design Rules

A test scenario should:

- Describe a high-level testing objective.
- Define **what** needs to be validated.
- Be traceable to one or more requirements.
- Have an appropriate priority.
- Avoid detailed execution steps.
- Avoid specific test data unless required to identify the scenario.
- Avoid detailed expected results.
- Be capable of producing one or more test cases.
- Avoid describing an individual defect as the scenario itself.

### Example

**Correct scenario:**

> Validate transfer amount rules and input validation.

**Not a scenario:**

> Enter `-100` in the transfer amount field and verify that an error message appears.

The second example is a **test case-level description**.

---

# 11. Test Case Derivation

Detailed test cases will be created from the scenarios using appropriate test-design techniques, including:

- Positive testing
- Negative testing
- Boundary Value Analysis
- Equivalence Partitioning
- Business-rule validation
- Data consistency validation
- Security validation
- Relevant combinations

A single scenario may therefore have one, several, or many test cases depending on its complexity and risk.

---

# 12. Scenario Review Criteria

Before creating detailed test cases, each scenario should be reviewed to confirm that it:

- Has a clear testing objective.
- Is linked to a requirement.
- Has an appropriate priority.
- Is not unnecessarily duplicated.
- Represents a meaningful functional or business condition.
- Can be expanded into executable test cases.
- Is written at the appropriate high level.

---

# 13. Document Status

| Version | Date | Status | Description |
|---|---|---|---|
| 1.0 | 2026-09-07 | Draft | Initial test scenario document |
| 2.0 | 2026-09-07 | Draft | Reworked into high-level scenario format with reference, priority, test-case count, and status columns |

---

## End of Document
