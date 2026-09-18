# Regression summary, Plane QA project

## Purpose

Regression testing here checks whether investigating one thing broke or clarified
another, the same mindset a real QA cycle needs, even though Plane is a live
third-party product where you don't control the fix cycle. The set below is a
deliberately re-run cross-section of P1 cases spanning every module, executed a
second time after the main execution and defect-triage pass.

## Regression results

| Test Case ID | First Run Result | Regression Result | Notes |
|---|---|---|---|
| TC-PRJ-004 | Pass | Pass | Confirmed; only caught a Join-gate flow worth a follow-up screenshot of the post-join view |
| TC-PRJ-007 | Pass | Pass | First redo had wrong evidence (work-item creation, not project edit); second redo showed the "..." menu on the project card correctly limited to Copy link for this account |
| TC-WI-007 | Pass | Pass | Confirmed |
| TC-WI-014 | Pass | Pass | Confirmed via role progression on vinayvsd19125@gmail.com: no access as Guest/Member, full Delete access after switching to Admin |
| TC-CYC-003 | Pass | Pass | Confirmed |
| TC-E2E-004 | Pass | Pass | Confirmed |

## Conclusion

This regression pass turned out to be more useful than expected: it didn't just
confirm stability, it caught that 2 of the 6 cases (`TC-PRJ-007`, `TC-WI-014`) had
been marked Pass on evidence that didn't actually demonstrate their stated
scenario. Both are now resolved: `TC-PRJ-007` with a proper redo, `TC-WI-014` by
confirming the actual role progression used (Guest/Member with no access, then
switched to Admin with full access). The other 4 held up on a second pass with no
new issues. The same evidence-matches-scenario check turned up two more cases
outside this regression set with similar problems, `TC-E2E-002` (resolved the
same way as `TC-WI-014`) and `TC-WI-009` (an unrelated invalid-transition case,
resolved by actually attempting the transition and confirming it's rejected).
Every case in the suite now has a confirmed outcome.
