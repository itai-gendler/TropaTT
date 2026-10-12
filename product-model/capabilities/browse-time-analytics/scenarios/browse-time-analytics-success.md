---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Request a valid reporting period and visible work/person filters."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::time-analytics"
      rest-work:
        place: "rest::work::time-reports"
  - text: "Worklog-based recorded, unique and overlapping time calculations are returned with permitted financial calculations."
    kind: "product"
    actor: "root-administrator"
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
          - "Cost rate"
          - "Bill rate"
          - "Payout rate"
          - "Provenance"
          - "Locked"
    contexts:
      web-work:
        place: "web::work::time-analytics"
      rest-work:
        place: "rest::work::time-reports"
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

# Browse time analytics: successful operation

## Trigger

Request a valid reporting period and visible work/person filters.

## Outcome

Worklog-based recorded, unique and overlapping time calculations are returned with permitted financial calculations.
