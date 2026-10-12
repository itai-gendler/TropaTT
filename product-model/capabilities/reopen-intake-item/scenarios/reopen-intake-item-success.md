---
kind: primary
routes:
  web-work: Web Work
  rest-work: Rest Work
steps:
- text: Reopen a rejected request.
  kind: actor
  actor: root-administrator
  entities: []
  contexts:
    web-work:
      place: web::work::intake
    rest-work:
      place: rest::work
- text: The Intake item returns to Pending; accepted requests do not reopen.
  kind: product
  actor: root-administrator
  entities:
  - entity: intake-item
    effect: changes
    facts:
    - Resolution
    - Revision
    - Snoozed until
    from: Rejected
    to: Pending
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

# Reopen intake item: successful operation

## Trigger

Reopen a rejected request.

## Outcome

The Intake item returns to Pending; accepted requests do not reopen.
