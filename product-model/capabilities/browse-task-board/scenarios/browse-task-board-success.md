---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Request work grouped by status and inspected board filters."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::kanban"
      rest-work:
        place: "rest::work::task-board"
  - text: "Task projections and status columns are returned."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "task"
        effect: "reads"
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
      - entity: "task-status"
        effect: "reads"
        facts:
          - "Code"
          - "Title"
          - "Order"
          - "Active"
          - "Terminal"
          - "WIP limit"
          - "Organization"
    contexts:
      web-work:
        place: "web::work::kanban"
      rest-work:
        place: "rest::work::task-board"
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

# Browse task board: successful operation

## Trigger

Request work grouped by status and inspected board filters.

## Outcome

Task projections and status columns are returned.
