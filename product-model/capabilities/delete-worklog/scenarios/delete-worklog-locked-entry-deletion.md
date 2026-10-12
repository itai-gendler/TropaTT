---
kind: "edge"
routes:
  rest-work: "Rest Work"
steps:
  - text: "Delete an addressed locked time entry through the inspected deletion path."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work::worklog-record"
  - text: "The Worklog is removed because this path does not apply the ordinary edit lock check."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "worklog"
        effect: "removes"
        from: "Locked"
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

# Locked entry deletion

## Trigger

The addressed worklog starts Locked. Delete an addressed locked time entry through the inspected deletion path.

## Outcome

The Worklog is removed because this path does not apply the ordinary edit lock check.
