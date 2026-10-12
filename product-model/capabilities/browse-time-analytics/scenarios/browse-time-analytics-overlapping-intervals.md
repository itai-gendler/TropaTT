---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Report two recorded intervals, 09:00–10:00 and 09:30–10:30, on the same date."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::time-analytics"
      rest-work:
        place: "rest::work::time-reports"
  - text: "The Worklog-based report distinguishes 120 recorded minutes, 90 unique minutes and 30 overlapping minutes, without rewriting either saved interval."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "worklog"
        effect: "reads"
        facts:
          - "Date"
          - "Minutes"
          - "Started at"
          - "Ended at"
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

# Overlapping intervals

## Trigger

Report two recorded intervals, 09:00–10:00 and 09:30–10:30, on the same date.

## Outcome

The Worklog-based report distinguishes 120 recorded minutes, 90 unique minutes and 30 overlapping minutes, without rewriting either saved interval.
