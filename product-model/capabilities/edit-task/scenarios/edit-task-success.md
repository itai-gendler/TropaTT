---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Supply supported ordinary metadata and, optionally, a positive current revision."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::task-detail"
      rest-work:
        place: "rest::work::task-record"
  - text: "The Task metadata is saved through the ordinary write fence and its revision advances."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "task"
        effect: "changes"
        facts:
          - "Title"
          - "Description"
          - "Priority"
          - "Activity"
          - "Start date"
          - "Due date"
          - "Project"
          - "Counterparty"
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

# Edit task: successful operation

## Trigger

Supply supported ordinary metadata and, optionally, a positive current revision.

## Outcome

The Task metadata is saved through the ordinary write fence and its revision advances.
