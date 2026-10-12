---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Request work for the linked customer."
    kind: "actor"
    actor: "external-observer"
    entities: []
    contexts:
      web-work:
        place: "web::work::tasks"
      rest-work:
        place: "rest::work::task-collection"
  - text: "Task records for the linked customer are returned; foreign-customer records are absent."
    kind: "product"
    actor: "external-observer"
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
          - "Payout rate"
          - "Currency"
    contexts:
      web-work:
        place: "web::work::tasks"
      rest-work:
        place: "rest::work::task-collection"
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

# Browse tasks as external observer

## Trigger

Request work for the linked customer.

## Outcome

Task records for the linked customer are returned; foreign-customer records are absent.
