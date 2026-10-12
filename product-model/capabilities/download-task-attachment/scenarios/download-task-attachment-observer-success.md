---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Download a record-visible file on linked-customer work."
    kind: "actor"
    actor: "external-observer"
    entities: []
    contexts:
      web-work:
        place: "web::work::task-detail"
      rest-work:
        place: "rest::work::task-record"
  - text: "Task attachment bytes are streamed with safe treatment."
    kind: "product"
    actor: "external-observer"
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

# Download task attachment as external observer

## Trigger

Download a client-visible file on linked-customer work.

## Outcome

Task attachment bytes are streamed with safe treatment.
