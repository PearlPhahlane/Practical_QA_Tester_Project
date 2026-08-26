# SauceDemo Test Management

## Project Overview

This document explains how Jira and Qase were used to manage the manual testing of the [SauceDemo](https://www.saucedemo.com/) web application.

The project covers:

- Requirements analysis
- Test-scenario design
- Test-case design
- Positive, negative, and edge-case testing
- Manual test execution
- Requirements traceability
- Defect reporting
- Defect retesting

## Test Management Tools

### Jira

Jira was used to:

- Organise requirements into epics and user stories
- Document acceptance criteria in Gherkin format
- Track testing progress on a Kanban board
- Record defects
- Track defect fixes and retesting

### Qase

Qase was used to:

- Organise test cases into functional suites
- Group test cases under their related Jira user stories
- Create and execute test runs
- Record test results
- Store test evidence
- Link failed tests to Jira defects

## Test Documentation

The project test documentation includes:

- Requirements review
- Revised Software Requirements Specification
- Test scenarios
- Test cases
- Test management information
- Test execution results
- Defect reports
- Traceability information

## Test Scope

| Functional Area | Test Scenarios |
|---|---:|
| Authentication and Access Control | 10 |
| Product Catalogue | 10 |
| Shopping Cart | 12 |
| Checkout and Order Completion | 15 |
| Session Management | 5 |
| **Total** | **52** |

The test scenarios cover positive, negative, and edge-case behaviour.

## Jira Structure

The SauceDemo requirements were organised into the following epics:

1. Authentication and Access Control
2. Product Catalogue
3. Shopping Cart
4. Checkout and Order Completion
5. Session Management

Related user stories were added under each epic.

Each Jira user story contains:

- Requirement ID
- User-story statement
- Gherkin acceptance criteria
- Test-scenario IDs
- Qase test-case links
- Related Jira defect links

## Qase Repository Structure

The Qase repository follows the same functional structure used in Jira:

```text
01 - Authentication and Access Control
├── US_LOGIN_001: Log in using registered credentials
├── US_LOGIN_002: Validate required login fields
└── US_ACCESS_001: Control access to protected pages

02 - Product Catalogue
├── US_PROD_001: Browse available products
├── US_PROD_002: Sort available products
└── US_PROD_003: View individual product details

03 - Shopping Cart
├── US_CART_001: Add products to the shopping cart
├── US_CART_002: Review shopping-cart contents
├── US_CART_003: Remove products from the shopping cart
└── US_CART_004: Continue shopping without losing cart contents

04 - Checkout and Order Completion
├── US_CHK_001: Start checkout
├── US_CHK_002: Enter and validate checkout information
├── US_CHK_003: Review products and totals
├── US_CHK_004: Cancel checkout
└── US_CHK_005: Complete an order

05 - Session Management
├── US_LOGOUT_001: Log out securely
└── US_LOGOUT_002: Restore a saved cart after signing in again
```

## Requirements Traceability

Traceability was maintained between the requirements, Jira user stories, test scenarios, Qase test cases, test results, and defects.

### Traceability Matrix

| Epic | Jira User Story | Qase Test-Case Folder | Number of Test Cases |
|---|---|---|---:|
| Authentication and Access Control | `US_LOGIN_001` — Log in using registered credentials | `US_LOGIN_001: Log in using registered credentials` | 7 |
| Authentication and Access Control | `US_LOGIN_002` — Validate required login fields | `US_LOGIN_002: Validate required login fields` | 2 |
| Authentication and Access Control | `US_ACCESS_001` — Control access to protected pages | `US_ACCESS_001: Control access to protected pages` | 1 |
| Product Catalogue | `US_PROD_001` — Browse available products | `US_PROD_001: Browse available products` | 7 |
| Product Catalogue | `US_PROD_002` — Sort available products | `US_PROD_002: Sort available products` | 2 |
| Product Catalogue | `US_PROD_003` — View individual product details | `US_PROD_003: View individual product details` | 1 |
| Shopping Cart | `US_CART_001` — Add products to the shopping cart | `US_CART_001: Add products to the shopping cart` | 4 |
| Shopping Cart | `US_CART_002` — Review shopping-cart contents | `US_CART_002: Review shopping-cart contents` | 2 |
| Shopping Cart | `US_CART_003` — Remove products from the shopping cart | `US_CART_003: Remove products from the shopping cart` | 4 |
| Shopping Cart | `US_CART_004` — Continue shopping without losing cart contents | `US_CART_004: Continue shopping without losing cart contents` | 2 |
| Checkout and Order Completion | `US_CHK_001` — Start checkout | `US_CHK_001: Start checkout` | 2 |
| Checkout and Order Completion | `US_CHK_002` — Enter and validate checkout information | `US_CHK_002: Enter and validate checkout information` | 6 |
| Checkout and Order Completion | `US_CHK_003` — Review products and totals | `US_CHK_003: Review products and totals` | 4 |
| Checkout and Order Completion | `US_CHK_004` — Cancel checkout | `US_CHK_004: Cancel checkout` | 1 |
| Checkout and Order Completion | `US_CHK_005` — Complete an order | `US_CHK_005: Complete an order` | 2 |
| Session Management | `US_LOGOUT_001` — Log out securely | `US_LOGOUT_001: Log out securely` | 4 |
| Session Management | `US_LOGOUT_002` — Restore a saved cart after signing in again | `US_LOGOUT_002: Restore a saved cart after signing in again` | 1 |
| **Total** | **17 user stories** | **17 Qase user-story folders** | **52** |

### Traceability Example

The following example shows how one requirement is traced through the testing process:

| Traceability Level | Record |
|---|---|
| Requirement | `REQ-CART-002` |
| Jira User Story | `US_CART_002: Review shopping-cart contents` |
| Test Scenario | `TS_CART_005` |
| Qase Test Case | `TC_CART_005: Review product information in the cart` |
| Test Result | Passed, Failed, Blocked, or Skipped |
| Jira Defect | Created and linked if the test fails |
| Retest Result | Recorded in Qase after the defect is fixed |

The complete traceability path is:

```text
Requirement
    ↓
Jira Epic
    ↓
Jira User Story
    ↓
Acceptance Criteria
    ↓
Test Scenario
    ↓
Qase Test Case
    ↓
Qase Test Result
    ↓
Jira Defect
    ↓
Qase Retest Result
```

## Linking Jira and Qase

Because direct Jira–Qase integration was unavailable, Jira and Qase were linked manually.

### Jira to Qase

For each Jira user story:

1. Open the related test case in Qase.
2. Copy the Qase test-case URL.
3. Open the related user story in Jira.
4. Select **Add**.
5. Select **Web link**.
6. Paste the Qase test-case URL.
7. Use the test-case ID and title as the link name.

Example:

```text
TC_CART_005: Review product information in the cart
```

### Qase to Jira

The related Jira information was added to the Qase test-case description.

Example:

```text
Requirement: REQ-CART-002
Jira User Story: US_CART_002 — Review shopping-cart contents
Test Scenario: TS_CART_005
```

The Jira user-story URL was also added to the Qase test case. This created two-way traceability between Jira and Qase.

> The `SP` reference displayed next to a test case in Qase is a Qase-generated test-case reference. It is separate from the Jira issue key.

## Test Execution

Test runs were created in Qase to execute the SauceDemo test cases.

Each test case was assigned one of the following results:

| Result | Meaning |
|---|---|
| Passed | The actual result matched the expected result. |
| Failed | The actual result did not match the expected result. |
| Blocked | Testing could not continue because of an issue or dependency. |
| Skipped | The test case was not executed during the test run. |

Screenshots, comments, and other supporting evidence were added where required.

## Jira Kanban Workflow

| Board Column | Purpose |
|---|---|
| To Do | The user story is ready for testing. |
| In Testing | The related test cases are being executed in Qase. |
| Defect Found | One or more test cases failed and a defect was reported. |
| Retesting | The reported defect was fixed and the affected tests must be executed again. |
| Done | Testing and any required retesting were completed successfully. |

## Defect Management

When a Qase test case failed:

1. The failed result was recorded in Qase.
2. Supporting evidence was attached to the test result.
3. A defect was created in Jira.
4. The defect was linked to the affected Jira user story.
5. The Jira defect link was added to the Qase test case.
6. The user story was moved to **Defect Found**.
7. After the defect was fixed, the user story was moved to **Retesting**.
8. The affected test cases were executed again in Qase.
9. The retest results and evidence were recorded.
10. When retesting passed, the user story was moved to **Done**.

Each Jira defect contains:

- Defect ID
- Defect title
- Related requirement
- Related user story
- Related test-scenario ID
- Related Qase test-case ID
- Environment
- Preconditions
- Steps to reproduce
- Test data
- Expected result
- Actual result
- Severity
- Priority
- Supporting evidence
- Defect status
- Retest result

## Test Completion Criteria

Testing is considered complete when:

- All 52 planned test cases have been executed.
- Every test case has a recorded result.
- Failed test cases have linked Jira defects.
- Fixed defects have been retested.
- Retest evidence has been recorded.
- No unresolved critical defects remain.
- The related Jira user stories have been moved to **Done**.

## Project Links

- [SauceDemo Application](https://www.saucedemo.com/)
- [GitHub QA Project](https://github.com/PearlPhahlane/Practical_QA_Tester_Project)