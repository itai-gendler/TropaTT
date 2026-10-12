---
kind: edge
routes:
  web-work: Web Work
  rest-work: Rest Work
steps:
- text: Retry valid creation using a key with a remembered successful response.
  kind: actor
  actor: root-administrator
  entities: []
  contexts:
    web-work:
      place: web::work::tasks
    rest-work:
      place: rest::work::task-record
- text: The earlier Task response is replayed without a new creation.
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
    web-work:
      place: web::work::tasks
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

# Remembered creation response

## Trigger

Retry valid creation using a key with a remembered successful response.

## Outcome

The earlier Task response is replayed without a new creation.
