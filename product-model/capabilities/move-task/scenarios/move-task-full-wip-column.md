---
kind: "edge"
routes:
  rest-work: "Rest Work"
steps:
  - text: "Move to a different status whose unscoped active-work count reaches its configured WIP limit."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work::task-record"
  - text: "Dedicated movement is refused by the WIP check; ordinary status editing is a different path."
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

# Full WIP column

## Trigger

Move to a different status whose unscoped active-work count reaches its configured WIP limit.

## Outcome

Dedicated movement is refused by the WIP check; ordinary status editing is a different path.
