---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Supply open granted-record work, activity, date and valid minutes."
    kind: "actor"
    actor: "external-executor"
    entities: []
    contexts:
      web-work:
        place: "web::work::task-detail"
      rest-work:
        place: "rest::work::worklog-collection"
  - text: "An own Worklog is saved for the granted-work container work."
    kind: "product"
    actor: "external-executor"
    entities:
      - entity: "worklog"
        effect: "creates"
        facts:
          - "Owner"
          - "Task"
          - "Project"
          - "Date"
          - "Minutes"
          - "Started at"
          - "Ended at"
          - "Note"
          - "Activity"
          - "Currency"
          - "Locked"
        to: "Unlocked"
    contexts:
      web-work:
        place: "web::work::task-detail"
      rest-work:
        place: "rest::work::worklog-collection"
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

# Log time as external executor

## Trigger

Supply open granted-project work, activity, date and valid minutes.

## Outcome

An own Worklog is saved for the granted-project work.
