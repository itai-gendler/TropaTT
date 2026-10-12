---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Read record-visible files bound to linked-customer work."
    kind: "actor"
    actor: "external-observer"
    entities: []
    contexts:
      web-work:
        place: "web::work::task-detail"
      rest-work:
        place: "rest::work::task-record"
  - text: "customer-visible Task attachment metadata is returned."
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

# Browse task attachments as external observer

## Trigger

Read client-visible files bound to linked-customer work.

## Outcome

Client-visible Task attachment metadata is returned.
