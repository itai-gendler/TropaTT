---
kind: "edge"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Upload a supported file meeting a configured quarantine condition."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::task-detail"
      rest-work:
        place: "rest::work::task-record"
  - text: "A Task attachment is stored with Quarantined treatment; download uses safe disposition and content handling."
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

# Configured quarantine condition

## Trigger

Upload a supported file meeting a configured quarantine condition.

## Outcome

A Task attachment is stored with Quarantined treatment; download uses safe disposition and content handling.
