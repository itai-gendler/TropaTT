---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Supply nonempty comment text and supported visibility."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::task-detail"
      rest-work:
        place: "rest::work::task-record"
  - text: "A sanitized Task comment is saved."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "task-comment"
        effect: "creates"
        facts:
          - "Body"
          - "Visibility"
          - "Author"
          - "Created at"
          - "Edited at"
    contexts:
      web-work:
        place: "web::work::task-detail"
      rest-work:
        place: "rest::work::task-record"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/CommentService.php"
---

# Add task comment: successful operation

## Trigger

Supply nonempty comment text and supported visibility.

## Outcome

A sanitized Task comment is saved.
