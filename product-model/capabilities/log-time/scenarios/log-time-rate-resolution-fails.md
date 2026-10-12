---
kind: "edge"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Log valid time when rate resolution or snapshot persistence fails after the time entry is saved."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::time-analytics"
      rest-work:
        place: "rest::work::worklog-collection"
  - text: "The Worklog remains saved and unlocked; successful financial snapshot resolution is not required for the saved time result."
    kind: "product"
    actor: "root-administrator"
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
        place: "web::work::time-analytics"
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

# Rate resolution fails

## Trigger

Log valid time when rate resolution or snapshot persistence fails after the time entry is saved.

## Outcome

The Worklog remains saved and unlocked; successful financial snapshot resolution is not required for the saved time result.
