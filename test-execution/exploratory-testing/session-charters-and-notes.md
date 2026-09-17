# Exploratory testing: session charters and notes

## Session 

**Charter:** Explore Cycle progress reporting under unusual work-item state changes
(adding then removing a work item, cycling a work item's priority and status
repeatedly) to find display or data-consistency issues the scripted Cycle test
cases don't cover, using the Admin account.

| Field | Notes |
|---|---|
| Tester | Vinay Chaudhari |
| Duration | 45 minutes |
| Areas covered | Cycle Progress panel behavior: (1) adding then removing a work item from a cycle, checked before and after a page refresh; (2) repeatedly changing a single work item's Priority (Urgent, High, Medium, Low, None) and Status (Backlog, Todo, In Progress, Done, Cancelled) while it stayed in the cycle |
| Bugs / issues found | Two. First, a precise repro for the previously-logged Infinity% bug: it appears specifically right after removing a work item from a cycle, and self-corrects on refresh. Updated PMQP-2 and `TC-CYC-005` with the corrected steps. Second, a new finding: cycling a work item's priority and status produces a negative percentage ("Backlog: -100% of 1") in the Progress panel. Logged as PMQP-3 and added as a permanent regression case, `TC-CYC-009`. |
| Questions raised | Does the Progress panel recalculate fully on every state change, or does it apply incremental deltas that can drift (and go negative) over several changes? Worth asking whether this ever touches real reporting data or is purely a front-end display computation. |
| Follow-up needed | Worth one more short session on Work Item boundary fields, following up on TC-WI-003, to check whether the same "no limit shown" pattern shows up elsewhere (Cycle name, Comments). |

---

