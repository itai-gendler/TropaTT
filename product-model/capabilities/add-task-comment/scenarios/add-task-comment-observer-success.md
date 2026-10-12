---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Supply nonempty discussion text for reachable customer work."
    kind: "actor"
    actor: "external-observer"
    entities: []
    contexts:
      web-work:
        place: "web::work::task-detail"
      rest-work:
        place: "rest::work::task-record"
  - text: "A Task comment is saved with forced customer visibility."
    kind: "product"
    actor: "external-observer"
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

# Add task comment as external observer

## Trigger

Supply nonempty discussion text for reachable customer work.

## Outcome

A Task comment is saved with forced client visibility.
