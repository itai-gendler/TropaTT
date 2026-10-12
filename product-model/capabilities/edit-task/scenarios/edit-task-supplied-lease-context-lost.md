---
kind: "edge"
routes:
  rest-work: "Rest Work"
steps:
  - text: "Submit an ordinary edit with a supplied token/run/generation that no longer holds the lease."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work::task-record"
  - text: "The lost lease context is rejected without saving the requested changes."
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

# Supplied lease context lost

## Trigger

Submit an ordinary edit with a supplied token/run/generation that no longer holds the lease.

## Outcome

The lost lease context is rejected without saving the requested changes.
