---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Supply supported child metadata."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::task-detail"
      rest-work:
        place: "rest::work::task-record"
  - text: "Subtask metadata changes through its separate repository update path."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "subtask"
        effect: "changes"
        facts:
          - "Title"
          - "Description"
          - "Priority"
          - "Due date"
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

# Edit subtask: successful operation

## Trigger

Supply supported child metadata.

## Outcome

Subtask metadata changes through its separate repository update path.
