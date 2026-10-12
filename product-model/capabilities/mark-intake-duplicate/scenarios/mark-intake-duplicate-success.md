---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Mark a Pending request as duplicate of a supported existing target."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::intake"
      rest-work:
        place: "rest::work"
  - text: "The Intake item becomes Duplicate with its target reference."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "intake-item"
        effect: "changes"
        facts:
          - "Duplicate"
          - "Resolution"
          - "Revision"
        from: "Pending"
        to: "Duplicate"
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

# Mark intake duplicate: successful operation

## Trigger

Mark a Pending request as duplicate of a supported existing target.

## Outcome

The Intake item becomes Duplicate with its target reference.
