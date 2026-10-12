---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Supply a record title and ordering."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::task-detail"
      rest-work:
        place: "rest::work::task-record"
  - text: "A Checklist is created under the selected work."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "checklist"
        effect: "creates"
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

# Create checklist: successful operation

## Trigger

Supply a checklist title and ordering.

## Outcome

A Checklist is created under the selected work.
