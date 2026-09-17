# Test execution report, Plane QA project

## Environment

| Field | Value |
|---|---|
| Application under test | Plane, [app.plane.so](https://app.plane.so/) |
| Test workspaces | QA Demo Workspace, QA Demo Test |
| OS |  Windows 11 |
| Browser | Microsoft Edge 152.0.4191.53, Google Chrome 152.0.7977.83 |
| Test accounts used | Owner: codewithvinaysd@gmail.com Admin: cvinay1925@gmail.com · Member: vinayvsd19125@gmail.com (later switched to Admin) · Guest: vinusd1925@gmail.com |
| Execution period | Sep 12 to Sep 17, 2026, plus a regression pass and exploratory session after |
| Executed by | Vinay Chaudhari |

## Execution summary by module

| Module | Total Cases | Passed | Failed | Pass % |
|---|---|---|---|---|
| Workspace / Members | 9 | 9 | 0 | 100% |
| Project | 10 | 10 | 0 | 100% |
| Work Item | 15 | 14 | 1 | 93.3% |
| Cycle | 9 | 7 | 2 | 77.8% |
| End-to-End | 4 | 4 | 0 | 100% |
| **Total** | **47** | **44** | **3** | **93.6%** |

Cycle's total includes `TC-CYC-009`, added after exploratory testing found a bug
the original scripted suite didn't cover, so the scripted 46 grew to 47 the way a
real regression suite grows over time.

Three low-severity defects turned up (PMQP-1, PMQP-2, PMQP-3, see `Defect_Summary.md`).
All are display/reporting-layer issues: no data loss, no core functionality broken.

All 47 cases are now resolved to Pass or Fail. Four cases briefly sat at Not
Executed along the way, not because they weren't attempted, but because the
*captured evidence* didn't actually demonstrate what each case needed to prove
(`TC-PRJ-007`, `TC-WI-014`, `TC-WI-009`, `TC-E2E-002`). All four are now closed:
`TC-PRJ-007` with a proper redo, `TC-WI-014` and `TC-E2E-002` by confirming the
actual account role progression used (Guest/Member with no access, then switched
to Admin with full access), and `TC-WI-009` by confirming the interface actually
rejects an invalid transition. Full detail in `Test_Cases.xlsx` and
`Regression_Summary.md`.

## Screenshots / evidence

Evidence lives under `06-test-execution/screenshots/`, organized by module and then
priority (e.g. `WSP - Workspace/P1/TC-WSP-001.png`). See the `README.md` in that
folder for the naming convention and what gets a screenshot versus a text-only result.
