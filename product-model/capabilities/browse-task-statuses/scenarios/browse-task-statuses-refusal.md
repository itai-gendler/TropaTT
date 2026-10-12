---
kind: "validation"
routes:
  web-administration: "Web Administration"
  rest-work: "Rest Work"
steps:
  - text: "An invalid record context cannot return record dictionary entries."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-administration:
        place: "web::administration::task-statuses"
      rest-work:
        place: "rest::work"
  - text: "An invalid record context cannot return record dictionary entries."
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

# Browse task statuses: refused or unavailable operation

## Trigger

An invalid organization context cannot return task dictionary entries.

## Outcome

An invalid organization context cannot return task dictionary entries.
