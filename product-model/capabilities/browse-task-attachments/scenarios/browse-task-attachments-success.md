---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Read attachments bound to selected work."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::task-detail"
      rest-work:
        place: "rest::work::task-record"
  - text: "Task attachment metadata is returned."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "task-attachment"
        effect: "reads"
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

# Browse task attachments: successful operation

## Trigger

Read attachments bound to selected work.

## Outcome

Task attachment metadata is returned.
