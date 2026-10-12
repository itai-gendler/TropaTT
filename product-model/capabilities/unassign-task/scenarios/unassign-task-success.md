---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Clear the assignment using the supported empty designation."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::task-detail"
      rest-work:
        place: "rest::work::task-record"
  - text: "The Task assignee becomes empty."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "task"
        effect: "changes"
        facts:
          - "Assignee"
          - "Revision"
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

# Unassign task: successful operation

## Trigger

Clear the assignment using the supported empty designation.

## Outcome

The Task assignee becomes empty.
