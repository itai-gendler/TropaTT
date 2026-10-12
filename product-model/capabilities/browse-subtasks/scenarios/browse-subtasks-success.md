---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Request addressed child work under a parent."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::task-detail"
      rest-work:
        place: "rest::work::task-record"
  - text: "Subtask records and ordering are returned."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "subtask"
        effect: "reads"
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

# Browse subtasks: successful operation

## Trigger

Request addressed child work under a parent.

## Outcome

Subtask records and ordering are returned.
