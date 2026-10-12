---
kind: primary
routes:
  web-work: Web Work
  rest-work: Rest Work
steps:
- text: Read incoming work and its selected request activity.
  kind: actor
  actor: root-administrator
  entities: []
  contexts:
    web-work:
      place: web::work::intake
    rest-work:
      place: rest::work
- text: Intake item records, resolution links and displayed activity are returned.
  kind: product
  actor: root-administrator
  entities:
  - entity: intake-item
    effect: reads
    facts:
    - Title
    - Description
    - Source
    - Context
    - Priority
    - Start date
    - Due date
    - Assignee
    - Revision
    - Resolution
    - Task
    - Duplicate
    - Creator
    - Snoozed until
  - entity: intake-activity
    effect: reads
    facts:
    - Actor
    - Event
    - Field
    - Previous value
    - New value
    - Note
    - Created at
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

# Browse intake: successful operation

## Trigger

Read incoming work and its selected request activity.

## Outcome

Intake item records, resolution links and displayed activity are returned.
