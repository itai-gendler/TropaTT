---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Request reachable runtime labels and selected work record entries."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::task-detail"
      rest-work:
        place: "rest::work::task-record"
  - text: "Tag records and their work assignments are returned."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "tag"
        effect: "reads"
        facts:
          - "Title"
          - "Organization"
      - entity: "task-tag-assignment"
        effect: "reads"
        facts:
          - "Task"
          - "Tag"
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

# Browse task tags: successful operation

## Trigger

Request reachable runtime tags and selected work tag entries.

## Outcome

Tag records and their work assignments are returned.
