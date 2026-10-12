---
kind: "validation"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "An ungranted record returns no visible work or the work-not-found result."
    kind: "actor"
    actor: "external-executor"
    entities: []
    contexts:
      web-work:
        place: "web::work::tasks"
      rest-work:
        place: "rest::work::task-collection"
  - text: "An ungranted record returns no visible work or the work-not-found result."
    kind: "condition"
    actor: "external-executor"
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

# Browse tasks external executor boundary

## Trigger

An ungranted project returns no visible work or TASK_NOT_FOUND.

## Outcome

An ungranted project returns no visible work or TASK_NOT_FOUND.
