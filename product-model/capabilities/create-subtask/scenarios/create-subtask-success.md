---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Supply a nonempty title and supported child metadata."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::task-detail"
      rest-work:
        place: "rest::work::task-record"
  - text: "A Subtask is created with its parent, order, inherited context and stable underlying work identity."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "subtask"
        effect: "creates"
        facts:
          - "Title"
          - "Description"
          - "Status"
          - "Priority"
          - "Due date"
          - "Order"
          - "Parent"
          - "Project"
          - "Assignee"
          - "Deleted at"
    contexts:
      web-work:
        place: "web::work::task-detail"
      rest-work:
        place: "rest::work::task-record"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/subtask/SubtaskController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/SubtaskService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/model/subtask/SubtaskRepository.php"
---

# Create subtask: successful operation

## Trigger

Supply a nonempty title and supported child metadata.

## Outcome

A Subtask is created with its parent, order, inherited context and stable underlying work identity.
