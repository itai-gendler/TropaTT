---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Supply a nonempty title and supported work context, assignment and classification."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::tasks"
      rest-work:
        place: "rest::work::task-record"
  - text: "A Task with a stable key, default or requested status and creation defaults is returned."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "task"
        effect: "creates"
        facts:
          - "Key"
          - "Title"
          - "Description"
          - "Status"
          - "Priority"
          - "Activity"
          - "Start date"
          - "Due date"
          - "Revision"
          - "Archived at"
          - "Deleted at"
          - "Creator"
          - "Assignee"
          - "Project"
          - "Counterparty"
          - "Parent"
          - "Cost rate"
          - "Bill rate"
          - "Payout rate"
          - "Currency"
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

# Create task: successful operation

## Trigger

Supply a nonempty title and supported work context, assignment and classification.

## Outcome

A Task with a stable key, default or requested status and creation defaults is returned.
