---
appliesTo:
  - type: "capability"
    id: "add-task-relation"
  - type: "capability"
    id: "remove-task-relation"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/task/TaskRelationController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/TaskRelationService.php"
---

# Typed relations retain normalization and guarded cycle checks

Typed Task relations normalize reverse and symmetric forms, guard duplicate representations and apply cycle checks only to the guarded relation kinds. Removing a relation does not delete either Task.
