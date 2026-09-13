# Test Plan

## 1. Document Information

| Field | Details |
|---|---|
| Project | Enterprise SaaS QA Project - Plane |
| Application | Plane |
| Testing Type | Manual Testing |
| Release | Initial QA Cycle |
| QA Role | Junior QA Engineer |
| Document | Test Plan |
| Status | Draft |

---

## 2. Objective

The objective of this test cycle is to verify that the selected Plane functionality works according to the expected business behavior and provides a reliable experience for authorized users.

The testing will focus on functional correctness, validation, user permissions, workflow behavior, data integrity, and important negative scenarios.

---

## 3. Scope

### In Scope

The following areas are included in the initial manual testing cycle:

### Workspace & Members
- Workspace access
- Workspace information
- Member management
- Member access
- Permission-related behavior

### Project Management
- Project creation
- Project viewing
- Project editing
- Project deletion where applicable
- Project access

### Work Item Management
- Work item creation
- Work item editing
- Work item assignment
- Status changes
- Priority
- Labels
- Dates
- Cycle/module association
- Work item deletion where applicable

### Cycle Management
- Cycle creation
- Cycle information
- Cycle dates
- Work item assignment
- Cycle updates
- Cycle completion behavior

---

## 4. Out of Scope

The following areas are not part of the initial manual testing cycle:

- Deep AI/AI feature testing
- Performance/load testing
- Penetration testing
- Source-code testing
- Full integration testing with every external service
- Full API automation
- Database automation
- Playwright automation
- REST Assured automation
- CI/CD implementation

These areas may be considered in later phases of the overall QA/SDET project.

---

## 5. Testing Approach

The testing approach will be risk-based and primarily manual.

Testing will progress through:

```text
Requirement Understanding
        ↓
Test Scenario Design
        ↓
Test Case Design
        ↓
Test Data Preparation
        ↓
Smoke Testing
        ↓
Functional Testing
        ↓
Negative Testing
        ↓
Exploratory Testing
        ↓
Defect Reporting
        ↓
Retesting
        ↓
Regression Testing
        ↓
Test Summary
```

Testing will prioritize business-critical workflows and areas with higher risk, particularly access control, data modification, work item management, and project/cycle relationships.

---

## 6. Types of Testing

The initial project will include:

### Functional Testing
Verify that features behave according to expected requirements.

### Smoke Testing
Verify that the application and critical functionality are stable enough for further testing.

### Sanity Testing
Perform focused verification after relevant changes or fixes.

### Regression Testing
Verify that changes and bug fixes have not broken existing functionality.

### Negative Testing
Verify system behavior when invalid, unexpected, or unauthorized actions are performed.

### Boundary Testing
Verify behavior around important limits such as dates, lengths, and allowed values where applicable.

### Exploratory Testing
Explore the product using structured test ideas to identify unexpected behavior that may not be covered by predefined test cases.

### Permission / Authorization Testing
Verify that users can perform only actions allowed by their permissions.

### Data Integrity Testing
Verify that data remains accurate and consistent across edits, refreshes, and multi-step actions, without being lost, duplicated, or corrupted.

### End-to-End Testing
Verify that a complete cross-module workflow (e.g. workspace access through project, work item, and cycle) behaves correctly as a whole, not just at each individual step.

---

## 7. Test Environment

### Application Environment

Testing will initially be performed using the available Plane web application.

### Client Environment

The initial test environment will include:

- Desktop/laptop
- Windows environment
- Modern Chromium-based browser
- Stable internet connection

Specific browser versions and environment details will be recorded during actual execution.

### Future Environment

A self-hosted Plane environment may be used later for deeper API and database testing where practical.

---

## 8. Test Data

Test data should be created specifically for testing rather than using unnecessary real personal information.

Examples include:

- Test workspace
- Test users
- Test projects
- Test work items
- Test cycles
- Valid and invalid input values
- Different user permission levels where available

Sensitive or real personal data should not be used.

---

## 9. Entry Criteria

Testing can begin when:

- Required functionality is accessible.
- Test environment is available.
- Required test accounts/data are available.
- Initial requirements are understood sufficiently to begin testing.
- Major environment/access issues are resolved.
- Test scenarios and priority test cases are prepared.

---

## 10. Exit Criteria

The initial testing cycle can be considered complete when:

- Planned high-priority test cases have been executed.
- Critical workflows have been tested.
- Major defects have been reported.
- Retesting of resolved high-priority defects has been completed.
- Required regression testing has been completed.
- Remaining known issues and risks are documented.
- Test execution results and metrics are recorded.
- A test summary/release recommendation has been prepared.

Exit criteria do not necessarily mean that zero defects remain.

A release decision should consider defect severity, business impact, risk, and known limitations.

---

## 11. Severity Classification

| Severity | Meaning |
|---|---|
| Critical | Prevents a critical business function or creates severe impact/data loss/security risk |
| High | Major functionality is broken and there is significant business/user impact |
| Medium | Functionality is affected but a workaround may exist |
| Low | Minor issue with limited functional or usability impact |

---

## 12. Priority Classification

| Priority | Meaning |
|---|---|
| P1 - High | Requires immediate attention |
| P2 - Medium | Should be fixed in the current cycle where practical |
| P3 - Low | Can be addressed later depending on priority |

Severity and priority should be assigned independently based on technical impact and business urgency.

---

## 13. Defect Management

Defects identified during execution will be documented using a Jira-style defect workflow.

Typical lifecycle:

```text
New
 ↓
Assigned
 ↓
In Progress
 ↓
Fixed
 ↓
Ready for Retest
 ↓
Retest
 ↓
Closed
```

Additional states may include:

- Reopened
- Duplicate
- Rejected
- Deferred
- Not a Bug

Each defect should contain sufficient information for another team member to reproduce and understand the issue.

---

## 14. Roles and Responsibilities

### QA Engineer

- Analyze requirements
- Identify test conditions
- Create test scenarios and test cases
- Prepare test data
- Execute tests
- Report defects
- Retest fixes
- Perform regression testing
- Maintain test evidence
- Prepare test reports

### Product / Business Team

- Clarify expected business behavior
- Confirm ambiguous requirements
- Help determine business priority

### Development Team

- Investigate defects
- Fix confirmed defects
- Provide fixes/builds for retesting
- Support technical clarification when required

---

## 15. Risk Management

Initial high-risk areas include:

| Risk ID | Area | Risk | Impact |
|---|---|---|---|
| R-001 | Permissions | Unauthorized user can access or modify restricted data | High |
| R-002 | Work Items | Incorrect updates or assignment | High |
| R-003 | Project | Accidental deletion or unauthorized changes | High |
| R-004 | Cycle | Incorrect handling of work at cycle completion | Medium |
| R-005 | Workspace | Incorrect member access | High |
| R-006 | Data | User changes are not correctly saved or displayed | High |

Risks will be refined after detailed test design and execution.

---

## 16. Defect Evidence

Where practical, defects should include evidence such as:

- Screenshot
- Screen recording
- Relevant test data
- Browser/environment details
- Exact reproduction steps

Evidence should avoid exposing sensitive or real personal information.

---

## 17. Test Deliverables

The following artifacts will be created during the testing cycle:

```text
Requirement Analysis
Requirement Questions
Test Plan
Test Scenarios
Test Cases
Test Data
RTM
Test Execution Report
Defect Reports
Regression Results
Test Summary Report
```

---

## 18. Overall QA Strategy

The initial goal is not to test every available Plane feature.

The goal is to provide meaningful coverage of the selected business-critical workflows and demonstrate a complete QA lifecycle:

```text
Understand
   ↓
Plan
   ↓
Design
   ↓
Execute
   ↓
Report
   ↓
Retest
   ↓
Regress
   ↓
Summarize
```

The project will prioritize **quality of testing and reasoning over the number of test cases**.