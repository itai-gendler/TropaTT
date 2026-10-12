---
kind: "validation"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "An explicitly forbidden workspace is rejected."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::kanban"
      rest-work:
        place: "rest::work::task-board"
  - text: "An explicitly forbidden workspace is rejected."
    kind: "condition"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::kanban"
      rest-work:
        place: "rest::work::task-board"
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

# Browse task board: refused or unavailable operation

## Trigger

An explicitly forbidden workspace is rejected.

## Outcome

An explicitly forbidden workspace is rejected.
