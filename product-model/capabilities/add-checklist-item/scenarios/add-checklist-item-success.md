---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Supply item text and optional ordering."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::task-detail"
      rest-work:
        place: "rest::work::task-record"
  - text: "A item list item is created incomplete."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "checklist-item"
        effect: "creates"
        facts:
          - "Text"
          - "Order"
          - "Completed"
        to: "Open"
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

# Add checklist item: successful operation

## Trigger

Supply item text and optional ordering.

## Outcome

A Checklist item is created incomplete.
