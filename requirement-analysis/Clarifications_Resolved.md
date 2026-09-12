# Clarifications resolved

This log tracks the "Clarifications Required" items raised in `Requirement_Analysis.md`.
On a real project these would go to a product or business contact. On a solo
project, it's on the QA engineer to resolve what's answerable from official
documentation and product behavior, and flag clearly what still needs testing to
confirm. Both are logged here.

## Workspace / Member management

| # | Open Question | Resolution | Status |
|---|---|---|---|
| 1 | What exact workspace roles and permissions exist? | Plane defines three workspace roles. **Admin** manages workspace settings, members, and billing (full workspace governance). **Member** can create and manage projects and work items and can see the full member list, but can't change workspace structure or invite others. **Guest** only sees the specific projects they're invited into and can't see the broader member list or workspace settings. | Confirmed, Plane official docs (docs.plane.so, Member Roles) |
| 2 | Who can invite or remove members? | Member invitations and removals happen under Workspace Settings > Members, an area restricted to Admins. | Confirmed, Plane official docs |
| 3 | Can a user belong to multiple workspaces? | Yes. A user can belong to and switch between multiple workspaces from the workspace dropdown, as long as the same email is used across them. | Confirmed, Plane official docs (Workspaces overview) |
| 4 | What happens when a member is removed from a workspace? | Partially confirmed via `TC-WSP-008`: the removed member's row stays visible in the Workspace Members list, but their Status changes to **Suspended** rather than the row being deleted outright. Whether their existing session loses access immediately or only on next login was not directly tested, that part is a genuine open item, not something to guess at. | Partially confirmed, access-timing still open |
| 5 | Are users notified when their workspace membership changes? | Not verified during execution. No email or in-app notification was specifically checked for during `TC-WSP-004`/`TC-WSP-008`. Left as an honest open item rather than a guessed answer. | Open |

## Project / Work Item / Cycle management

The remaining clarification items in these sections (project transfer between
workspaces, work-item deletion recovery, cycle reopening, overlapping cycles, and
so on) aren't documented well enough to answer with confidence in advance. These
are things you're expected to discover by using the product, which is
realistic: a QA engineer routinely has to establish actual system behavior when
it isn't written down anywhere. Log what you find for each as you execute the
related test case, either directly in this file or in the RTM's "Risk / Gap" column.

**Source referenced above:** Plane official documentation, docs.plane.so, paraphrased, not quoted.