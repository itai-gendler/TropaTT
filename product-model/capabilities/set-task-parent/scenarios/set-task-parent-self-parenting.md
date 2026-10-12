---
kind: "validation"
routes:
  rest-work: "Rest Work"
steps:
  - text: "Set work as its own parent."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work::task-record"
  - text: "Self-parenting is rejected and the parent reference is unchanged."
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

# Self-parenting

## Trigger

Set work as its own parent.

## Outcome

Self-parenting is rejected and the parent reference is unchanged.
