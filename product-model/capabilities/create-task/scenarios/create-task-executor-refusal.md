---
kind: "validation"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Missing or inaccessible record context prevents creation."
    kind: "actor"
    actor: "external-executor"
    entities: []
    contexts:
      web-work:
        place: "web::work::tasks"
      rest-work:
        place: "rest::work::task-record"
  - text: "Missing or inaccessible record context prevents creation."
    kind: "condition"
    actor: "external-executor"
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

# Create task external executor boundary

## Trigger

Missing or inaccessible project context prevents creation.

## Outcome

Missing or inaccessible project context prevents creation.
