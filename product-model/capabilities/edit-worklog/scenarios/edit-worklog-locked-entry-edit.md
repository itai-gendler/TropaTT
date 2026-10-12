---
kind: "validation"
routes:
  rest-work: "Rest Work"
steps:
  - text: "Edit an entry carrying a lock designation."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work::worklog-record"
  - text: "The lock check refuses the ordinary edit and the entry remains unchanged."
    kind: "condition"
    actor: "root-administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work::worklog-record"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/worklog/WorklogController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/WorklogService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/EarningsService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/security/FinancialFieldPolicy.php"
---

# Locked entry edit

## Trigger

Edit an entry carrying a lock designation.

## Outcome

The lock check refuses the ordinary edit and the entry remains unchanged.
