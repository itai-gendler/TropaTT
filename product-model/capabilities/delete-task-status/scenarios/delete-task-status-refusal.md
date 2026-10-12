---
kind: "validation"
routes:
  web-administration: "Web Administration"
  rest-work: "Rest Work"
steps:
  - text: "An unavailable status identifier cannot be removed."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-administration:
        place: "web::administration::task-statuses"
      rest-work:
        place: "rest::work"
  - text: "An unavailable status identifier cannot be removed."
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

# Delete task status: refused or unavailable operation

## Trigger

An unavailable status identifier cannot be removed.

## Outcome

An unavailable status identifier cannot be removed.
