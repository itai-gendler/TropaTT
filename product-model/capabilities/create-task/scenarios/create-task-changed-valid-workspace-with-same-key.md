---
kind: edge
routes:
  rest-work: Rest Work
steps:
- text: Retry creation using the same actor, method, route and key after selecting another valid workspace.
  kind: actor
  actor: root-administrator
  entities: []
  contexts:
    rest-work:
      place: rest::work::task-record
- text: The earlier Task response can replay; workspace selection is absent from key hashing.
  kind: product
  actor: root-administrator
  entities:
  - entity: task
    effect: reads
    facts:
    - Key
    - Title
    - Description
    - Status
    - Priority
    - Activity
    - Start date
    - Due date
    - Revision
    - Archived at
    - Deleted at
    - Creator
    - Assignee
    - Project
    - Counterparty
    - Parent
    - Cost rate
    - Bill rate
    - Payout rate
    - Currency
  contexts:
    rest-work:
      place: rest::work::task-record
references:
- kind: code
  role: implementation
  target: upload/api/controller/task/TaskController.php
- kind: code
  role: implementation
  target: upload/api/system/library/service/TaskService.php
- kind: code
  role: implementation
  target: upload/api/model/task/TaskRepository.php
- kind: code
  role: implementation
  target: upload/api/system/library/support/TaskStatusSemantics.php
- kind: code
  role: implementation
  target: upload/api/controller/common/BaseController.php#withIdempotency
- kind: code
  role: implementation
  target: upload/api/system/library/service/IdempotencyService.php#replay
- kind: code
  role: implementation
  target: upload/api/system/library/service/IdempotencyService.php#remember
- kind: code
  role: implementation
  target: upload/api/model/common/IdempotencyRepository.php
---

# Changed valid workspace with same key

## Trigger

Retry creation using the same actor, method, route and key after selecting another valid workspace.

## Outcome

The earlier Task response can replay; workspace selection is absent from key hashing.
