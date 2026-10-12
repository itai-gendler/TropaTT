---
kind: "validation"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Internal and foreign files are excluded."
    kind: "actor"
    actor: "external-observer"
    entities: []
    contexts:
      web-work:
        place: "web::work::task-detail"
      rest-work:
        place: "rest::work::task-record"
  - text: "Internal and foreign files are excluded."
    kind: "condition"
    actor: "external-observer"
    entities: []
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

# Browse task attachments external observer boundary

## Trigger

Internal and foreign files are excluded.

## Outcome

Internal and foreign files are excluded.
