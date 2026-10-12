---
kind: "primary"
routes:
  web-work: "Web Work"
  rest-work: "Rest Work"
steps:
  - text: "Reject a Pending request with a nonempty reason."
    kind: "actor"
    actor: "root-administrator"
    entities: []
    contexts:
      web-work:
        place: "web::work::intake"
      rest-work:
        place: "rest::work"
  - text: "The Intake item becomes Rejected with its reason."
    kind: "product"
    actor: "root-administrator"
    entities:
      - entity: "intake-item"
        effect: "changes"
        facts:
          - "Resolution"
          - "Revision"
        from: "Pending"
        to: "Rejected"
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

# Reject intake item: successful operation

## Trigger

Reject a Pending request with a nonempty reason.

## Outcome

The Intake item becomes Rejected with its reason.
