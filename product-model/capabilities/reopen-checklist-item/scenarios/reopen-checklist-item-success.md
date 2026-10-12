---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Reopen a completed item."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::task-detail"
      rest-work:
        place: "rest::work::task-record"
  - text: "The item list item becomes incomplete."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "checklist-item"
        effect: "changes"
        facts:
          - "Completed"
        from: "Complete"
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

# Reopen checklist item: successful operation

## Trigger

Reopen a completed item.

## Outcome

The Checklist item becomes incomplete.
