---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Supply a valid bound file for granted-record work."
    kind: "actor"
    actor: "external-executor"
    entities: []
    contexts:
      web-work:
        place: "web::work::task-detail"
      rest-work:
        place: "rest::work::task-record"
  - text: "A Task attachment is stored with customer-visible treatment."
    kind: "product"
    actor: "external-executor"
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

# Upload task attachment as external executor

## Trigger

Supply a valid bound file for granted-project work.

## Outcome

A Task attachment is stored with client-visible treatment.
