---
appliesTo:
  - type: "capability"
    id: "create-task"
  - type: "capability"
    id: "edit-task"
references:
  - kind: "code"
    role: "implementation"
    target: "upload/api/controller/task/TaskController.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/service/TaskService.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/model/task/TaskRepository.php"
  - kind: "code"
    role: "implementation"
    target: "upload/api/system/library/support/TaskStatusSemantics.php"
---

# Task keys are stable after generation

Task creation generates its stable key from the applicable project/key context, retries uniqueness conflicts and reports failure when those retries cannot produce a usable key. Ordinary edits preserve the key rather than regenerating it whenever other fields change.
