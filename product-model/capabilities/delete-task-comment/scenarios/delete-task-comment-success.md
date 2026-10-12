---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Select an addressed comment to remove."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::task-detail"
      rest-work:
        place: "rest::work::task-record"
  - text: "The Task comment is removed by its supported deletion path."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "task-comment"
        effect: "removes"
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

# Delete task comment: successful operation

## Trigger

Select an addressed comment to remove.

## Outcome

The Task comment is removed by its supported deletion path.
