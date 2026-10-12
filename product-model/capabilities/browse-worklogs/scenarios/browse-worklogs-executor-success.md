---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Read visible own recorded time for granted-record work."
    kind: "actor"
    actor: "external-executor"
    entities: []
    contexts:
      web-work:
        place: "web::work::task-detail"
      rest-work:
        place: "rest::work::worklog-collection"
  - text: "Own Worklog records are returned with permitted own payout fields only."
    kind: "product"
    actor: "external-executor"
    entities:
      - entity: "worklog"
        effect: "reads"
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
          - "Payout rate"
          - "Locked"
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

# Browse worklogs as external executor

## Trigger

Read visible own recorded time for granted-project work.

## Outcome

Own Worklog records are returned with permitted own payout fields only.
