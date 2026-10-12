---
kind: "edge"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Add a canonical typed relationship already active between the same endpoints."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::task-detail"
      rest-work:
        place: "rest::work::task-record"
  - text: "The duplicate relationship is refused rather than creating another entry."
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

# Duplicate active typed relation

## Trigger

Add a canonical typed relationship already active between the same endpoints.

## Outcome

The duplicate relationship is refused rather than creating another entry.
