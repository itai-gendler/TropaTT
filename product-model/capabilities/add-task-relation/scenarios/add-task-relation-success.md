---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Supply distinct reachable endpoints, a supported relation kind and optional note."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::task-detail"
      rest-work:
        place: "rest::work::task-record"
  - text: "A normalized Task relation is kept."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "task-relation"
        effect: "creates"
        facts:
          - "Source"
          - "Target"
          - "Kind"
          - "Note"
          - "Creator"
          - "Created at"
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

# Add task relation: successful operation

## Trigger

Supply distinct reachable endpoints, a supported relation kind and optional note.

## Outcome

A normalized Task relation is kept.
