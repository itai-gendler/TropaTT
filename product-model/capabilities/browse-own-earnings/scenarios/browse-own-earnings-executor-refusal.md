---
kind: "validation"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Missing payout availability or invalid identity prevents the payout result."
    kind: "actor"
    actor: "external-executor"
    entities: []
    contexts:
      web-work:
        place: "web::work::my-earnings"
      rest-work:
        place: "rest::work::time-reports"
  - text: "Missing payout availability or invalid identity prevents the payout result."
    kind: "condition"
    actor: "external-executor"
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

# Browse own earnings external executor boundary

## Trigger

Missing payout availability or invalid identity prevents the payout result.

## Outcome

Missing payout availability or invalid identity prevents the payout result.
