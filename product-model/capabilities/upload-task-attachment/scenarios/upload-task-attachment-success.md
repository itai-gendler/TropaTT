---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Supply a supported file bound to existing work."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::task-detail"
      rest-work:
        place: "rest::work::task-record"
  - text: "A Task attachment and its stored bytes are kept with upload and visibility facts."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "task-attachment"
        effect: "creates"
        facts:
          - "Name"
          - "Type"
          - "Size"
          - "Visibility"
          - "Uploader"
          - "Quarantined"
          - "Deleted at"
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

# Upload task attachment: successful operation

## Trigger

Supply a supported file bound to existing work.

## Outcome

A Task attachment and its stored bytes are kept with upload and visibility facts.
