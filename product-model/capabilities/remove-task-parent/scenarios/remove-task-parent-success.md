---
kind: "primary"
routes:
  rest-work: "Rest Work"
steps:
  - text: "Clear the existing parent work reference."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work::task-record"
  - text: "The Task parent becomes empty."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "task"
        effect: "changes"
        facts:
          - "Parent"
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

# Remove task parent: successful operation

## Trigger

Clear the existing parent work reference.

## Outcome

The Task parent becomes empty.
