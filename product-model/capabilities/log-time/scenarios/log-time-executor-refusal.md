---
kind: "validation"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Ungrantable work returns the work-not-found result or an unavailable logging result."
    kind: "actor"
    actor: "external-executor"
    entities: []
    contexts:
      web-work:
        place: "web::work::task-detail"
      rest-work:
        place: "rest::work::worklog-collection"
  - text: "Ungrantable work returns the work-not-found result or an unavailable logging result."
    kind: "condition"
    actor: "external-executor"
    entities: []
    contexts:
      web-work:
        place: "web::work::task-detail"
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

# Log time external executor boundary

## Trigger

Ungrantable work returns TASK_NOT_FOUND or an unavailable logging result.

## Outcome

Ungrantable work returns TASK_NOT_FOUND or an unavailable logging result.
