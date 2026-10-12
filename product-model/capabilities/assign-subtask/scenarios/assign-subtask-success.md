---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Select the child assignment input."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::task-detail"
      rest-work:
        place: "rest::work::task-record"
  - text: "The Subtask assignment is updated; unresolved optional assignment can become empty."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "subtask"
        effect: "changes"
        facts:
          - "Assignee"
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

# Assign subtask: successful operation

## Trigger

Select the child assignment input.

## Outcome

The Subtask assignment is updated; unresolved optional assignment can become empty.
