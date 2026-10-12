---
kind: "validation"
routes:
  rest-work: "Rest Work"
steps:
  - text: "An unavailable work identifier cannot be reparented."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work::task-record"
  - text: "An unavailable work identifier cannot be reparented."
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

# Remove task parent: refused or unavailable operation

## Trigger

An unavailable work identifier cannot be reparented.

## Outcome

An unavailable work identifier cannot be reparented.
