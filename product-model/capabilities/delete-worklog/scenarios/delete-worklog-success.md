---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Select an addressed time entry for deletion."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::time-analytics"
      rest-work:
        place: "rest::work::worklog-record"
  - text: "The Worklog is removed; the ordinary edit lock check is not inherited."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "worklog"
        effect: "removes"
        from: "Unlocked"
    contexts:
      web-work:
        place: "web::work::time-analytics"
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

# Delete worklog: successful operation

## Trigger

The addressed worklog starts Unlocked. Select an addressed time entry for deletion.

## Outcome

The Worklog is removed; the ordinary edit lock check is not inherited.
