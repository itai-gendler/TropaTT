---
kind: "validation"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Add a guarded typed relationship that closes a prohibited cycle."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::task-detail"
      rest-work:
        place: "rest::work::task-record"
  - text: "The relation cycle is refused without creating the entry."
    kind: "condition"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::task-detail"
      rest-work:
        place: "rest::work::task-record"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/task/TaskRelationController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/TaskRelationService.php"
---

# Guarded relation cycle

## Trigger

Add a guarded typed relationship that closes a prohibited cycle.

## Outcome

The relation cycle is refused without creating the entry.
