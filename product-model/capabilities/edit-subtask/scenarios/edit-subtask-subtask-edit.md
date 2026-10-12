---
kind: "edge"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Edit addressed child metadata with a stale ordinary-work revision or an occupied ordinary-write lease."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::task-detail"
      rest-work:
        place: "rest::work::task-record"
  - text: "Subtask title/description change through its raw child repository path; the ordinary revision/lease fence is not applied."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "subtask"
        effect: "changes"
        facts:
          - "Title"
          - "Description"
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

# Subtask edit

## Trigger

Edit addressed child metadata with a stale ordinary-work revision or an occupied ordinary-write lease.

## Outcome

Subtask title/description change through its raw child repository path; the ordinary revision/lease fence is not applied.
