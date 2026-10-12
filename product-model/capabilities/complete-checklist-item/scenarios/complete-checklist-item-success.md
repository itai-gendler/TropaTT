---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Mark an incomplete item complete."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::task-detail"
      rest-work:
        place: "rest::work::task-record"
  - text: "The item list item becomes complete."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "checklist-item"
        effect: "changes"
        facts:
          - "Completed"
        from: "Open"
        to: "Complete"
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

# Complete checklist item: successful operation

## Trigger

Mark an incomplete item complete.

## Outcome

The Checklist item becomes complete.
