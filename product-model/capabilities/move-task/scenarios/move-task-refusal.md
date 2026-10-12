---
kind: "validation"
routes:
  rest-work: "Rest Work"
steps:
  - text: "An unavailable destination or work identifier prevents dedicated movement."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work::task-record"
  - text: "An unavailable destination or work identifier prevents dedicated movement."
    kind: "condition"
    actor: "root-administrator"
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

# Move task: refused or unavailable operation

## Trigger

An unavailable destination or work identifier prevents dedicated movement.

## Outcome

An unavailable destination or work identifier prevents dedicated movement.
