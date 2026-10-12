---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Request the current person's payout for valid dates."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::my-earnings"
      rest-work:
        place: "rest::work::time-reports"
  - text: "Own Worklog-based payout is calculated and grouped by currency; no payment is executed."
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
          - "Currency"
          - "Payout rate"
    contexts:
      web-work:
        place: "web::work::my-earnings"
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

# Browse own earnings: successful operation

## Trigger

Request the current person's payout for valid dates.

## Outcome

Own Worklog-based payout is calculated and grouped by currency; no payment is executed.
