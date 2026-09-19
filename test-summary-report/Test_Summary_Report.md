# Test summary report, Plane QA project

## 1. Overview

A one-week manual testing cycle covering Workspace/Members, Project, Work Item, and
Cycle management in Plane (app.plane.so), following the process defined in `Test_Plan.md`.

## 2. Scope covered

All in-scope areas from `Test_Plan.md` were covered: Workspace/Members, Project,
Work Item, and Cycle management, plus 4 cross-module End-to-End workflows. All 46
originally planned test cases (34 P1, 12 P2) were executed within the 1-week window,
nothing was descoped, and 1 more case (`TC-CYC-009`) was added mid-cycle after
exploratory testing found a gap in the original scripted coverage.

## 3. Execution metrics

47 test cases executed (46 originally scripted, 1 added after exploratory
testing): 44 Pass, 3 Fail, 93.6% pass rate. See
`Test_Execution_Report.md` for the per-module breakdown. Three low-severity
defects were logged (PMQP-1, PMQP-2, PMQP-3); no critical, high, or medium-severity
defects found. All 4 cases that briefly sat at Not Executed during review are now
resolved: `TC-PRJ-007`, `TC-WI-014`, and `TC-E2E-002` with proper redos and account
confirmation, and `TC-WI-009` by confirming Plane does reject an invalid
transition. Every case in the suite now has a final Pass or Fail.

## 4. Defect summary

Three defects logged, all Low severity:

- **PMQP-1** (P3): Work Item description field shows no visible character limit and
  noticeable input lag past ~500 characters (`TC-WI-003`).
- **PMQP-2** (P3): Cycle Progress panel shows "Infinity% of 0" for Started right
  after a work item is removed from a cycle. Self-corrects on refresh (`TC-CYC-005`).
- **PMQP-3** (P2): Cycle Progress panel shows a negative percentage ("-100% of 1")
  after a work item's priority/status are changed repeatedly (`TC-CYC-009`, added
  from exploratory testing).

All three are display/reporting-layer issues: no data loss, no core functionality
broken. Full detail in `Defect_Summary.md`.

## 5. Regression summary

A 6-case P1 regression pass was run across all five modules (see
`Regression_Summary.md`). 4 held up immediately; the other 2 (`TC-PRJ-007`,
`TC-WI-014`) needed a second look before they were properly confirmed. The same
review caught one more case outside the regression set with a similar problem
(`TC-E2E-002`), now also resolved, and one unrelated case (`TC-WI-009`) that just
needed the actual attempt made. All resolved.

## 6. Known issues and risks not covered

- No open test cases remain. All 47 are resolved to Pass or Fail.
- Two items from `Clarifications_Resolved.md` remain open and undocumented by
  Plane: the exact access-revocation timing on member removal (TC-WSP-008), and
  whether membership-change notifications are sent.
- Deep API/database-level testing and performance/load testing stay formally out
  of scope per `Test_Plan.md` 4.
- One exploratory session has been run (Cycle progress reporting) and it turned up
  real findings, see `exploratory-testing/session-charters-and-notes.md`. A second
  session on Work Item boundary fields is a reasonable next step, following up on
  the TC-WI-003 pattern.

## 7. Lessons learned

This testing cycle helped me understand a few important things about real-world testing:

1. **Understanding the product and requirements comes first.**
   Before writing and executing test cases, it is important to understand the product, its requirements, and how the different features work together. This helps in creating relevant test scenarios and finding issues more effectively.

2. **Proper documentation is important throughout the testing process.**
   Test cases, execution results, defects, retesting, and clarifications should be documented clearly. Good documentation makes it easier to track the testing process and understand what happened during the cycle.

3. **Exploratory testing is important even when all planned test cases are covered.**
   Completing the planned test cases does not always mean that all issues will be found. During exploratory testing, an additional issue was found in Cycle Progress that was not covered by the original test cases.

4. **Testing should also consider how different modules work together.**
   Some issues may not appear when a feature is tested separately but can appear when it interacts with another module. Cross-module and end-to-end testing therefore provide additional coverage.

5. **Automation should start with stable and repetitive scenarios.**
   If this project were extended into an automation project, stable regression and important end-to-end test cases would be good candidates for automation, while exploratory testing would continue to be performed manually.
