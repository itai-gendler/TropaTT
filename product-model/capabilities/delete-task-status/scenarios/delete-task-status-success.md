---
kind: "primary"
routes:
  web-administration: "Web Administration"
  rest-work: "Rest Work"
steps:
  - text: "Delete an unused record-scope status."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-administration:
        place: "web::administration::task-statuses"
      rest-work:
        place: "rest::work"
  - text: "The Task status is removed."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "task-status"
        effect: "removes"
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

# Delete task status: successful operation

## Trigger

Delete an unused task-scope status.

## Outcome

The Task status is removed.
