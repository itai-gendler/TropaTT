---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Request own earnings over dates containing more than one saved currency."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::my-earnings"
      rest-work:
        place: "rest::work::time-reports"
  - text: "Worklog-based payout totals remain grouped by Currency; no implicit currency conversion or payment occurs."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "worklog"
        effect: "reads"
        facts:
          - "Owner"
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

# Own earnings

## Trigger

Request own earnings over dates containing more than one saved currency.

## Outcome

Worklog-based payout totals remain grouped by Currency; no implicit currency conversion or payment occurs.
