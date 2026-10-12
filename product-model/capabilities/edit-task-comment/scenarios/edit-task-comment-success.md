---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Supply supported replacement comment text."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::task-detail"
      rest-work:
        place: "rest::work::task-record"
  - text: "The Task comment body changes and its edit date is recorded."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "task-comment"
        effect: "changes"
        facts:
          - "Body"
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

# Edit task comment: successful operation

## Trigger

Supply supported replacement comment text.

## Outcome

The Task comment body changes and its edit date is recorded.
