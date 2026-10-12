---
kind: "validation"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "An invalid identity or missing payout availability yields an unavailable result."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::my-earnings"
      rest-work:
        place: "rest::work::time-reports"
  - text: "An invalid identity or missing payout availability yields an unavailable result."
    kind: "condition"
    actor: "root-administrator"
    entities: []
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

# Browse own earnings: refused or unavailable operation

## Trigger

An invalid identity or missing payout availability yields an unavailable result.

## Outcome

An invalid identity or missing payout availability yields an unavailable result.
