---
kind: "validation"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Self-relation or unsupported kind is rejected."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::task-detail"
      rest-work:
        place: "rest::work::task-record"
  - text: "Self-relation or unsupported kind is rejected."
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

# Add task relation: refused or unavailable operation

## Trigger

Self-relation or unsupported kind is rejected.

## Outcome

Self-relation or unsupported kind is rejected.
