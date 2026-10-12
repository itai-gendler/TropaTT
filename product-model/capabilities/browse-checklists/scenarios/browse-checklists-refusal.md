---
kind: "validation"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Unavailable parent work cannot return its record records."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::task-detail"
      rest-work:
        place: "rest::work::task-record"
  - text: "Unavailable parent work cannot return its record records."
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
    target: "upload/api/controller/checklist/ChecklistController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/ChecklistService.php"
---

# Browse checklists: refused or unavailable operation

## Trigger

Unavailable parent work cannot return its checklist records.

## Outcome

Unavailable parent work cannot return its checklist records.
