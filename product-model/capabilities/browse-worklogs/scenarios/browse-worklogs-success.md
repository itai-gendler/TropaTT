---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Read visible recorded time with supported person, work and date filters."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::time-analytics"
      rest-work:
        place: "rest::work::worklog-collection"
  - text: "Worklog records are returned with response-specific financial filtering."
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

# Browse worklogs: successful operation

## Trigger

Read visible recorded time with supported person, work and date filters.

## Outcome

Worklog records are returned with response-specific financial filtering.
