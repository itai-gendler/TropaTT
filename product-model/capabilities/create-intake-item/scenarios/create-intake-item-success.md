---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Supply a title and supported request context and defaults."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::intake"
      rest-work:
        place: "rest::work"
  - text: "A Pending Intake item is saved and its creation activity recorded."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "intake-item"
        effect: "creates"
        facts:
          - "Title"
          - "Description"
          - "Source"
          - "Context"
          - "Priority"
          - "Start date"
          - "Due date"
          - "Assignee"
          - "Revision"
          - "Resolution"
          - "Task"
          - "Duplicate"
          - "Creator"
        to: "Pending"
    contexts:
      web-work:
        place: "web::work::intake"
      rest-work:
        place: "rest::work"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/IntakeItemService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/intake/IntakeItemController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/model/intake/IntakeItemRepository.php"
---

# Create intake item: successful operation

## Trigger

Supply a title and supported request context and defaults.

## Outcome

A Pending Intake item is saved and its creation activity recorded.
