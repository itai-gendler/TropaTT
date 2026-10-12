---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Supply changed item text or ordering."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::task-detail"
      rest-work:
        place: "rest::work::task-record"
  - text: "item list item text or order changes."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "checklist-item"
        effect: "changes"
        facts:
          - "Text"
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

# Edit checklist item: successful operation

## Trigger

Supply changed item text or ordering.

## Outcome

Checklist item text or order changes.
