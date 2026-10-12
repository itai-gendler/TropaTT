---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Read record-visible discussion for linked-customer work."
    kind: "actor"
    actor: "external-observer"
    entities: []
    contexts:
      web-work:
        place: "web::work::task-detail"
      rest-work:
        place: "rest::work::task-record"
  - text: "customer-visible Task comment records are returned."
    kind: "product"
    actor: "external-observer"
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

# Browse task comments as external observer

## Trigger

Read client-visible discussion for linked-customer work.

## Outcome

Client-visible Task comment records are returned.
