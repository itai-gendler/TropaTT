---
kind: "validation"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Invalid title, referenced context or supported input is rejected before creation."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::tasks"
      rest-work:
        place: "rest::work::task-record"
  - text: "Invalid title, referenced context or supported input is rejected before creation."
    kind: "condition"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::tasks"
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

# Create task: refused or unavailable operation

## Trigger

Invalid title, referenced context or supported input is rejected before creation.

## Outcome

Invalid title, referenced context or supported input is rejected before creation.
