---
appliesTo:
- type: capability
  id: delete-task-status
  contexts:
  - place: web::administration
  - place: rest::work
references:
- kind: code
  role: implementation
  target: upload/api/system/library/service/StatusService.php#delete
- kind: code
  role: implementation
  target: upload/api/model/status/StatusRepository.php#remapTaskScope
---

# Status remapping uses its raw write contract

Deleting an in-use Task status requires the applicable replacement and remaps matching Tasks before deleting the dictionary record. Those raw writes do not use the ordinary Task lease fence, activity history or revision contract. A remap is not evidence that ordinary movement validation ran.
