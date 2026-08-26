# Practical Manual QA Testing Project

## Project Overview

This repository contains a practical manual software testing project created to demonstrate my ability to analyse software requirements, design test scenarios and test cases, manage testing activities, maintain test traceability, and document software defects.

The project follows a structured manual QA process, beginning with requirements analysis and continuing through test design, test management, test execution, and defect reporting.

## Project Objectives

This project demonstrates my ability to:

- Critically analyse software requirements.
- Identify unclear, incomplete, inconsistent, or untestable requirements.
- Ask relevant questions and request clarification.
- Revise requirements into clear and testable statements.
- Create positive, negative, and edge-case test scenarios.
- Write detailed and repeatable manual test cases.
- Manage test scenarios and test cases using Jira and Qase.
- Maintain traceability between requirements, test scenarios, test cases, and defects.
- Write clear and reproducible defect reports.

## Repository Structure

```text
Practical_QA_Tester_Project/
├── README.md
├── Requirements_Review.md
├── Revised_Software_Requirements_Specification.md
└── test-documentation/
    ├── TEST-SCENARIOS.md
    ├── TEST-CASES.md
    ├── TEST-MANAGEMENT.md
    └── DEFECT-REPORTS.md
```

## Requirements Analysis

The requirements-analysis documents are stored in the root of this repository.

They demonstrate the work completed before the test scenarios and test cases were created.

### Requirements Review

The requirements review identifies questions and concerns found while analysing the original software requirements.

The review highlights:

- Ambiguous requirements
- Missing validation rules
- Incomplete acceptance criteria
- Undefined system behaviour
- Inconsistent requirements
- Requirements that are difficult to test
- Areas requiring clarification from the product owner

[View the Requirements Review](Requirements_Review.md)

### Revised Software Requirements Specification

The revised Software Requirements Specification addresses the questions and concerns raised during the requirements review.

The revised document presents requirements that are:

- Clear
- Complete
- Consistent
- Specific
- Measurable
- Testable

[View the Revised Software Requirements Specification](Revised_Software_Requirements_Specification.md)

Together, these documents demonstrate my ability to critically analyse a requirements document, identify gaps, ask for clarification, and improve the testability of software requirements.

## Test Documentation

The `test-documentation` folder contains the test artefacts created from the revised software requirements.

[Open the Test Documentation Folder](test-documentation/)

### Test Scenarios

The project contains **52 test scenarios** covering the following modules:

- Login
- Products
- Shopping Cart
- Checkout
- Logout

The scenarios include positive, negative, and edge-case coverage.

[View the Test Scenarios](test-documentation/test-scenarios.md)

### Test Cases

The project contains **52 detailed manual test cases**.

Each test case includes:

- Test Case ID
- Requirement ID
- Module
- Test scenario
- Preconditions
- Test data
- Test steps
- Expected result
- Actual result
- Execution status
- Priority

[View the Test Cases](test-documentation/test-cases.md)

## Test Coverage Summary

| Test Type | Number of Tests |
|-----------|----------------:|
| Positive | 24 |
| Negative | 18 |
| Edge Case | 10 |
| **Total** | **52** |

## Test Management Using Jira and Qase

The test-management document explains how Jira and Qase are used to organise and track the testing work.

The high-level test scenarios are documented as Jira issues. Each Jira test scenario contains a link to its corresponding detailed test case in Qase.

This provides traceability between:

- The software requirement
- The test scenario documented in Jira
- The detailed test case stored in Qase
- The test execution result
- Any defect discovered during testing

[View the Test Management Documentation](test-documentation/test-management.md)

### External Test-Management Links

[View the Jira Test Scenarios](PASTE_JIRA_TEST_SCENARIOS_LINK_HERE)

[View the Qase Test Cases](PASTE_QASE_TEST_CASES_LINK_HERE)

## Defect Reporting

The defect-report document contains the defects identified during test execution.

Each defect report includes:

- Defect ID
- Defect title
- Related requirement
- Related test case
- Test environment
- Preconditions
- Steps to reproduce
- Expected result
- Actual result
- Severity
- Priority
- Supporting evidence
- Defect status

Each documented defect includes a link to its corresponding Jira issue. This makes it possible to trace the defect from the failed test case to the issue being managed in Jira.

[View the Defect Reports](test-documentation/defect-reports.md)

[View the Jira Defects](PASTE_JIRA_DEFECTS_LINK_HERE)

## Requirements Traceability

The project maintains traceability throughout the manual testing lifecycle:

```text
Software Requirement
        ↓
Test Scenario in Jira
        ↓
Detailed Test Case in Qase
        ↓
Test Execution Result
        ↓
Defect Report
        ↓
Jira Defect
```

This structure makes it possible to identify:

- Which requirement is being tested
- Which test scenario covers the requirement
- Which detailed test case validates the scenario
- What happened during test execution
- Which defect was raised when the expected result was not achieved

## Tools Used

- GitHub
- Jira
- Qase
- Google Sheets
- Markdown

## Skills Demonstrated

- Requirements review
- Critical requirements analysis
- Requirements clarification
- Software Requirements Specification revision
- Test scenario design
- Manual test-case development
- Positive testing
- Negative testing
- Edge-case testing
- Test prioritisation
- Test management
- Requirements traceability
- Defect identification
- Defect reporting
- Technical documentation

## Author

**Pearl Phahlane**

ISTQB Certified Tester – Foundation Level