---
appliesTo:
- type: capability
  id: create-task
  contexts:
  - place: web::work
  - place: rest::work
  - place: mcp
references:
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
- kind: code
  role: implementation
  target: upload/web/install/mysql-schema.snapshot.sql
---

# Creation replay remembers a response without guaranteeing exactly-once writes

Creation replay uses a key no longer than 255 characters and a hash of actor, request method, route and key. Payload and organization are absent from that hash. Applicable validation occurs before replay. The producer runs before its response is remembered, and producer error responses can also be remembered. The inspected storage does not uniquely constrain key_hash and production plus remembering is not an atomic reservation, so response replay is not an exactly-once creation guarantee. MCP controller delegation retains outer headers/path and clears query; tool name is not independently established as replay scope.
