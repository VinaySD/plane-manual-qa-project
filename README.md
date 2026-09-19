# Plane Manual QA Project

![Testing](https://img.shields.io/badge/testing-manual-blue) ![Test%20Cases](https://img.shields.io/badge/test%20cases-47-informational) ![Pass%20Rate](https://img.shields.io/badge/pass%20rate-93.6%25-brightgreen) ![Status](https://img.shields.io/badge/status-complete-success)

A full manual QA cycle on [Plane](https://plane.so/), a real project/work-management
SaaS platform, used here as the System Under Test. It follows the same STLC steps a
QA engineer would use on a real team: requirement analysis, test planning, test
design, execution, defect management, regression, and reporting.

> Live SUT: [app.plane.so](https://app.plane.so/) · Docs: [developers.plane.so](https://developers.plane.so/)

## Why a real product instead of a demo site

Most fresher QA projects test a seeded demo app where the bugs are already known.
This one tests a live SaaS product instead, so the ambiguity, the requirement gaps,
and the defects are all real (not planted), and they're tracked through an actual
Jira workflow instead of just a spreadsheet.

## Scope

- Workspace & Members (access, roles, permission-based actions)
- Project Management (create / view / edit / delete)
- Work Item Management (create / edit / assign / status / labels / dates / cycle linkage)
- Cycle Management (create / dates / work-item assignment / completion behavior)

Full scope and out-of-scope rationale: [`Test_Plan.md`](./02-test-plan/Test_Plan.md).

## Test coverage

| Module | Test Scenarios | Test Cases |
|---|---|---|
| Workspace / Members | 9 | 9 |
| Project | 10 | 10 |
| Work Item | 15 | 15 |
| Cycle | 9 | 9 |
| End-to-End | 4 | 4 |
| **Total** | **47** | **47** |

(46 were originally scripted; 1 more was added mid-cycle after exploratory testing
turned up a bug the original suite didn't cover. See
`exploratory-testing/session-charters-and-notes.md`.)

## Execution status

Full breakdown: [`Test_Execution_Report.md`](./06-test-execution/Test_Execution_Report.md) · Release recommendation: [`Test_Summary_Report.md`](./09-test-summary-report/Test_Summary_Report.md)

| Metric | Value |
|---|---|
| Executed | 47 / 47 |
| Passed | 44 |
| Failed | 3 |
| Defects logged (Jira) | 3, all Low severity, display/reporting-layer only, no data loss |

## Folder guide

| Folder | Contents |
|---|---|
| `requirement-analysis/` | Functional/business analysis, negative scenarios, risks, and a resolved-clarifications log |
| `test-plan/` | Scope, approach, severity/priority model, defect lifecycle, entry/exit criteria |
| `test-scenarios/` | 47 high-level test scenarios |
| `test-cases/` | 47 detailed, executable test cases |
| `rtm/` | Requirement Traceability Matrix |
| `test-execution/` | Execution report, evidence screenshots, exploratory testing session notes |
| `defect-reports/` | Defect summary and Jira board snapshot |
| `regression-testing/` | Regression cycle results |
| `test-summary-report/` | Final release-recommendation report |

## Process and tools

| Phase | Tool |
|---|---|
| Test design & traceability | Excel (Test Scenarios, Test Cases, RTM) |
| Defect tracking | Jira (Kanban, custom workflow matching this project's defect lifecycle) |
| Execution evidence | Screenshots |
| Version control | Git / GitHub |

## Differentiators

- Tests a real, live SaaS product, not a static demo
- Full defect lifecycle tracked in Jira, not just a spreadsheet of bugs found
- Exploratory testing sessions with written charters, alongside scripted test cases
- A requirement-clarification log resolved against the product's actual docs and
  behavior instead of guessed
- A real regression pass, not a one-and-done execution round
- End-to-end workflow test cases, not just isolated module checks

## What's next

This is Phase 1 (manual). Phase 2 will take the highest-value P1 regression cases
from here and automate them using the Selenium/Java/TestNG framework from my other
project, [`selenium-java-hybrid-framework`](https://github.com/VinaySD/selenium-java-hybrid-framework).

## Author

**Vinay Chaudhari**, Computer Engineering, SPPU (2026), QA Automation / SDET
[GitHub](https://github.com/VinaySD) · [LinkedIn](https://linkedin.com/in/vinay-chaudhari-qa) · cvinay1925@gmail.com
