---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Select a record for deletion."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::task-detail"
      rest-work:
        place: "rest::work::task-record"
  - text: "The item list item is removed."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "checklist-item"
        effect: "removes"
        from: "Open"
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

# Delete checklist item: successful operation

## Trigger

The addressed checklist item starts Open. Select a checklist item for deletion.

## Outcome

The Checklist item is removed.
