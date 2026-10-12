---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Supply changed record title or ordering."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::task-detail"
      rest-work:
        place: "rest::work::task-record"
  - text: "Checklist metadata changes."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "checklist"
        effect: "changes"
        facts:
          - "Title"
          - "Order"
    contexts:
      web-work:
        place: "web::work::task-detail"
      rest-work:
        place: "rest::work::task-record"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/checklist/ChecklistController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/ChecklistService.php"
---

# Edit checklist: successful operation

## Trigger

Supply changed checklist title or ordering.

## Outcome

Checklist metadata changes.
