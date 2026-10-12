---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Read the displayed activity of selected work."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::task-detail"
      rest-work:
        place: "rest::work::task-record"
  - text: "Task activity records are returned in the inspected order."
    kind: "product"
    actor: "root-administrator"
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

# Browse task activity: successful operation

## Trigger

Read the displayed activity of selected work.

## Outcome

Task activity records are returned in the inspected order.
