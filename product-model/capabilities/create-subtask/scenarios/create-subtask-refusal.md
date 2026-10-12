---
kind: "validation"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Missing title or invalid canonical child status is rejected."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::task-detail"
      rest-work:
        place: "rest::work::task-record"
  - text: "Missing title or invalid canonical child status is rejected."
    kind: "condition"
    actor: "root-administrator"
    entities: []
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

# Create subtask: refused or unavailable operation

## Trigger

Missing title or invalid canonical child status is rejected.

## Outcome

Missing title or invalid canonical child status is rejected.
