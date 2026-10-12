---
kind: "validation"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Internal or foreign files return an unavailable download result."
    kind: "actor"
    actor: "external-observer"
    entities: []
    contexts:
      web-work:
        place: "web::work::task-detail"
      rest-work:
        place: "rest::work::task-record"
  - text: "Internal or foreign files return an unavailable download result."
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

# Download task attachment external observer boundary

## Trigger

Internal or foreign files return an unavailable download result.

## Outcome

Internal or foreign files return an unavailable download result.
