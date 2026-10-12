---
kind: "primary"
routes:
  rest-work: "Rest Work"
steps:
  - text: "Supply supported rate overrides on the selected work."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work::task-record"
  - text: "Task financial overrides change through the ordinary update path."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "task"
        effect: "changes"
        facts:
          - "Cost rate"
          - "Bill rate"
          - "Payout rate"
          - "Currency"
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

# Edit task rates: successful operation

## Trigger

Supply supported rate overrides on the selected work.

## Outcome

Task financial overrides change through the ordinary update path.
