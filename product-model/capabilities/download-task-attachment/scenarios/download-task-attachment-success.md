---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Request download of an addressed available attachment."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::task-detail"
      rest-work:
        place: "rest::work::task-record"
  - text: "Task attachment bytes are streamed with safe content treatment."
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
          - "Quarantined"
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

# Download task attachment: successful operation

## Trigger

Request download of an addressed available attachment.

## Outcome

Task attachment bytes are streamed with safe content treatment.
