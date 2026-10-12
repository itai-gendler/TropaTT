---
kind: "validation"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "An inaccessible work reference returns the work-not-found result without saving discussion."
    kind: "actor"
    actor: "external-observer"
    entities: []
    contexts:
      web-work:
        place: "web::work::task-detail"
      rest-work:
        place: "rest::work::task-record"
  - text: "An inaccessible work reference returns the work-not-found result without saving discussion."
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
    target: "upload/api/system/library/service/CommentService.php"
---

# Add task comment external observer boundary

## Trigger

An inaccessible work reference returns TASK_NOT_FOUND without saving discussion.

## Outcome

An inaccessible work reference returns TASK_NOT_FOUND without saving discussion.
