---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Confirm deletion of the selected work."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::task-detail"
      rest-work:
        place: "rest::work::task-record"
  - text: "The Task is soft-deleted and direct child work is cascaded by the inspected deletion path."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "task"
        effect: "removes"
      - entity: "subtask"
        effect: "removes"
        with: "task"
    contexts:
      web-work:
        place: "web::work::task-detail"
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

# Delete task: successful operation

## Trigger

Confirm deletion of the selected work.

## Outcome

The Task is soft-deleted and direct child work is cascaded by the inspected deletion path.
