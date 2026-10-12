---
kind: "primary"
routes:
  rest-work: "Rest Work"
steps:
  - text: "Choose a supported destination status or record through dedicated movement."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work::task-record"
  - text: "The Task moves to the requested destination and the movement response is returned."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "task"
        effect: "changes"
        facts:
          - "Status"
          - "Project"
          - "Revision"
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

# Move task: successful operation

## Trigger

Choose a supported destination status or project through dedicated movement.

## Outcome

The Task moves to the requested destination and the movement response is returned.
