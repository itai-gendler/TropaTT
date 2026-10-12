---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Select a bound file for removal."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::task-detail"
      rest-work:
        place: "rest::work::task-record"
  - text: "The Task attachment receives its logical removal designation."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "task-attachment"
        effect: "removes"
    contexts:
      web-work:
        place: "web::work::task-detail"
      rest-work:
        place: "rest::work::task-record"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/file/FileController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/FileService.php"
---

# Remove task attachment: successful operation

## Trigger

Select a bound file for removal.

## Outcome

The Task attachment receives its logical removal designation.
