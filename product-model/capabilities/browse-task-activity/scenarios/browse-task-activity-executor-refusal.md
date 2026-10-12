---
kind: "validation"
routes:
  rest-work: "Rest Work"
steps:
  - text: "Ungrantable work returns the work-not-found result."
    kind: "actor"
    actor: "external-executor"
    entities: []
    contexts:
      rest-work:
        place: "rest::work::task-record"
  - text: "Ungrantable work returns the work-not-found result."
    kind: "condition"
    actor: "external-executor"
    entities: []
    contexts:
      rest-work:
        place: "rest::work::task-record"
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

# Browse task activity external executor boundary

## Trigger

Ungrantable work returns TASK_NOT_FOUND.

## Outcome

Ungrantable work returns TASK_NOT_FOUND.
