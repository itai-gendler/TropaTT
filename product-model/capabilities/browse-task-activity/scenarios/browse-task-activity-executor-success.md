---
kind: "primary"
routes:
  rest-work: "Rest Work"
steps:
  - text: "Read activity of work in a granted record."
    kind: "actor"
    actor: "external-executor"
    entities: []
    contexts:
      rest-work:
        place: "rest::work::task-record"
  - text: "Task activity records for the reachable work are returned."
    kind: "product"
    actor: "external-executor"
    entities:
      - entity: "task-activity"
        effect: "reads"
        facts:
          - "Actor"
          - "Event"
          - "Field"
          - "Previous value"
          - "New value"
          - "Created at"
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

# Browse task activity as external executor

## Trigger

Read activity of work in a granted project.

## Outcome

Task activity records for the reachable work are returned.
