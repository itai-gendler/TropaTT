---
kind: "validation"
routes:
  rest-work: "Rest Work"
steps:
  - text: "Invalid explicit record context prevents a valid activity-code result."
    kind: "actor"
    actor: "external-executor"
    entities: []
    contexts:
      rest-work:
        place: "rest::work"
  - text: "Invalid explicit record context prevents a valid activity-code result."
    kind: "condition"
    actor: "external-executor"
    entities: []
    contexts:
      rest-work:
        place: "rest::work"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/status/StatusController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/StatusService.php"
---

# Browse task statuses external executor boundary

## Trigger

Invalid explicit organization context prevents a valid activity-code result.

## Outcome

Invalid explicit organization context prevents a valid activity-code result.
