---
appliesTo:
  - type: "capability"
    id: "delete-task"
    contexts:
      - place: "web::work"
      - place: "rest::work"
      - place: "mcp"
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

# Task removal is logical with its direct-child cascade

Task deletion is logical and cascades to direct child subtasks through the inspected path. Repeating deletion can still return success and run hooks. The behavior does not establish recursive physical removal or ordinary-update revision/lease fencing.
