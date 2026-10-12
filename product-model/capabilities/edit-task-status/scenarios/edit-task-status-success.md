---
kind: "primary"
routes:
  web-administration: "Web Administration"
  rest-work: "Rest Work"
steps:
  - text: "Supply supported dictionary metadata."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-administration:
        place: "web::administration::task-statuses"
      rest-work:
        place: "rest::work"
  - text: "The Task status metadata changes."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "task-status"
        effect: "changes"
        facts:
          - "Title"
          - "Order"
          - "Active"
          - "Terminal"
          - "WIP limit"
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

# Edit task status: successful operation

## Trigger

Supply supported dictionary metadata.

## Outcome

The Task status metadata changes.
