---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Read work item lists and their items."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::task-detail"
      rest-work:
        place: "rest::work::task-record"
  - text: "Checklist and item facts are returned."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "checklist"
        effect: "reads"
        facts:
          - "Title"
          - "Order"
      - entity: "checklist-item"
        effect: "reads"
        facts:
          - "Text"
          - "Order"
          - "Completed"
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

# Browse checklists: successful operation

## Trigger

Read work checklists and their items.

## Outcome

Checklist and item facts are returned.
