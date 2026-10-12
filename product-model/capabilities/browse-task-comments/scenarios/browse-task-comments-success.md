---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Read comments on selected work."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::task-detail"
      rest-work:
        place: "rest::work::task-record"
  - text: "Task comment bodies and visibility are returned within the response subset."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "task-comment"
        effect: "reads"
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

# Browse task comments: successful operation

## Trigger

Read comments on selected work.

## Outcome

Task comment bodies and visibility are returned within the response subset.
