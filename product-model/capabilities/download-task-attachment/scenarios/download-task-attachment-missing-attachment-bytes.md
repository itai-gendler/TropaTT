---
kind: "edge"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Download an accessible file record whose backing bytes are missing."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::task-detail"
      rest-work:
        place: "rest::work::task-record"
  - text: "Task attachment metadata resolves but byte delivery returns the storage-unavailable outcome."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "task-attachment"
        effect: "reads"
        facts:
          - "Name"
          - "Type"
          - "Size"
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

# Missing attachment bytes

## Trigger

Download an accessible file record whose backing bytes are missing.

## Outcome

Task attachment metadata resolves but byte delivery returns the storage-unavailable outcome.
