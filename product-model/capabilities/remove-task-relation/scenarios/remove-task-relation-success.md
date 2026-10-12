---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Select an existing typed relationship to remove."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::task-detail"
      rest-work:
        place: "rest::work::task-record"
  - text: "The Task relation is removed."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "task-relation"
        effect: "removes"
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

# Remove task relation: successful operation

## Trigger

Select an existing typed relationship to remove.

## Outcome

The Task relation is removed.
