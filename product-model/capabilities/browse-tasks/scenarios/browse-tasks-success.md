---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
  web-detail: "Web Detail"
  web-my-day: "Web My Day"
  web-my-week: "Web My Week"
  rest-record: "Rest Record"
steps:
  - text: "Read a work collection or a selected work identifier."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::tasks"
      rest-work:
        place: "rest::work::task-collection"
      web-detail:
        place: "web::work::task-detail"
      web-my-day:
        place: "web::work::my-day"
      web-my-week:
        place: "web::work::my-week"
      rest-record:
        place: "rest::work::task-record"
  - text: "Task facts are returned with filtering appropriate to the response path."
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
    contexts:
      web-work:
        place: "web::work::tasks"
      rest-work:
        place: "rest::work::task-collection"
      web-detail:
        place: "web::work::task-detail"
      web-my-day:
        place: "web::work::my-day"
      web-my-week:
        place: "web::work::my-week"
      rest-record:
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

# Browse tasks: successful operation

## Trigger

Read a work collection or a selected work identifier.

## Outcome

Task facts are returned with filtering appropriate to the response path.
