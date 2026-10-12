---
kind: primary
routes:
  web-work: Web Work
  rest-work: Rest Work
steps:
- text: Defer a Pending request to a valid future snooze date.
  kind: actor
  actor: root-administrator
  entities: []
  contexts:
    web-work:
      place: web::work::intake
    rest-work:
      place: rest::work
- text: The Intake item becomes Snoozed with its deferral information.
  kind: product
  actor: root-administrator
  entities:
  - entity: intake-item
    effect: changes
    facts:
    - Snoozed until
    - Revision
    from: Pending
    to: Snoozed
  contexts:
    web-work:
      place: web::work::intake
    rest-work:
      place: rest::work
references:
- kind: code
  role: implementation
  target: upload/api/system/library/service/IntakeItemService.php
- kind: code
  role: implementation
  target: upload/api/controller/intake/IntakeItemController.php
- kind: code
  role: implementation
  target: upload/api/model/intake/IntakeItemRepository.php
---

# Snooze intake item: successful operation

## Trigger

Defer a Pending request to a valid future snooze date.

## Outcome

The Intake item becomes Snoozed with its deferral information.
