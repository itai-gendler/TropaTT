---
kind: "validation"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "A foreign-customer request returns an empty filtered list or the work-not-found result."
    kind: "actor"
    actor: "external-observer"
    entities: []
    contexts:
      web-work:
        place: "web::work::tasks"
      rest-work:
        place: "rest::work::task-collection"
  - text: "A foreign-customer request returns an empty filtered list or the work-not-found result."
    kind: "condition"
    actor: "external-observer"
    entities: []
    contexts:
      web-work:
        place: "web::work::tasks"
      rest-work:
        place: "rest::work::task-collection"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/task/TaskController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/TaskService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/model/task/TaskRepository.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/support/TaskStatusSemantics.php"
---

# Browse tasks external observer boundary

## Trigger

A foreign-customer request returns an empty filtered list or TASK_NOT_FOUND.

## Outcome

A foreign-customer request returns an empty filtered list or TASK_NOT_FOUND.
