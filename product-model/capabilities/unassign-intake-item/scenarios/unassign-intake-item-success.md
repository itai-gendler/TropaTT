---
kind: "primary"
routes:
  rest-work: "Rest Work"
steps:
  - text: "Clear the incoming-work assignment with null or zero input."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work"
  - text: "The Intake item assignee becomes empty."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "intake-item"
        effect: "changes"
        facts:
          - "Assignee"
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

# Unassign intake item: successful operation

## Trigger

Clear the incoming-work assignment with null or zero input.

## Outcome

The Intake item assignee becomes empty.
