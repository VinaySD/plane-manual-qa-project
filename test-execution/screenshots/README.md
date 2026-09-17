# Evidence folder convention

Screenshots are organized by module, then priority, e.g.:

```
screenshots/
├── WSP - Workspace/
│   ├── P1/
│   │   ├── TC-WSP-001.png
│   │   └── TC-WSP-002.png
│   └── P2/
│       └── TC-WSP-006.png
├── PRJ - Project/
│   └── ...
```

Each file is named after the Test Case ID it evidences.

Guidelines:
- Capture the *result* that proves pass/fail (the validation message, the denied
  access screen, the saved field), not just a generic app screenshot.
- For negative/authorization cases, a screenshot of the blocked or denied state IS
  the evidence. That's often more valuable than a happy-path screenshot.
- Where one screenshot doesn't tell the whole story, add a second with a suffix
  (e.g. `TC-CYC-008-2.png`) rather than cramming everything into one image.
- Redact anything unnecessary. This is a public repo.

**Evidence policy:** full screenshot evidence is captured for all P1 cases. P2
cases get a screenshot only where they produced a logged defect or illustrate a
notable negative/boundary result (`TC-WI-003`, `TC-CYC-005`, `TC-WSP-006`,
`TC-PRJ-003`). Routine P2 passes are documented in `Test_Cases.xlsx` without a
screenshot. That's a deliberate scoping decision, not a gap.
