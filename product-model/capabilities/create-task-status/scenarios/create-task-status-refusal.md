---
kind: "validation"
routes:
  web-administration: "Web Administration"
  rest-work: "Rest Work"
steps:
  - text: "Missing scope, code or title is rejected."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-administration:
        place: "web::administration::task-statuses"
      rest-work:
        place: "rest::work"
  - text: "Missing scope, code or title is rejected."
    kind: "condition"
    actor: "root-administrator"
    entities: []
    contexts:
      web-administration:
        place: "web::administration::task-statuses"
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

# Create task status: refused or unavailable operation

## Trigger

Missing scope, code or title is rejected.

## Outcome

Missing scope, code or title is rejected.
