---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Read typed relationships of selected work."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::task-detail"
      rest-work:
        place: "rest::work::task-record"
  - text: "Task relation records are returned."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "task-relation"
        effect: "reads"
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

# Browse task relations: successful operation

## Trigger

Read typed relationships of selected work.

## Outcome

Task relation records are returned.
