---
kind: "validation"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Empty or overlong comment content is rejected."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::task-detail"
      rest-work:
        place: "rest::work::task-record"
  - text: "Empty or overlong comment content is rejected."
    kind: "condition"
    actor: "root-administrator"
    entities: []
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

# Add task comment: refused or unavailable operation

## Trigger

Empty or overlong comment content is rejected.

## Outcome

Empty or overlong comment content is rejected.
