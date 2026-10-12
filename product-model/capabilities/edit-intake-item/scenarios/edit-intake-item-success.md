---
kind: "primary"
routes:
  rest-work: "Rest Work"
steps:
  - text: "Supply supported ordinary request changes."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work"
  - text: "Intake item metadata changes; direct status/resolution/creator replacement is not accepted by ordinary editing."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "intake-item"
        effect: "changes"
        facts:
          - "Title"
          - "Description"
          - "Context"
          - "Priority"
          - "Start date"
          - "Due date"
          - "Revision"
    contexts:
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

# Edit intake item: successful operation

## Trigger

Supply supported ordinary request changes.

## Outcome

Intake item metadata changes; direct status/resolution/creator replacement is not accepted by ordinary editing.
