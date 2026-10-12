---
kind: "primary"
routes:
  rest-work: "Rest Work"
steps:
  - text: "Select a valid person for incoming-work assignment."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      rest-work:
        place: "rest::work"
  - text: "The Intake item assignee changes."
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

# Assign intake item: successful operation

## Trigger

Select a valid person for incoming-work assignment.

## Outcome

The Intake item assignee changes.
