---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Supply supported changes to an unlocked entry."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::time-analytics"
      rest-work:
        place: "rest::work::worklog-record"
  - text: "Worklog time, interval or note facts change."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "worklog"
        effect: "changes"
        facts:
          - "Date"
          - "Minutes"
          - "Started at"
          - "Ended at"
          - "Note"
          - "Activity"
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

# Edit worklog: successful operation

## Trigger

Supply supported changes to an unlocked entry.

## Outcome

Worklog time, interval or note facts change.
