---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Select a record for removal."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::task-detail"
      rest-work:
        place: "rest::work::task-record"
  - text: "The Checklist and its items are removed."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "checklist"
        effect: "removes"
      - entity: "checklist-item"
        effect: "removes"
        with: "checklist"
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

# Delete checklist: successful operation

## Trigger

The addressed checklist item starts Open. Select a checklist for removal.

## Outcome

The Checklist and its items are removed.
