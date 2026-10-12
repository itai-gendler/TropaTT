---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Request own payout with valid dates and an own-payout-enabled credential."
    kind: "actor"
    actor: "external-executor"
    entities: []
    contexts:
      web-work:
        place: "web::work::my-earnings"
      rest-work:
        place: "rest::work::time-reports"
  - text: "Own Worklog-based payout is returned by currency."
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

# Browse own earnings as external executor

## Trigger

Request own payout with valid dates and an own-payout-enabled credential.

## Outcome

Own Worklog-based payout is returned by currency.
