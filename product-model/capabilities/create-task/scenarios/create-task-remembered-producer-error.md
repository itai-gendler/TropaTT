---
kind: edge
routes:
  rest-work: Rest Work
steps:
- text: Retry valid creation under a key with a remembered producer error.
  kind: actor
  actor: root-administrator
  entities: []
  contexts:
    rest-work:
      place: rest::work::task-record
- text: The earlier error response is replayed; the retry creates no new work.
  kind: condition
  actor: root-administrator
  entities: []
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

# Remembered producer error

## Trigger

Retry valid creation under a key with a remembered producer error.

## Outcome

The earlier error response is replayed; the retry creates no new work.
